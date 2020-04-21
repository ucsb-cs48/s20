---
assigned: 2020-04-21 16:00
desc: First Production Deployment
due: 2020-04-24 17:59
layout: lab
num: lab01
ready: false
slack_url: https://ucsb-cs48-s20.slack.com
github_org: ucsb-cs48-s20
gauchospace: https://gauchospace.ucsb.edu/courses/mod/assign/view.php?id=3821278&forceview=1
---

In this group lab, your entire team will collaborate on making a production deployment
of your CS48 web app.

The production deployment is the one that should always be running the latest
version of the `master` branch of your repo.

You should NOT do development on the `master` branch going forward, but instead
should use a "feature branch / Pull Request" workflow (we'll discuss this in lecture).


# Step 1: Create Heroku Account (every team member)

Every member of the team will need a Heroku Account.

If you don't have a Heroku Account yet, please create a Heroku account by
logging in at <https://heroku.com>

Click the “Sign up for Free” link.

You’ll be asked for:

- First Name, Last Name
- Email (we suggest using your `@ucsb.edu` email, but that's up to you)
- Company (you may leave this blank).
- Preferred Development Language: choose JavaScript or Java

  Don’t worry; your choice doesn’t prevent you from using the
  account with other languages later such as Ruby or Python

**NOTE for folks with existing Heroku Accounts**: If you already have a Heroku account
on the free tier from CS56, you might need to delete old apps to make space for new ones.   There is a limit of
five apps on the free tier of Heroku (unless/until you enter a credit card.)


# Step 2: Install Heroku CLI (every team member)

CLI stands for Command Line Interface.  The Heroku CLI gives you the ability to
type `heroku` as a command at the shell/terminal prompt.

If you haven't already done so, install the Heroku CLI on your system
(it's already installed on CSIL).

Instructions are here: <https://devcenter.heroku.com/articles/heroku-cli>

# Step 3: Create Heroku App (one team member)

One member of the team should:

* share their screen
* login to the Heroku Dashboard <https://dashboard.heroku.com>
* create a new Heroku app called, for example: `cs48-s20-s0-t0-prod`

  Substitute in for `s0-t0` the section and team number of your team.
  
  PLEASE use exactly this name; for purposes of keeping track for grading
  and evaluation purposes, it makes it MUCH easier if there is a consistent
  naming convention.

  You may also optionally create another deployment under any name you like
  if you want to show off the app to real users (e.g. `our-cool-app`)
  but the one we'll grade is the one with the `cs48-s20-s0-t0.herokuapp.com` URL.

* Create another new Heroku app called, for example: `cs48-s20-s0-t0-qa`
  substituting the `s0-t0` as you did before.   We won't set this one up yet,
  but want to reserve the name for later.

# Step 4: Add Collaboarators to prod (one team member)

Now go back to the `cs48-s20-s0-t0-prod` app.

Go to the "Access" tab.

Add each member of your team by the email address they use to login to
Heroku.

Then additionally, add these emails as collaborators:
* `phtcon@ucsb.edu` (instructor)
* `tehchowster@gmail.com` (TA)

You may, from time-to-time, also find it helpful to add one or more of the LAs as
collaborators if you are asking for help with debugging an application problem.
This gives us visibility to the logs as well as the values of the "Config Vars",
each of which is helpful in debugging.

# Step 5: Add collaborators to qa (two team members)

The person that created the qa app should now
* Add *one* team member as a collaborator on the qa app
* Ask that team member to add everyone else on the team to the qa app as a
  collborator (they can open two tabs: one to prod and one to qa, just copy/paste
  the emails one at a time.)


# Step 6: Deploy App (another team member)

Now pivot to another team member; not the one that did steps 3,4 or the
second half of step 5).

This team member should share their screen and then:

* Navigate to the <https://dashboard.heroku.com>
* Bring up your production app (e.g. "cs48-s20-s0-t0-prod")
* Navigate to the `Deploy` tab
* Under `Deployment Method`, select `GitHub`
* To select your repo, type in `ucsb-cs48-s20` for the owner, and then
  any substring of your team's repo name (e.g. `project-t0-s0`), and click search.
* Click to link your repo to the production app
* Go down to "Automatic Deploys" and set up your repo to deploy the master branch
  automatically.

The next step depends on where you are in the process of building your app.

* If you already have a working Spring Boot or next.js app in your team's repo,
  skip Step 7.
  - If your app requires OAuth configuration, skip to Step 8
  - If it does NOT require OAuth configuration, skip to Step 9
  
* If you do NOT have a working Spring Boot or next.js app in yoru team's repo,
  then you should at this stage, discuss as a team what your starting point code
  should be.

  We recommend, if you don't have a good reason to do otherwise, that you start
  with the code in one of:

  * next.js: <https://github.com/ucsb-cs48-s20/demo-nextjs-app>
  * spring boot: <https://github.com/ucsb-cs48-s20/demo-spring-google-oauth-app>

  We'll walk you through that process in Step 7.


# Step 7: Establish a starting point for your app

If you don't yet have *any* code for the starting point for your app, here is a way
to get started quickly.

* Clone your repo into a local repo and `cd` into that redirectory
  - or just `cd` into a directory where you've already cloned it
* `git checkout master`
* `git pull origin master`
*  <tt>git remote add demo <i>url-of-demo-repo</i></tt>
   - where <tt><i>url-of-demo-repo</i></tt> is the url of the demo repo you are
     basing your code on.
* `git pull demo master --allow-unrelated-histories`
  - The `--allow-unrelated-histories` is necessary since your repo and the
    demo repo likely have no common ancestors.
  - This will likely result in some merge conflicts in files such as `README.md`, but
    they should be easy to fix.
* Resolve the merge conflicts:
  - `git status` will list the files with conflicts
  - For each one, fix it and add it to a new commit
  - Make a new commit when all merge conflicts are fixed
* Try testing locally on localhost according to the instructions appropriate to your
  platform.
* When your app is working on localhost, do a `git push origin master`
* You are now ready to try to get the app working on production.

Now, it depends on whether your app requires OAuth.
* If your app requires OAuth, proceed to Step 8
* If your app currently does NOT require OAuth, proceed to Step 9


# Step 8: Configure OAuth on Production

At this point, you may need to do additional configuration, depending on your 
tech stack to get the app to come up.

(Note: If your minimum viable product does not require OAuth, then this step
might not be necessary.)

* On next.js
  * Add the Heroku Production url to the list of URIs in the Auth0 app
	
* On Spring Boot:
  * Add the Heroku Production url to the list of URIs in the Google OAuth App

Then, proceed to Step 9 to update the Config Vars.

# Step 9: Update Config Vars

At this point, you may need to do additional configuration, depending on your 
tech stack to get the app to come up.

* On next.js
  * Add a `SESSION_COOKIE_SECRET` value, as explained in the documentation
    for [demo-nextjs-app](https://github.com/ucsb-cs48-s20/demo-nextjs-app/blob/master/README.md)
  * Run `npx heroku-dotenv push --app cs48-s20-t0-s0-prod` to copy the values in your
    `.env` file into the Heroku Config Vars.
  * Redeploy your app from the master branch
    (note that changig config vars should do this automatically)
	
* On Spring Boot:
  * Run `./setHerokuEnv.sh --app cs48-s20-t0-s0-prod`
  * Redeploy your app from the master branch
    (note that changig config vars should do this automatically)

# Step 10: Your app should now work!

At this point, you shoudl have a working production app.

Visit the apps URL in this table to see if it works.

If it doesn't, then work as a team to resolve the problem.

|team|production|
|----|----------|
|s0-t1-budget|<https://cs48-s20-s0-t1-prod.herokuapp.com>|
|s0-t2-env|<https://cs48-s20-s0-t2-prod.herokuapp.com>|
|s0-t3-iv-housing|<https://cs48-s20-s0-t3-prod.herokuapp.com>|
|s0-t4-new-city|<https://cs48-s20-s0-t4-prod.herokuapp.com>|
|s1-t1-music-queue|<https://cs48-s20-s1-t1-prod.herokuapp.com>|
|s1-t2-music-queue|<https://cs48-s20-s1-t2-prod.herokuapp.com>|
|s1-t3-expense|<https://cs48-s20-s1-t3-prod.herokuapp.com>|
|s1-t4-missile|<https://cs48-s20-s1-t4-prod.herokuapp.com>|
|s2-t1-care|<https://cs48-s20-s2-t1-prod.herokuapp.com>|
|s2-t2-free|<https://cs48-s20-s2-t2-prod.herokuapp.com>|
|s2-t3-slack-bot|<https://cs48-s20-s2-t3-prod.herokuapp.com>|
|s2-t4-mafia|<https://cs48-s20-s2-t4-prod.herokuapp.com>|
|s3-t1-accountant|<https://cs48-s20-s3-t1-prod.herokuapp.com>|
|s3-t2-meal-plan|<https://cs48-s20-s3-t2-prod.herokuapp.com>|
|s3-t3-poker|<https://cs48-s20-s3-t3-prod.herokuapp.com>|
|s3-t4-textbooks|<https://cs48-s20-s3-t4-prod.herokuapp.com>|
{:.table .table-sm .table-striped .table-bordered}

# Step 11: Set up the QA app as well

Now repeat these steps so that the QA app also works.

You'll be able to use the QA app to deploy other branches of your app
before accepting pull requests to the master branch.

|team|qa|
|----|----|
|s0-t1-budget|<https://cs48-s20-s0-t1-budget-qa.herokuapp.com>|
|s0-t2-env|<https://cs48-s20-s0-t2-env-qa.herokuapp.com>|
|s0-t3-iv-housing|<https://cs48-s20-s0-t3-iv-housing-qa.herokuapp.com>|
|s0-t4-new-city|<https://cs48-s20-s0-t4-new-city-qa.herokuapp.com>|
|s1-t1-music-queue|<https://cs48-s20-s1-t1-music-queue-qa.herokuapp.com>|
|s1-t2-music-queue|<https://cs48-s20-s1-t2-music-queue-qa.herokuapp.com>|
|s1-t3-expense|<https://cs48-s20-s1-t3-expense-qa.herokuapp.com>|
|s1-t4-missile|<https://cs48-s20-s1-t4-missile-qa.herokuapp.com>|
|s2-t1-care|<https://cs48-s20-s2-t1-care-qa.herokuapp.com>|
|s2-t2-free|<https://cs48-s20-s2-t2-free-qa.herokuapp.com>|
|s2-t3-slack-bot|<https://cs48-s20-s2-t3-slack-bot-qa.herokuapp.com>|
|s2-t4-mafia|<https://cs48-s20-s2-t4-mafia-qa.herokuapp.com>|
|s3-t1-accountant|<https://cs48-s20-s3-t1-accountant-qa.herokuapp.com>|
|s3-t2-meal-plan|<https://cs48-s20-s3-t2-meal-plan-qa.herokuapp.com>|
|s3-t3-poker|<https://cs48-s20-s3-t3-poker-qa.herokuapp.com>|
|s3-t4-textbooks|<https://cs48-s20-s3-t4-textbooks-qa.herokuapp.com>|

# Step 12: Submit on Gauchospace

Submission on Gauchospace is *per group*

You should be assigned on Gauchospace to a group that matches your project group.

If you are not, please contact the instructor.

Only one submission per group is needed, but each group member is responsible to make
sure that a submission for the group has been made.

I recommend taking a screen shot of the submission and posting it to the group's slack
channel so that everyone can be confident that it was done.

To submit, visit: <{{page.gauchospace}}>
