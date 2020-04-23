---
desc: "Thursday Lecture: feature-branch/pull request workflow"
lecture_date: 2020-04-21
num: lect11
ready: false
---


# Feature Branch / Pull Request Workflow

When making a change to your team's repo, you should typically NOT be making changes on the `master` branch

* At many companies, the `master` branch is a "protected" branch.
* There is "process and ceremony" around when/where changes to `master` are pushed.
  * Things have to have to be done first
  * Sometimes only certain members of the team do it
 
Reasonable exceptions: small changes to documentation only (not touching code).

# So what do you do instead?

* Make a feature branch
* Work on the feature branch
* When done, make a Pull Request

# How do you make a feature branch?

```
git checkout master
git pull origin master
git checkout -b pcAddMenuItem
```

The `pc` are your initials (the person making the branch).   The rest is camel-cased and summarizes the purpose of the branch.

You could also come up with a different branch name convention, one that works better for your team.

The important thing is to have one.
* You should use the branch naming convention described above *unless* your entire team comes to a team consensus
  on a different convention, and a rationale for why that process is better.
* If you decide on a different convention, document it in a file `team/CONVENTIONS.md`

# Working on a feature branch

You may need, periodically, to push your changes to GitHub.  Use the branch name in place of `master`:

* `git push origin pcAddMenuItem` 

You may need, from time to time, to rebase your branch on master.

This is to say, replay all of the changes on your branch on top of a *fresh* copy of master.

To do this, type:

```
git pull --rebase origin master
```

You may have merge conflicts.  If so, you may find that you have to resolve these merge conflicts *one commit at a time*.

If all else fails, you can always type `git rebase --abort` to abort the mission and start over.

But if you stay focused, you can get through it:

* Step through the commits carefully, and read the instructions on the screen carefully.  
* At each step, use `git status` to see where you are and what the next step is.
* Files marked in red as `both changed` are the ones that you need to look for merge conflicts in
* You resolve those by editing the file, and then doing a `git add` so that it turns green in the `git status` output.
* You may have to do multiple commits and then `git rebase --continue`
* At some steps, you may also find you need to do `git rebase --skip` to get to the next commit.


Eventually, you'll have a new version of your branch, at which point you'll want to:

* test to make sure that everything still works.
* then "force push" to update GitHub with the new branch history for your branch (your changes "rebased" on the newest version of `master`).

```
git push --force origin pcAddMenuItem
```



