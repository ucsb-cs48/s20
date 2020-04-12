---
assigned: 2020-04-13 16:00
desc: Deployment Practice
due: 2020-04-17 17:00
layout: lab
num: lab00
ready: false
slack_url: https://ucsb-cs48-s20.slack.com
github_org: ucsb-cs48-s20
---

In this individual lab, you will practice deploying a web app to the cloud using the stack that your group has chosen.

**Purpose**: To ensure that each member of the team is familiar with how to deploy the chosen technology stack


Each member of your project team should complete the appropriate version of this lab as an individual

You'll start with a few steps that are common to both versions of the lab.

You'll the continue the lab with steps specific to your technology stack.


# Step 1: Create a repo

Create a new github repo in the <tt>{{page.github_org}}</tt> organization (not under your own github id).

The name of the repo should be your githubid, followed by `_lab00`
* For example, if your github id is `cgaucho`, the name should be <tt>cgaucho_lab00</tt>

The repo should be:
* private
* initially empty (no README, no .gitignore, no LICENSE)

Here is what that should look like: 

![creating cgaucho_lab00 under ucsb-cs48-s20](create_lab_repo.png) 

The reason we are creating an empty repo is that we'll be pulling in starter code from another repo in a later step.


# Next Steps

* For the remainder of the lab, there are two different versions of the instructions, depending on the technology stack chosen.

| Stack | Detailed Instructions | Deployment Platform | 
|-------|-----------------------|---------------------|
| Spring Boot (Java) | [lab00_sb]({{'/lab/lab00_sb' | relative_url }}) | Heroku |
| next.js (JavaScript) | [lab00_nj]({{'/lab/lab00_nj' | relative_url }}) | now.sh |


