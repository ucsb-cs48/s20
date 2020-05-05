---
desc: "Tuesday Lecture: Planning MVP Demos, Other Topics"
lecture_date: 2020-05-05
num: lect16
ready: false
---

# Today

* More details about demos
* 

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
  - Cover methods GET/POST/PUT/DELETE
  - HTTP Header Fields
  - HTTP Status Codes
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


#  Various Topics (rough notes)


* Discuss *front-end* vs. *backend*
  - End point vs. API end points
  - Frontend: loading web pages you see in your browser.  You can test by just putting URL in the browser and seeing what comes up.
  - Backend: these are web request/response transactions that are hidden away: the browser talks to the server and exchanges JSON messages.  You can test those using `curl` or Postman (or dev tools of the browser) but you usually can't do it just by typing URLs into your web browser.

* Discuss React `pages` vs. Node `pages/api`

* Passing data within/among React components. 
 
# Setting up MongoDB

How do you connect to MongoDB?

Tutorial from Bryan...   specifically in the context of React / Next.js


