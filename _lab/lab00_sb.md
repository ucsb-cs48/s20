---
assigned: 2020-04-13 16:00
desc: "Deployment Practice: Spring Boot"
due: 2020-04-22 23:59
layout: lab
num: lab00_sb
ready: false
slack_url: https://ucsb-cs48-s20.slack.com
gauchospace_url: https://gauchospace.ucsb.edu/courses/mod/assign/view.php?id=3766298&forceview=1
---

This page describes detailed steps for completing lab00 using Spring Boot.

Please complete Steps 1-5 on the [lab00]({{'/lab/lab00' | relative_url }}) page first.


# Step 6: Understanding what we are trying to do

### What are we trying to accomplish again in this lab?

-   In this lab, we will <em>set up a basic web app writting in Java</em> to run on Heroku.
-   A web app is a piece of Java code that takes HTTP request messages as input, and responds with HTTP response objects as output.
-   Our app is written using the Spring Boot framework, a Java framework for writing web apps
-   Heroku is a platform where we can host a Java web app.

### Why use Heroku?

-   Web applications run on the "server" side of the web architecture, not the client side.
-   So to test a web application, we need to set up a web server that can run Java code.
-   Configuring a web server for Java is challenging. But, fortunately, we don't have to.
-   Heroku.com offers "platform as a service" cloud computing for Java web applications.
-   We'll use the "free plan" that they offer for folks just getting started with learning Heroku.
-   This puts your application "on the web", for real, so that anyone in the world can access it 24/7

### Limitations of the free plan of Heroku

TL;DR: You should NOT need to enter a credit card into Heroku.  If you are asked for one, something has gone wrong.

-   If no-one has accessed your web app for a while, it "goes to sleep", so to speak.
    -   The first time someone tries to access it after it has gone to sleep, there is a <em>noticable</em> delay in the response, perhaps several seconds or even up to a minute.
-   If too many people try to access your service per hour, eventually, you'll run out of "free resources".
    -   That is <em>very unlikely to happen</em> unless you make a web app that somehow attracts the attention of a very large audience.
    -   I suggest you try to avoid doing that with the web apps you develop for this class.
    -   I suggest you avoid doing that in general, unless/until you have some plan for how to make money off your web app to pay for the server resources. (With a credit card, you can set up Heroku to have higher usage limits, and to keep your app running so that response time is fast. But you should NOT need that for this course.)


### Web Apps vs. Static Web Pages

You may already have some experience with creating static web pages, and/or with creating web applications (e.g. using PHP, Python (Django or Flask) or Ruby on Rails.) If so, then the "Learn More" section will be basic review.

If you are new to writing software for the web, you are <em>strongly encouaged</em> to read the background information at the "learn more" link below.
-   [Web Pages vs. Web Apps](https://ucsb-cs56.github.io/topics/webapps_webapps_vs_websites/)


### Disk Quota

IMPORTANT: if you are working on CSIL, and at some point things just "stop working":

-   You get odd error messages, especially "cannot write file", or "disk quota exceeded"
-   You cannot log in---it takes your user name and password on the machines in Phelps 3525 or CSIL, but then just logs you out immediately.

Then you probably have a disk quota problem.

-   The best way to troubleshoot this, if you cannot log in, is to ask someone else that CAN log in to allow you to use a terminal window on their screen.
    -   Use `ssh yourusername@csil.cs.ucsb.edu` to get into your account from their terminal session.
-   For troubleshooting tips, visit: [CSIL Disk Quota Troubleshooting](https://ucsb-cs56.github.io/topics/csil_disk_quota/)

# Step 7: Create a Heroku Account

If you do not already have a Heroku account, navigate to <https://www.heroku.com/> and click the "Sign up for Free" link.

You'll be asked for:

-   First Name
-   Last Name
-   Email (you may use any email address you like)
-   Company (you may leave this blank).
-   Preferred Development Language: We suggest you select "Java" if you are currently enrolled in CMPSC 56
    -   (Don't worry; this doesn't prevent you from using the account with other languages later.)

# Step 8: Add remote for starter code

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

# Step 9: Pull remote into local repo

Now, we are going to pull from the starter code remote into the local repo, and then push to the origin repo

```
git pull starter master
git push origin master
```

At this point, you should be able to visit the github organization (<https://github.com/{{page.github_org}}>) and see your repo listed as one of the private repos to which you have access (you won't see it unless you are logged in to your github account.)    You should also see that it has all of the files from the starter repo.


# Step 10: See example of completed app

The example app here shows what the app looks like when it is fully deployed on the web.

* <https://demo-spring-google-oauth-app.herokuapp.com/>

Try logging into this app with any Google account you have (e.g. your UCSB Email Account).

You should be able to login, logout.   You won't be able to see the admin features, because you aren't an admin, but
if you want to try those out, ask either the instructor or the TA to add you as an admin.

Once you've complete the steps in this lab, you should be able to:
* Run this app locally (including making yourself an admin)
* Deploy this app to the web at the address <https://cs48-cgaucho-lab00.herokuapp.com> (where `cgaucho` is replaced with your githubid).

Now that we know what we are trying to accomplish, let's proceed.

# Step 11: Install Java 11 and Maven on your machine

If you are working on CSIL, you may skip this step, because as of this writing (April 12, 2020), Java 11 and Maven are both installed on CSIL.


Otherwise, follow the instructions here for installing Java 11 and Maven

* Make sure you have Java 11
   * Install instructions for Mac OS: <https://ucsb-cs56.github.io/topics/macos/>
   * For Windows, see:  <https://ucsb-cs56.github.io/topics/windows/>
   
* Install Maven.  Instructions are here: <https://maven.apache.org/index.html>
   * If you are a Mac user, try to install Maven using Homebrew. <https://ucsb-cs56.github.io/topics/macos/>
		  Type "brew install maven" in your Terminal. (Check if your mac have Homebrew installed firstly)
		  
* Install the Heroku CLI.  Instructions are here: <https://devcenter.heroku.com/articles/heroku-cli#download-and-install>


# Special note for Windows Subsystem for Linux (WSL)

If you are using Windows Subsystem Linux (WSL), an error `The environment variable JAVA_HOME is not correctly set` may appear when you try to use Java tools. If this does occur a temporary fix is this: 

* Type `export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64` 
  - Replace `java-1.11.0-openjdk-amd64` with whatever version of Java you have installed if needed.


# Step 12: Type `mvn compile` to try compiling the app

We will use Maven (the `mvn` command) to work with Spring Boot.

Type `mvn compile` to try compiling the app.

For a crash course in Maven, read this: <https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html>

 
# Step 13: Explanation of "running on `localhost`"

Running on `localhost` is also known as *development mode*

If you know what is meant by "running on `localhost'" you can skip the following explanation, and go straight to the next step.

Running on `localhost` means that 
* we are running the server on our local machine
* it can *only* be accessed from web browsers running on that local machine

Running on localhost is convenient for testing code as we develop; it is not the way we make the web app available to real users.

For Spring Boot apps, running on localhost typically means we interact with the running web app by pointing our browser to <http://localhost:8080>, however:
* The *local machine* in this case might be our own laptop or desktop machine, or it might be CSIL.  
* If it's your laptop or desktop, It depends on where you are working.  If the *local machine* is CSIL, you'll need to use SSH forwarding to be able to see your running app.  Consult <https://ucsb-cs48.github.io/topics/csil_ssh_port_forwarding/> for details.


Assuming you are working on CSIL, you can use `mvn` to run Maven.

* If you are working on your own machine, you'll need to install Maven on your machine.
* We've collected [advice on how to do that here](https://ucsb-cs56-pconrad.github.io/topics/maven_installing/).

Use `mvn compile` and `mvn spring-boot:run` to try to run the code and get a web app running on `localhost`.

Note that in order to see this web app running, you'll need to be in a web browser on the same host that you are running your program on.  
* For example, if you are running on `csil-04.cs.ucsb.edu`, you'll need to be running your web browser on `csil-04.cs.ucsb.edu`.   
* If you are working in Phelps 3525 on `cstl-07.cs.ucsb.edu`, you'll need to be running your web browser on `cstl-07.cs.ucsb.edu`.


## About `localhost` and "Port Numbers"

The code in this repo is configured to start up a webserver on port 8080, running on `localhost`, which is a name for the machine on which the code is running.  

* If you are running the code on a Phelps 3526 or CSIL machine, either because you are sitting in Phelps 3526, or sitting in CSIL, or 
  even if it is because you ssh'd into a CSIL machine from your laptop, then `localhost` refers to that CSIL machine.
* The port number is a more specific "communications channel" on that machine.   You can find more information on port numbers
  at this short article, which you are encouraged to read if you are not already familiar with port numbers
  (or, for that matter, even if you are): <https://ucsb-cs56.github.io/topics/port_numbers/>
  
So the web address to acccess your server is: `http://localhost:8080`.

* Note: You should use `http` not `https` when running on `localhost`. Using `http` is the unsecure, unencrypted version.   
* It is possible to set up Spring Boot to run `https` (the secure, encrypted version), but it's complicated and typically
  unnecessary; Heroku sets up `https` for us automatically, so we really don't need to deal with those steps most of the time.

## What if I get `port already in use`

The error `port already in use` signifies that someone else on the same system (perhaps you, in another window?) is already using
the port you are trying to use.

In this case:
* If it's you, shut down the server in the other window.
* It it's not you, then you are probably ssh'd into CSIL, say `csil-14.cs.ucsb.edu`, and someone else is logged into the same machine,
  doing the same assignment as you.  Therefore, they already grabbed that port number.
* In that case, maybe:
  * Try a different machine, say `csil-15.cs.ucsb.edu` OR
  * Type `export PORT=8082` before running `mvn spring-boot:run`.  That should start your server on port 8082 instead of 8080.
  * In that case, you'll need to change `http://localhost:8080` to `http://localhost:8082` of course.
  
## How do I access `http://localhost:8080` on CSIL from my laptop?

Suppose you are running your Spring Boot application on `localhost:8080` on one of the CSIL 
machines.

You normally *will not* be able to access that application from any browser that is NOT directly
running on that CSIL machine.

If you are ssh'ing into CSIL on your laptop (e.g. using `ssh` in a terminal session, or using an app such as `PuTTY` or `MobaXTerm` on Windows) keep in mind that if you direct your browser (running on your laptop) to `localhost:8080`, that request *never leaves your laptop*.  It looks for a web app running *on your laptop*.

# Using ssh tunnelling

To solve this you can use *ssh tunneling*.  Here's how it works.

Suppose you are running on port 8080 on host `csil-10.cs.ucsb.edu`

Then you'll type the command: 

```
ssh -L 12345:localhost:8080 username@csil-10.cs.ucsb.edu
```

* If you have Mac or Linux, this should "just work".   
* On Windows, you may need to install [Git For Windows](https://git-scm.com/download/win) and use the `Git Bash Shell` to do this.

What this does is make it so that when you navigate to `http://localhost:12345` on your local browser, it sends the web request and response through an "SSH Tunnel" to port `8080` on `csil-10.cs.ucsb.edu`

Running on `localhost` is fine, but it has some limitations.  That's our next task: to understand those limitations, and why we need a cloud computing platform.


# Step 14: Configuration of OAuth for Localhost

The example repo uses Google OAuth for logins/logouts.  Before we can run the application on localhost, we need to do some configuration.

This configuration is explained here: <https://ucsb-cs48.github.io/topics/oauth_google_setup/>

# Step 15: Test application on localhost

The instructions for running are in the README.md file of the starter repo, which you can read here: <https://github.com/ucsb-cs48-s20/demo-spring-google-oauth-app/blob/master/README.md>

The basic command is `mvn spring-boot:run`

Start up your server and verify that you can interact with it on `localhost:8080` in the same ways you interacted with the sample implementation at <https://demo-spring-google-oauth-app.herokuapp.com/>

At first, you won't able to access the admin functions.  We'll fix that in the next step

# Step 16: Test application **as an admin** on localhost

Now, let's configure yourself as an admin, and run the app again.

The admins for the sample code are configured in a file called `src/main/resources/application.properties`.

If you open up that file, you'll see that it contains this line:

```
app.admin.emails=phtcon@ucsb.edu,scottpchow@ucsb.edu
```

There are two ways to add yourself as an admin:

1. Add your email (any Gmail account) to the end of this comma separated list.
2. Override this property value in either your `secrets-localhost.properties` or `secrets-heroku.properties` file, or both.

Essentially, any property defined in `application.properties` can be overridden for `localhost` or for `heroku` by specifying
a new value in `secrets-localhost.properties` or `secrets-heroku.properties`

* New values in `secrets-localhost.properties` take effect immediately when you restart the server with `mvn spring-boot:run`
* New values in `secrets-heroku.properties` take effect when you:
  - Rerun `./setHerokuEnv.sh --app appname` (where `appname` is the name of your Heroku app, e.g. `cs48-s20-cgaucho-lab00`)
  - Redeploy the app

Make this change (whichever way you prefer), and then see if you can access the admin features of the application. You should
see a menu for Users and one for Admins.

If it works, proceed to the next step.

# Step 17: Understanding GitHub Actions


At this point, if you look at your GitHub repo, you'll probably see that there
is an green check next to the commit hash on the main page.

The green check signifies that GitHub Action is running test cases on your repo and they are passing.

After each commit it pushed, this first be a yellow circle, indcating that the tests are still running.
It should then change to a green check.

If, instead, you see a red X, then something is wrong with the tests.   In this case, ask for help; that shouldn't be
happening for this simple "getting started" lab.


# Step 18: Configure application to run on Heroku

In this step, we put the application online on the public web, using a service known as Heroku

We will also refer to this as "running in production", since it is a public facing version of our running code, running 24/7 on a web server in the cloud.

Login to <https://dashboard.heroku.com/apps> and click to create a new Heroku App.  

Call it  <tt>create cs56-{{site.qxx}}-<i>githubid</i>-{{page.num}}</tt> 
* If that name is too long or prohibited because your githubid is too long, you may abbreviate.

Then go to the Deploy tab.   You should find a place where you can connect your App to Github.  

Click on this, and select your repo to connect the Github Repo to Heroku.

Then, click on "deploy branch".

You should see a log of the deployment in the screen.  When it is finished, there will be an "Open App" button where you can open up the URL for your app.

Note that while the app may come up, Google OAuth may not work immediately.  To get it to work, you may need to do some additional configuration.    That involves adding the address of your Heroku app as an additional redirect URI for your Google OAuth app.

That step is explained here: <https://ucsb-cs48.github.io/topics/oauth_google_setup/>

# Troubleshooting

If it doesn't work, try these things before asking a mentor, TA, or instructor for help.

1. Make sure you are logged into Heroku at CLI with `heroku login`.  
2. Try running `heroku apps`, and make sure your app shows up.
3. If it does, try `heroku logs --app appname` (substitute the name of your app where you see `appname`).  You'll see the log output of that app on Heroku.   
   * You may find it helpful to open a second Terminal, login to CSIL and the Heroku CLI, and use `heroku logs --app appname --tail`, which keeps the log output running continously.
   * You can also see your logs in a web browser at: <https://dashboard.heroku.com/apps/app-name/logs> (note that you need to put your `app-name` in the URL instead of `app-name`.  
   * You can navigate to this from <https://dashboard.heroku.com/> by selecting your app, clicking on it,  selecting the `More` menu at upper right, and the selecting `Logs`.

The instructions for doing this are in the {{page.README_link}} for the starter code.  Follow those instructions, including
the adjustments needed to configure Google OAuth for production.

## Explanation of localhost vs. Heroku


If you are new to running on Heroku, you may also want to read the following explanation.  If you are familiar with Heroku, you may skip it.

When running on `localhost`:
* The web app is only runnning as long as your program is executing. 
* As soon as you CTRL/C the program to interrupt it, the web app is no longer available.
* The web app is only available on the machine where you are running the program; not on the public internet.

Running on `localhost` is fine for testing and development.  But eventually we want to know how to deploy a web application so that anyone on the internet can access it.

To get the web app running on the public internet, we'll need to use a cloud-computing platform such as Heroku.
Heroku allows us to deploy web applications in Java rather easily. 

*A side note*: though we won't explore it in this course, Heroku also makes it easy to deploy webapps in *a variety of langauges*, including Python, Node (JavaScript), and Ruby just to name a few.   Many of the skills you'll learn in this course about Heroku will transfer to those other languages if you want to work with them in other courses such as CMPSC 48, CMPSC 189A/B, or personal projects.)

*A note about security*: Let's say up front that this is a risky thing to do.   You need to be very careful about security when deploying web applications to the public internet.  Fortunately, this particular application is rather simple and low-risk.   We'll discuss web security throughout the course.


# Step 19: Submit on Gauchospace


When you have a running web app, visit <{{page.gauchospace_url}}> and make a submission.

In the text area, enter something like this, substituting your repo name and your Heroku app name:

<div style="font-family:monospace;">
repo name: https://github.com/ucsb-cs48-s20/cgaucho_lab00<br>
on now.sh: https://cs48-cgaucho0-lab00.now.sh<br>
</div>

Then, **and this is super important**, please make both of those URLs **clickable urls**.

The instructions for doing so are here: <https://ucsb-cs48.github.io/topics/gauchospace_clickable_urls/>

# Grading Rubric:

TBA.  It will be 100 points divided across the  steps in the lab.

