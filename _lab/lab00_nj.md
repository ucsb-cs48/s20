---
assigned: 2020-04-13 16:00
desc: "Deployment Practice: Next.js"
due: 2020-04-17 17:00
layout: lab
num: lab00_nj
ready: false
github_org: ucsb-cs48-s20
slack_url: https://ucsb-cs48-s20.slack.com
---

This page describes detailed steps for completing lab00 using Next.js.

Please complete Steps 1-5 on the [lab00]({{'/lab/lab00' | relative_url }}) page first.

# Step 6: Add remote for starter code

If you followed Step 1-5 [lab00]({{'/lab/lab00' | relative_url }}), you should now be at a terminal prompt, and your 
current directory should be the repo you created for lab00, with a name such as `cgaucho_lab00`.

The next step is to add a git *remote* for your starter code.

* If you already know how this works, you can just type the command and skip the explanation below
* If you have not worked with remotes before, please read this explanation carefully.

```
git remote add starter https://github.com/ucsb-cs48-s20/demo-nextjs-app.git
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

* <https://cs48-btk5h-demo-nextjs-app.now.sh/>

Try logging into this app with any Google account you have (e.g. your UCSB Email Account).

You should be able to login, logout, and show a picture of a random dog.

* Note that the menu item "Random Dog With Auth" appears only when you are logged in.
* If you log out and try to access the same URL to which that menu item takes you, i.e. <https://cs48-btk5h-demo-nextjs-app.now.sh/woof-private>, the app will force you back to the login screen before it allows you to see the random dog.

Once you've complete the steps in this lab, you should be able to:
* Run this app locally
* Deploy this app to the web at the address <https://cs48-cgaucho-lab00.now.sh> (where `cgaucho` is replaced with your githubid).

Now that we know what we are trying to accomplish, let's proceed.


# Step 9: Install node

If you are working on CSIL, you may skip this step, because as of this writing (April 12, 2020), a sufficient version of node is installed on CSIL:

```
[pconrad@csil-05 ~]$ node --version
v10.16.3
[pconrad@csil-05 ~]$ 
```

You may also skip this step if, when you type the command `node --version` on your local system. you see a version that is `10.*` or higher.

Otherwise, follow the instructions here for installing node:

Additional installation advice for specific platforms can be found here:
* MacOS: <https://ucsb-cs48.github.io/jstopics/node_macos/>
* Windows: <https://ucsb-cs48.github.io/jstopics/node_windows/>
* Linux: <https://ucsb-cs48.github.io/jstopics/node_linux/>

When you have finished with those instructions, you should be able to do each of these at the terminal prompt:
* type `node --version` and get a number that is `10.*` or higher (e.g. `v10.16.3`)
* type `npm --version` and get a version number (as opposed to `command not found`)
* type `npx --version` and get a version number (as opposed to `command not found`)


# Step 10: Configuration of OAuth

The example repo uses Google OAuth for logins/logouts.  Before we can run the application, we need to do some configuration.

The instructions for doing this configuration are in the README.md file of the starter repo, which you can read either:
* online here: <https://github.com/ucsb-cs48-s20/demo-nextjs-app/blob/master/README.md>
* in the `README.md` of your local copy of the repo 


