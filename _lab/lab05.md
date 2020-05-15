---
layout: lab
num: lab05
ready: false
desc: "Ops Instructions/Video/Review"
assigned: 2020-05-18 12:00
due: 2020-05-26 15:30
github_org: "ucsb-cs48-s20"
---

NOTE: THIS IS STILL A WORK IN PROGRESS... Please return to this later

# Ops Video / Instructions

One of the important aspects of Software Development that often gets overlooked in the academic curriculum is "operations".   

Operations refers to the things other than your code that are necessary to deploy a running application.   This includes:
* configuring the platform on which the software is deployed
* configuring external dependencies such as authorization servers, databases, API credentials, etc.
* configuring initial accounts (for example, accounts for admins, etc.)

Each of your production and QA applications has some "operations" that are necessary to get it deployed on Heroku.

This assignment is divided across two labs, this one, and [lab08](https://ucsb-cs48.github.io/s20/lab/lab08/). 

* In this lab, you'll prepare written deployment instructions and a video with deployment instructions.
* In [lab08](https://ucsb-cs48.github.io/s20/lab/lab08/), your team and the other teams in your section will swap instructions/videos, try them out, and provide feedback, both on the deploy instructions, and on the apps themselves.

# Part One: Written Deployment Instructions

Someone on your team should pprepare a set of instructions with all of the steps necessary to start with nothing but "read only" access to your repo, and end with a running instance of your app on Heroku.  

While this is a team grade, it is likely that you'll assign one or more people from your team to focus on this, while other members of your team are working on fixing bugs or adding new features.  I suggest you make this task an "issue" and track it on your Kanban board along with your other issues.  Ideally, whoever is working on these instructions is not *also* juggling working on a coding issue at the same time.

## Share instructions, NOT credentials

The running instance that your instructions enable should be *entirely separate* from the running instances for your
own team.  That is:

* You should not share any database credentials
* You should not share any OAuth or Auth0 credentials
* You should not share any 3rd party API credentials (e.g. Firebase, Spotify, Google, etc.)
    
Instead of sharing the credentials, you should share *instructions for obtaining those credentials*,
and instructions for configuring those credentials for your application.

These instructions should be in Markdown format, and stored in a file called `/docs/DEPLOY.md` in your repo.
(It is ok to factor this out into separate pages also stored under `/docs` and linked to from `docs/DEPLOY.md`)
    
There should be a link to `./docs/DEPLOY.md` from your main `README.md` file of your repo, e.g.
    
```
* [Deployment Instructions](./docs/DEPLOY.md)
```


# Part Two: Deployment Video

Working from your written deployment instructions, someone on your team should make a video where you follow the written deployment instructions yourselves,
step by step, and show what the deployment looks like.   

For guidance on making the video, you can use the instructions [here](https://youtu.be/k0Je8ASh4jo) for advice on how to do this using Zoom and YouTube; you may also use another tool if you have access to one and prefer it.

If in the course of making that video, you end up showing
values of secrets (e.g. database passwords, OAuth tokens, etc.) you should go back and *invalidate* those tokens before
releasing the video.
    
Today, I suggest that you create a story on your Kanban board for the creation of the deployment video, and put it 
wherever you keep stories that are not ready to start yet; you will eventually assign that story to someone, but
you aren't ready to start it until you have the written instructions done.   

Ideally, the person that makes the video
should be different from the person that wrote the instructions.  That makes it more
likely that if there are any ambiguities, errors, or omissions in the instructions, you'll find them before the video
is finished.  But, this is a recommendation, not a requirement.
    
