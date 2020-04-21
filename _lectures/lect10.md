---
desc: "Tuesday Lecture: Team Deployment"
lecture_date: 2020-04-21
num: lect10
ready: true
---

# lab00 announcements

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
  - Look at the links below and choose an "online retro tool"
    for your next retro.
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

