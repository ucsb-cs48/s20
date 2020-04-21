---
desc: "Tuesday Lecture: Team Deployment"
lecture_date: 2020-04-21
num: lect10
ready: true
---

# lab00 announcements

* Almost everyone is done... just 3 folks on Spring Boot, and 4 on next.js.
* Please get it done asap

# Slack tips

* You can find a person's local time zone by clicking on their avatar
* Handy if/when you have folks working across multiple time zones

# Standup

* What have you gotten done?
* What are you working on now?
* Are there any blockers/obstacles?

# Decide who will lead next retro

* Next Retro will be Monday, 05/04/20
* Choose that person, and add their name to team/LEADERSHIP.md
* Assignment for that person:
  - Go ahead and put a section in team/RETROS.md anticipating
    your next retro.   You can find a template for that here:
    [retro2]({{'/lectures/lect10/retro2' | relative_url}})
    
# Today's work: Getting started with Team Deployment

It's time for your team to spin up some "team deployments"
of your new app.

You are all in different places:
* Some of you have not started coding
* Some of you have started coding

Either way, you can proceed with getting a starting point
web app up for your project.

* The initial deployment can simply be a clone of one of the demo apps;
* You can then iterate on that by deleting things you don't need, and
  customizing the menu items to be relevant, until you have a suitable
  base for building your app

* The first deployment we build will be `production`.
  * This is the "real" version of the app, your "best code" at any point.
  * This should always be running the `master` branch code.
  * The goal is always to keep this code error and bug free, and a good
    experience for your users.

* The next deployment will be `qa`.   This is a version of your app where
  you can deploy branches other than master, and try things out before
  deploying those branches to production.

* Finally, you might also want to have private deployments for your
  individual team members.

At first, if you are using a MongoDB database, you may end up sharing
the same database across these deployments.   However, eventually,
you'll definitely want to have separate MongoDB databases for the
different deployments of your app.  We'll set that up in lab02.

# The details: lab01

For the details, see:

* <https://ucsb-cs48.github.io/s20/lab/lab01/>

This is a group grade.  You'll make one submission for the entire group on Gauchospace.

You should see that you are now assigned to groups on Gauchospace that correspond to your teams.

If you find that you are assigned to the wrong team on Gauchospace, let us know and we'll correct that; send a message
in the `#lab01` channel on the course slack <https://ucsb-cs48-s20.slack.com>.


# Today: Please work on lab01 as a group

If you finish, then use the time however you see fit.

* Work on Learning Plan
* Work on refining iterations
* **OR, get started with coding**

# If coding, please use: feature-branch/pull request workflow

If you know about how to do "feature-branch/Pull Request" workflow,
you can proceed with staring to work on stories for your MVP.

(Some of you may have done that already)

We'll discuss it in detail on Thursday, but as a quick reminder:

* Never work directly on `master`; always create a feature branch
* Example:
  ```
  git checkout master
  git pull origin master
  git checkout -b cgAddRidersMenu
  ```
  
* Be sure to assign issues to individuals and drag them into the "In Progress" column.
* It's a good practice to comment on the issue with the name of the branch where you are working on it.
* Drag issues to the "In Review" column when they are ready to be reviewed by the team.
  * This is a good time to rebase the feature branch on master, and the deploy that branch to
    the QA site, and have everyone bang on it to try to find any bugs or problems.
* Drag them to "Done" only after they've been merged to master and are deployed on the production site.

If this workflow is new to you, see if someone on your team knows about it and can exlain it to the team.

If your *entire* team is new to this workflow:
* ask for help, and someone from the staff can help you get you up to speed, OR
* wait for Thursday's lecture




