---
desc: "Thursday Lecture: public vs private, licenses, 3rd party libraries, more"
lecture_date: 2020-04-28
num: lect14
ready: false
---

# Today in Lecture

Plenary

* Overview of lecture
* Teams page on course website  <https://ucsb-cs48.github.io/s20/teams_page/>
* Discussion of role of staff liaisons for teams
* Discussion of Public vs. Private
  - And limited in-class sharing
* Considerations for Public Repos:
  - Licenses (MIT, GPL, etc.)
  - Auditing for secrets
* High Level Concerns / Information Sharing across teams
* Optional: a few words on MongoDB
  - How to share MongoDB instances with your team
  - How to have multiple MongoDB's for production / QA / dev
  
In Breakout Groups:

* Standup
* Check your Team's row on <https://ucsb-cs48.github.io/s20/teams_page/>
  - Especially check the Kanban board link
  - If your team is using multiple Kanban boards, let a staff member know  which one is currently the primary active one, so we can update the table; the project number goes in the Project Number column.
  - If your team has multiple repos (e.g. one for front end and one for back end, as `s3-t3-poker` is doing) then the kanban project board is at the organization level.  We indicate this by putting a lowercase `p` in front of the project number.
* Staff will ask about aspects/feature of your app 
  - Purpose of this is to help us figure out how to promote more sharing of learning across teams, and what to focus on.
  - Staff will fill in row [in this table](https://docs.google.com/spreadsheets/d/1vRz72xn1w1PXdIOZP1ieny6_AS0o8gXjCaih-IauJAo/edit?usp=sharing)
  - This may require some team discussion to figure out
  - For each cell, enter yes / no / it's complicated / or ?
  - If "it's complicated" is your answer, add a brief report in your `team/STATUS.md` file under today's date with an explanation.
  - If you are unsure, just put a ? in the table and move on.
* Discuss: Public or Private?
  * Add line near top of `team/AGREEMENTS.md` to indicate decision
  * See details below.
* If public: 
  - make it public
  - add a LICENSE (e.g. MIT)
    - This web site helps you choose a license <https://choosealicense.com/>
    - It will also make an automatic PR to put the license in the repo
  - Audit for secrets
* Other work as you see fit

# Staff Liaisons

I've assigned staff liaisons for each team: 
* since there are sixteen teams, each LA (undergrad) has three teams and Scott (the TA) has one team.

The main role of the staff liaison is to be one central point of contact between each team and the staff.    

Some of the roles these liaisons will play:
* collecting information about your team's progress for course grading purposes
* communicating to the instructor what kind of support your team needs from the staff

Your can see which staff member was assigned to your team by visiting this link:  
* <https://ucsb-cs48.github.io/s20/teams_page/>

**Note that you'll continue to have interactions with many staff members.**

While you might see your course liaison dropping in more often on your breakout groups than other staff members, we will still change things up now and then so you get a variety of perspectives.

# public vs. private?

pros/cons of going public (open source)

Pros: 
* easier to share information with classmates
* easier to share your code with potential employers

Cons:
* give up some privacy
* must consider license and audit for secrets
* if you plan to monetize (which is historically rare for CS48 projects) could be a problem.

License concerns:
* Easiest: slap an MIT license on it and forget it
* Or, include GPL if you have strong feelings about not permitting closed source use

Auditing for Secrets:

- Be sure to audit for `.env, secrets-localhost.properties, secrets-heroku.properties`
- Includes Auth0 credentials, but also MongoDB URIs.
- Be sure to audit for secrets embedded in your code (e.g. from tutorials from other sources)
- If you have any of these, even on older commits or other branches, do NOT make repo public unless/until you 
  invalidate old secrets.  (How to do that is platform dependent--done on Auth0, or cloud.mongodb.com, etc.)

# Another option: "limited" sharing within the class

If you are willing to allows us to give other class teams "read only" access to your code, pleae let us know.

This has the benefits of allowing us to do some sharing  (e.g. among teams using `socket.io` or solving
particular issues with MongoDB or uses of React) without risks of making repos fully public.

# Let us know by adding a line to top of `team/AGREEMENTS.md`

If there isn't already heading at the top of your existing team agreements file, add one, e.g. 

```
# Initial Team Agreements
```

Then, *above that* at the top of the file, copy/paste one of these three options.  (Optionally, you may also add another other discussion points that seem relevant, e.g. if there was disagreement and you came to a compromise, or the concerns that led you to your decision.)

1. Fully open source
   ```
   # 4/30/2020
   
   Team decided to make repo public (open source under ____ license).
   ```

2. Closed source, but open to classmates as needed

   ```
   # 4/30/2020

   Team decided to keep repo closed source, but allow read only access to other CS48 S20 teams on a limited basis, 
   as determined by course staff when there is an learning opportunity.
   ```

3. Fully closed source, including to classmates

   ```
   # 4/30/2020

   Team decided to keep repo closed source, with access only by course staff, not by other teams.
   ```

# Integrating with 3rd Parties

Some comments on how to integrate with 3rd parties

* Approach 1: Find any old javascript tutorial, and the wedge it into next.js
* Approach 2: Actually look for React + Plaid, or Next.js + socket.io, etc.

We encourage you to try #2 first, and use #1 only when approach #2 fails.

In addition, today in lecture let us know (in the chat during the plenary if possible) what other third party libraries, functions, etc. you are trying to integrate with your code.   We'd like to help cross-pollination where possible to make it easier for all teams, and allow you to build better products.


# Big picture patterns

* socket.io for real time communication
  - Missile, Spotify Queues, Poker?, Mafia?
* loading big datasets
  - new-city (Spring Boot), other teams?
* OAuth other than Google
  - Plaid API (has it's own OAuth), Slack-Bot (Slack has it's own OAuth).
  


# MongoDB Setup

* Setting up a MongoDB database for the first time:
  - <https://ucsb-cs48.github.io/topics/mongodb_cloud_atlas_setup/>
* Sharing access to a MongoDB database with your team 
  - <https://ucsb-cs48.github.io/topics/mongodb_cloud_atlas_sharing/>
* Setting up separate MongoDB instances for production, qa (staging) and dev
  - No instructions yet, just a PR, but this shows what's needed 
  - PR: <https://github.com/ucsb-cs48-s20/project-idea-reviewer-nextjs/pull/19>
  - The change is only a change in the file `next.config.js`; the rest is documentation.
