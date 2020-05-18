---
layout: lab
num: lab08
ready: true
desc: "Ops Review"
assigned: 2020-05-26 03:30
due: 2020-06-01 11:30
github_org: "ucsb-cs48-s20"
---

# Ops Review

In [lab05](https://ucsb-cs48.github.io/s20/lab/lab05/) you prepared written instructions, and a video for your team's project that 
described how to start with only your team's source code repo, and finish with an production ready instance of the application
up and running on Heroku.

In this lab:
* The 4-6 people on your team will divide up and try out the written instructions and videos of the other three teams
  in your discussion section, and provide feedback to each of them.
* In turn, you'll be receiving feedback from the other three teams in your discussion section on your own
  instructions and video.


# Step 1: Divide up the work


As a team, you are now going to divide up the three other teams apps from your discussion section among the 
individuals on your team, and working as individuals or in pairs, you'll try following the other teams 
instructions.
   
In the file `team/DEPLOY.md`, put in a table such as this one where you indicate how you are dividing up the 
reviewing.  Refer to <https://ucsb-cs48.github.io/s20/teams_page/> for the actual teams that are in your discussion
section.

```
# Deployment Testing
    
Our team: s0-t1-ride-share

Other Teams:
  
| Team    | Who is reviewing |
|----------------|------------------|
| s0-t2-covid-19 | Alice, Bob       |
| s0-t3-restaurant-reviews | Chris, Danny |
| s0-t4-dog-sitting | Ellery |
```
    
# Step 2: Obtain and Grant GitHub repo access 

For each team, there will be a repo that has the name of the team, followed by `DEPLOY_FEEDBACK`.

For instance:

* s3-t4-textbooks-DEPLOY-FEEDBACK
* s0-t2-env-DEPLOY-FEEDBACK
* s3-t3-poker-DEPLOY-FEEDBACK
* s2-t2-free-DEPLOY-FEEDBACK 
* etc.  

This repo is private.   You will need to:
* grant write access to your team's `-DEPLOY-FEEDBACK` repo to the folks from the other teams in your section that are reviewing your repo
* obtain write access to the other team's repos for each person on your team that is participating in a review.

For example, if your team is `s0-t1-ride-share`, and your team has broken up the other teams in your section as follows:

| Team    | Who is reviewing |
|----------------|------------------|
| s0-t2-covid-19 | Alice, Bob       |
| s0-t3-restaurant-reviews | Chris, Danny |
| s0-t4-dog-sitting | Ellery |

Then Alice and Bob need to ask the `s0-t2-covid-19` team for:
- ask the `s0-t2-covid-19` team for write access to the `s0-t2-covid-19-DEPLOY-FEEDBACK` repo.
- ask the `s0-t2-covid-19` team for read access to the `project-s0-t2-covid-19` repo (if it is not public already)
- find out who on the `s0-t2-covid-19` team is reviewing `s0-t1-ride-share`, and grant them the access they need
  - write access to the `s0-t1-ride-share-DEPLOY-FEEDBACK` repo.
  - read access to the `project-s0-t1-ride-share` repo (if it is not public already)
  

Chris, Danny and Ellery would do likewise for the teams to which they are assigned.

You can make these requests by joining the Slack group of the team for which you are reviewing.  Also monitor your own channel for requests
from other teams to make your repos available.    

To grant access you'll need the github id's of the folks from the other team (which you can obtain
using the `/whois @ScreenName` command on the course Slack.)   

To grant access, you visit the `Settings` Page of the repo, then `Manage Access` (url is `/settings/access`).

# Step 3: Create Stub for your Feedback

To make these instructions concrete: 
* assuming you are Chris and Danny from team `s0-t1-ride-share`
* you have been assigned to provide deploy feedback for team `s0-t3-restaurant-reviews`.

1. Go to the `-DEPLOY-FEEDBACK` repo for the team you are supposed to provide feedback for (e.g. `s0-t3-restaurant-reviews-DEPLOY-FEEDBACK`)
2. Create a file with the name of your own team (e.g. `s0-t1-ride-share.md`) in the root of the repo.  You can just do this directly in the web ui on the master branch.
3. In this file, put the following template (substituting in your name(s) and team name):

   ```
   # Feedback from team s0-t1-ride-share.md

   Review by Chris and Danny
   
   (Review in progress--leave this line here until review is final)
   
   TODO: Insert review here
   
   ```
   
# Step 4: Actually try deploying the app

Each of you should then try deploying the app from the other discussion sections assigned to you.  

If possible, call your Heroku app: `cs48-s20-s0-t2-tries-t1`, where:
* `s0` is your section number (`s0` for noon, `s1` for 1pm, `s2` for 2pm, `s3` for 3pm)
* `t2` is your team's number (which comes before `-tries-`)
* `t1` is the team number of the code your are trying out (which comes after `-tries-`)

You may need to create Auth0 or Google credentials, MongoDB credentials, other API credentials, etc.

As you do, follow the instructions provided in the writeup and/or the video.

As you run into issues and/or problems, document these, and also work with the other team to try to resolve them.

As you edit, leave this line as the top of yoru review until the final step of the lab:

```
   (Review in progress--leave this line here until review is final)
```

# Step 5: Finish your review
 
When you are done, provide a brief writeup in which you provide:

* A link to the running application (or your attempt at bringing up a running application)
* Suggestions for the team on improving their deploy instructions

Then, turn to some comments about the app itself.  Please address the following questions, plus
anything else you think would be helpful for the team that is working on the app:

- What do you like about the app?
- What, if anything, did you find confusing about the app? 
- What bugs did you find (if any?)
- What suggestions do you have for improvements or new features?
- Would you use this app?  Why or why not?

# Step 6: Notify the other team that your review is finished via Slack.

When your review is finished remove the line:

```
(Review in progress--leave this line here until review is final)
```

And replace it with:

```
Review Complete
```

Then notify the team whose deploy instructions and app you were reviewing, via Slack, that your review is complete.

# Grade


* (20 pts) Team has committed `team/DEPLOY.md` in a timely fashion (to divide up the team across other repos in the section)
* (20 pts) Team has provided access to it's own repo and `-DEPLOY-FEEDBACK` repo to members of the other teams in timely fashion.
* (60 pts) (Twenty points each) Team has completed review of the three other teams products, according to instructions, by the deadline for this assignment.

Note: "In a timely fashion" in the items above means "during the lecture or section in which this assignment is made, or within a few hours afterwards"; this is based
on the fact that time will be given during class to complete these tasks.
