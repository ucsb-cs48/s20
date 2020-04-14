---
assigned: 2020-04-13 16:00
desc: "Deployment Practice: Spring Boot"
due: 2020-04-17 17:00
layout: lab
num: lab00_sb
ready: false
slack_url: https://ucsb-cs48-s20.slack.com
gauchospace_url: https://gauchospace.ucsb.edu/courses/mod/assign/view.php?id=3766298&forceview=1
---

This page describes detailed steps for completing lab00 using Spring Boot.

Please complete Steps 1-5 on the [lab00]({{'/lab/lab00' | relative_url }}) page first.

# Step 6: Add remote for starter code

If you followed Step 1-5 [lab00]({{'/lab/lab00' | relative_url }}), you should now be at a terminal prompt, and your 
current directory should be the repo you created for lab00, with a name such as `cgaucho_lab00`.

The next step is to add a git *remote* for your starter code.

* If you already know how this works, you can just type the command and skip the explanation below
* If you have not worked with remotes before, please read this explanation carefully.

```
git remote add starter https://github.com/ucsb-cs48-s20/demo-spring-google-oauth-app
```

## Explanation of the `git remote` command

If you know the command `git push origin master`, in this command:
* `origin` is a remote
* `master` is a branch

A remote refers to the location of a repository other than the current local repository (the one on your local filesystem.)  By convention, when you `git clone` a repository, it creates a remote called `origin` that points back to where you cloned the repo from.   

We are going to add another remote for the starter code.  You'll only pull from this remote once; you won't have permission to push to it.

# Step 7: Pull remote into local repo

Now, we are going to pull from the starter code remote into the local repo, and then push to the origin repo

```
git pull starter master
git push origin master
```

At this point, you should be able to visit the github organization (<https://github.com/{{page.github_org}}>) and see your repo listed as one of the private repos to which you have access (you won't see it unless you are logged in to your github account.)    You should also see that it has all of the files from the starter repo.


# Step 8: See example of completed app

The example app here shows what the app looks like when it is fully deployed on the web.

TODO: ADD THIS

Try logging into this app with any Google account you have (e.g. your UCSB Email Account).

You should be able to login, logout.

Once you've complete the steps in this lab, you should be able to:
* Run this app locally
* Deploy this app to the web at the address <https://cs48-cgaucho-lab00.herokuapp.com> (where `cgaucho` is replaced with your githubid).

Now that we know what we are trying to accomplish, let's proceed.


# Step 9: Install Java 11 and Maven on your machine

If you are working on CSIL, you may skip this step, because as of this writing (April 12, 2020), Java 11 and Maven are both installed on CSIL.


Otherwise, follow the instructions here for installing Java 11 and Maven

TODO: Insert these instructions

# Step 10: Type `mvn compile` to try compiling the app

TODO: Add explanation  
 
# Step 11: Explanation of "running on `localhost`"

Running on `localhost` is also known as *development mode*

If you know what is meant by "running on `localhost'" you can skip the following explanation, and go straight to the next step.

Running on `localhost` means that 
* we are running the server on our local machine
* it can *only* be accessed from web browsers running on that local machine

Running on localhost is convenient for testing code as we develop; it is not the way we make the web app available to real users.

For Spring Boot apps, running on localhost typically means we interact with the running web app by pointing our browser to <http://localhost:8080>, however:
* The *local machine* in this case might be our own laptop or desktop machine, or it might be CSIL.  
* If it's your laptop or desktop, It depends on where you are working.  If the *local machine* is CSIL, you'll need to use SSH forwarding to be able to see your running app.  Consult <https://ucsb-cs48.github.io/topics/csil_ssh_port_forwarding/> for details.

# Step 12: Configuration of OAuth for Localhost

The example repo uses Google OAuth for logins/logouts.  Before we can run the application on localhost, we need to do some configuration.

TODO: Add explanation here

# Step 13: Test application on localhost

The instructions for running are in the README.md file of the starter repo, which you can read here: <https://github.com/ucsb-cs48-s20/demo-nextjs-app/blob/master/README.md>

The basic command is `mvn spring-boot:run`

Start up your server and verify that you can interact with it on `localhost:8080` in the same ways you interacted with the sample implementation at <https://cs48-btk5h-demo-nextjs-app.now.sh/>

TODO: ADD EXPLANATION OF CONFIGURING ADMINS

If it works, proceed to the next step.

# Step 14: Understanding GitHub Actions


TODO: REWRITE THIS TO MAKE SENSE FOR SPRING BOOT APP

At this point, if you look at your GitHub repo, you'll probably see that there
is an red X next to the commit hash on the main page, as shown in the
image below.

![red x full context](red-x-full-context_50pct.png)

The red x signifies that GitHub Action is trying to run test cases
for this repo, but the test cases are failing.  This is likely because
the secrets necessary for GitHub Actions to succeed have not
yet been configured.

The next step in the README.md describes how to configure secrets for GitHub actions.   Follow these steps.

Then make a commit to the README.md of your own repo, in which you add your name, github id, and team to the top of the 
README.   You can do this directly in the GitHub web interface.  Here's what
that would look like:

![add name to README](add-name-to-README_50pct.png)


That commit should trigger GitHub actions to run, which should result in first a yellow circle, then a green check next to your commit hash.

Yellow dot (signfying tests are still running):

![yellow dot](yellow-dot_50pct.png)

Green check signfifying tests are passing:

![green check](green-check-full-context_50pct.png)


After doing this commit, if you get the green check, do this to pull these change to the README.md into your local repo:

```
git pull origin master
```

# Step 15: Configure application to run on Heroku

In this step, we put the application online on the public web, using a service known as Heroku

We will also refer to this as "running in production", since it is a public facing version of our running code, running 24/7 on a web server in the cloud.

The instructions for doing this are in the {{page.README_link}} for the starter code.  Follow those instructions, including
the adjustments needed to configure Google OAuth for production.

# Step 16: Submit on Gauchospace

TODO: Put instructions for submitting on Gauchospace here.



