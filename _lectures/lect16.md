---
desc: "Tuesday Lecture: Planning MVP Demos, Other Topics"
lecture_date: 2020-05-05
num: lect16
ready: false
---

# Today

Before Breakouts:

* More details about demos
* Some notes on various web programming topics

In Breakouts:

* Standup
* Consider doing a "rehearsal" of the demo
* Is `prod` ready for your demo?
  * If not, what needs to happen so that it's ready for the demo?
  * Ask for help from staff if needed
* Then, work as you see fit.

# Planning for your demo

If you choose to make a YouTube video:
* Instructions for Zoom / YouTube <https://youtu.be/k0Je8ASh4jo>
* Where to submit link (lab02): <https://gauchospace.ucsb.edu/courses/mod/assign/view.php?id=3919993>

# Demo from your prod app

Your demo should be from your production app (`prod` on Heroku), not from a version deployed on `localhost`.

Students in the class, as well as Instructors/TAs/LAs should be able to visit your production link and try out the app after watching your video.

So, make every effort to have your production version ready to go with a stable MVP on Thursday.

# Additional notes about the MVP demo

1. **Features beyond MVP are fine**  Note that if you have moved your production version on master "beyond" your MVP, 
   that's fine; as long as it contains all of the MVP functions.   If you are time restricted, you can focus the demo
   just on the MVP features and "save" the rest for later.
   
2. **Broken `master` is a problem.  You can fix with a `temp-prod` branch**.   
   If your `master` branch is currently "broken" in 
   some way that makes it impossible to do a decent demo from your `prod` Heroku app, then here's a quick fix:
   
   - (a) find an earlier commit that isn't broken 
   - (b) give that commit a branch name `temp-prod` for example 
     - use: `git checkout -b temp-prod` 
     - then `git reset --hard a1b2c3d4` where `a1b2c3d4` 
       is the sha of the commit that's good; 
     - then `git push origin temp-prod -f` 
   - (c) redeploy your prod app using `temp-prod` instead of the master branch.
   
   If you do this, please disclose that you are demoing from `temp-prod` and not master in your lab02 submission 
   so that we aren't confused when evaluating your MVP.  
   
   It's not ideal, but it won't be a major deduction.  It's better than demoing a broken `master` branch.
   
3. **A demo from `localhost` is better than nothing, but isn't really an MVP demo**.   If you absolutely 
   *cannot* do a meaningful demo from your production app, then you may demo from `localhost` as a last resort, rather
   than offering no demo at all.   However, that will result in a lower grade; 
   a localhost app isn't really "viable" in the sense that you can't put it in the hands of customers.   

# Various Topics

## HTTP requests and responses

You will see the idea of **request/response**  all over web programming.

In a NextJS app, many functions found in the code under `pages/api` take parameters `(req, res)`, 
which stand for request and response.  This code from [demo-nextjs-app/pages/api/dog.js, line 3](https://github.com/ucsb-cs48-s20/demo-nextjs-app/blob/5c220b0c08ef3b0a45e8dad87b66798fe6fb874c/pages/api/dog.js#L3) is an example:
```
export default async function (req, res) {
```

In a Spring Boot app, the request and respose objects are often abstracted away, but they are still present, and it's helpful to understand their role.

These videos may help
* 5 minute simple overview of request/response <https://youtu.be/DrI2lUXL1no>
  - Just very basics of request/reponse
* 40 minute deeper dive <https://www.youtube.com/watch?v=iYM2zFP3Zn0>.
  - Covers methods GET/POST/PUT/DELETE
  - HTTP Header Fields and Status Codes
  - Using "Network" Tab in web browser dev tools to look at Request/Response
  - Exploring request/respose with Express and Postman
    - This uses Express directly, which is a good way to explore and understand how request/response work. 
    - NextJS uses a similar *but different* approach to structuring this code, so be aware of that.
    - But the *concepts* and the way you work with Postman is the same.


## GET vs. POST and idempotency

Quick version
* Use GET only for retrieving information; puts query parameters in URL
* Use POST when updating information; puts query parameters in Body

`GET` and `POST` are both examples of HTTP methods.   There are also `PUT`, `DELETE`, and several others.

More information
* 3 minutes: quick GET vs. POST <https://youtu.be/UObINRj2EGY>
* 6 minutes: HTTP Methods in general, including idempotency <https://www.youtube.com/watch?v=guYMSP7JVTA>  


# Front End vs. Back End (nextjs only)

* The "front end" code runs in your browser; the React components are front end code.
  - `components/` directory
  - `pages/` directory (except `pages/api/`)
* The "back end" code runs on the web server (e.g. on Heroku).
  - This code is under `pages/api`
 
The rest of the code in your app (e.g. functions under `utils/`) might be front end code, or back end code, depending on
where it's called from.

**It is important to know where you are**

* You can only talk to the database **directly** from backend code, i.e. the code under `pages/api`
* If you are in front end code (i.e. the code for a React component) and you *need data*, you need to 
  fetch it from the backend by doing a call to a `pages/api` endpoint.

That means that, typically, setting up a page in a NextJS app can involve three steps: 

1.  You *always* create a page under `pages/` that serves up your HTML.
2.  You *often* create reusable React components under `components/` to factor out code from files under `pages/`
3.  You *usually* need to create routes under `pages/api` for backend code 
    that sits between the React components on the front end and the database. 

A bit more detail on each of these:

1.  You *always* create a page under `pages/` that serves up your HTML.

    |         | Project | File | URL |
    |---------|------|------|--------|
    | Simple Example | `project-idea-reviewer-nextjs` | [`pages/index.js`](https://github.com/ucsb-cs48-s20/project-idea-reviewer-nextjs/blob/cc72ea42c082a878f776208b89cb414dd694fa8e/pages/index.js#L1) | [`/`](https://project-idea-reviewer-nextjs.herokuapp.com/) |
    | More Complex Example | `project-idea-reviewer-nextjs` | [`pages/ideas.js`](https://github.com/ucsb-cs48-s20/project-idea-reviewer-nextjs/blob/cc72ea42c082a878f776208b89cb414dd694fa8e/pages/ideas.js#L127) | [`/ideas`](https://project-idea-reviewer-nextjs.herokuapp.com/ideas) |
    {:.table .table-sm .table-striped .table-bordered}

    
    Requests made at the `/` and `/ideas` endpoints are served up by the backend of your server, but with one exception
    noted below, the JavaScript code in these files runs on the client, i.e the "front end", after the page is loaded
    into the app.
    
    The one exception in NextJS is code inside the function `getServerSideProps` ([see example](https://github.com/ucsb-cs48-s20/project-idea-reviewer-nextjs/blob/cc72ea42c082a878f776208b89cb414dd694fa8e/pages/ideas.js#L13)).
    
    
2.  Often: Creating React components under `components/` 


    |         | Project | File | 
    |---------|------|------|
    | `AppNavbar` | project-idea-reviewer-nextjs | [`components/AppNavbar.js`](https://github.com/ucsb-cs48-s20/project-idea-reviewer-nextjs/blob/cc72ea42c082a878f776208b89cb414dd694fa8e/components/AppNavbar.js#L20) |
    {:.table .table-sm .table-striped .table-bordered}

    Factoring out code from the files under `pages` into reusable components is optional, but highly recommended.
    
    You should consider creating a component when:
    * The same kind of thing appears multiple times on a page, or on multiple pages
    * When it just makes the page easier to understand if you can break it into smaller, understandable chunks, even
      if each of those is only used in one place on one page in the app.

3.  Usually: Creating a route under `pages/api` for the front end code to "talk to" to do database operations.


    |         | Project | File | URL |
    |---------|------|------|--------|
    | Example | project-idea-reviewer-nextjs | [`/pages/api/students/index.js`](https://github.com/ucsb-cs48-s20/project-idea-reviewer-nextjs/blob/cc72ea42c082a878f776208b89cb414dd694fa8e/pages/api/students/index.js#L87) | [`/api/students`](https://project-idea-reviewer-nextjs.herokuapp.com/api/students) |
    {:.table .table-sm .table-striped .table-bordered}

    The `/api/students` URL is in your webapp and is served
    from the the same server as your front end pages, but instead of sending HTML/JS in the response, 
    it sends data formatted in JSON.    In addition in a `POST`, data is sent to the server, typically also formatted
    in JSON.

    In the example above, a `GET` request returns a list of all of the students (as JSON) while a `POST` request allows
    a new student to be created.   We can test a `GET` request directly in our browser.
    
    For a `POST` request, it's more
    complicated; we have to use a tool such as `curl` or [Postman](https://ucsb-cs48.github.io/topics/postman/), and set up the `POST` request with the exact format
    of the required headers and request body.

#  Other topics that there may be questions about

* Passing data within/among React components. 

* Connecting to MongoDB

* Making data requests to MongoDB

