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

# Step 8: Configuration of OAuth

The example repo uses Google OAuth for logins/logouts.  Before we can run the application, we need to do some configuration.



