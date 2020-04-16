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


# Step 6: Understanding what we are trying to do

### What are we trying to accomplish again in this lab?

-   In this lab, we will <em>set up a basic web app in Java</em>
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

### What are we trying to accomplish again in this lab?

If you just did a deep dive into the article [Web Pages vs. Web Apps](https://ucsb-cs56.github.io/topics/webapps_webapps_vs_websites/) it may be helpful to again review what we are trying to accomplish in this lab:

-   In this lab, we will <em>create a basic "Hello, World" type web app in Java"</em>
-   To test that, we need to run that on a server somewhere.
-   Configuring a web server for Java is challenging. But, fortunately, we don't have to.
-   Heroku.com offers "platform as a service" cloud computing for Java web applications.
    -   We'll use the "free plan" that they offer for folks just getting started with learning Heroku.
    -   This puts your application "on the web", for real, so that anyone in the world can access it 24/7

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

TODO: ADD THIS

Try logging into this app with any Google account you have (e.g. your UCSB Email Account).

You should be able to login, logout.

Once you've complete the steps in this lab, you should be able to:
* Run this app locally
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

So, how to solve this?  There are two ways:

### (1) Use curl 

This is the least satisfying way, because you won't see a proper web page.  You'll only see a dump of the HTML content of the page.  But for a simple 'Hello World' app, this works fine.


The `curl` program is a command line web client (curl stands for "C" the "URL").  For example, this command should show you the output from the `/` route for your webapp.  Run this command at the shell prompt on the CSIL machine to which you are logged in:

```
curl http://localhost:8080
```

A better way, which allows you to see the full web page is to use SSH Tunneling, described next.

### (2) Use SSH Tunneling

In F19, CS56 student Darragh B offered this tip for when you are running your Spring Boot app on CSIL but your browser is on your laptop.    It involves setting up what's called an "SSH Tunnel".

Suppose you are running on port 8080 on host `csil-10.cs.ucsb.edu`

Then you'll type the command: 

```
ssh -L 12345:localhost:8080 username@csil-10.cs.ucsb.edu
```

* If you have Mac or Linux, this should "just work".   
* On Windows, you may need to install [Git For Windows](https://git-scm.com/download/win) and use the `Git Bash Shell` to do this.

What this does is make it so that when you navigate to `http://localhost:12345` on your local browser, it sends the web request and response through an "SSH Tunnel" to port `8080` on `csil-10.cs.ucsb.edu`

Running on `localhost` is fine, but it has some limitations.  That's our next task: to understand those limitations, and why we need a cloud computing platform.



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






# Step 4: Start your webapp on `localhost`



# Step 5: Undertstanding `localhost` vs. Heroku

When running on `localhost`:
* The web app is only runnning as long as your program is executing. 
* As soon as you CTRL/C the program to interrupt it, the web app is no longer available.
* The web app is only available on the machine where you are running the program; not on the public internet.

Running on `localhost` is fine for testing and development.  But eventually we want to know how to deploy a web application so that anyone on the internet can access it.

To get the web app running on the public internet, we'll need to use a cloud-computing platform such as Heroku.
Heroku allows us to deploy web applications in Java rather easily. 

*A side note*: though we won't explore it in this course, Heroku also makes it easy to deploy webapps in *a variety of langauges*, including Python, Node (JavaScript), and Ruby just to name a few.   Many of the skills you'll learn in this course about Heroku will transfer to those other languages if you want to work with them in other courses such as CMPSC 48, CMPSC 189A/B, or personal projects.)

*A note about security*: Let's say up front that this is a risky thing to do.   You need to be very careful about security when deploying web applications to the public internet.  Fortunately, this particular application is rather simple and low-risk.   We'll discuss web security throughout the course.

# Step 6: Create a new Heroku App using the Heroku CLI

In this step, we'll deploy our Spring Boot application to the public internet using Heroku.

Logged into CSIL (or one of the machines in the CSTL, i.e. Phelps 3525), use this command to login to Heroku at the command line:

```
heroku login
```

**NOTES**: 

* If you are ssh'ing in to CSIL, you may need to use `heroku login -i` which allows you to login without having to go to a browser.

* If the `heroku login` command doesn't work, you can instead create the Heroku App at the Heroku Dashboard by
  visiting <https://dashboard.heroku.com/apps>, clicking (at upper right):  "New&nbsp;=>&nbsp;Create New App" and
  then creating an app with the name <tt>heroku create cs56-{{site.qxx}}-<i>githubid</i>-{{page.num}}</tt> as explained in 
  the instructions below.

Then, use this command to create a new web app running on heroku.  Substitute your github id in place of `githubid`.  
Note that you should convert your githubid to all lowercase; heroku web-app names do not permit uppercase letters.

<tt>heroku create cs56-{{site.qxx}}-<i>githubid</i>-{{page.num}}</tt>

Notes:
* A reminder that this is an individual lab, 
  so you should complete it for yourself, i.e. there is only one github id in the name, not a pair of github ids.   
* Please do not literally put the letters <tt><i>githubid</i></tt> 
  in your app name; you are meant to substitute your own github id there.


# Step 7: Login to the Heroku Dashboard

Login to <https://dashboard.heroku.com/apps> and look for the <tt>create cs56-{{site.qxx}}-<i>githubid</i>-{{page.num}}</tt> app that you created.

You should find a place where you can connect your App to Github.  

Click on this, and select your repo to connect the Github Repo to Heroku.

Then, click on "deploy branch".


# What if it doesn't work?

If it doesn't work, try these things before asking a mentor, TA, or instructor for help.

1. Make sure you are logged into Heroku at CLI with `heroku login`.  If you exited your CSIL shell (logged out) and logged back in again, you have to login to Heroku again.  Then repeat the commands.
2. Try, try running `heroku apps`.  Make sure the `<appname>app-name-goes-here</appname>` element in the `heroku-maven-plugin` section of your `pom.xml` matches the name of your heroku app exactly.
3. If it does, try `heroku logs --app appname` (substitute the name of your app where you see `appname`).  You'll see the log output of that app on Heroku.   
   * You may find it helpful to open a second Terminal, login to CSIL and the Heroku CLI, and use `heroku logs --app appname --tail`, which keeps the log output running continously.
   * You can also see your logs in a web browser at: <https://dashboard.heroku.com/apps/app-name/logs> (note that you need to put your `app-name` in the URL instead of `app-name`.  
   * You can navigate to this from <https://dashboard.heroku.com/> by selecting your app, clicking on it,  selecting the `More` menu at upper right, and the selecting `Logs`.


Note:
* If you are using Windows Subsystem Linux (WSL), an error `The environment variable JAVA_HOME is not correctly set.` may appear. If this does occur a temporary fix is this: 
`export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64` 
replace `java-1.11.0-openjdk-amd64` with whatever version of Java you have installed if needed.





