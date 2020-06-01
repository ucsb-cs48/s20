---
layout: lab
num: lab10
ready: true
desc: "Final Report: Part 1 (Users Guide), Part 2 (Programmers Guide), Part 3 (Roles)"
assigned: 2020-06-01 12:00
due: 2020-06-08 12:00
github_org: "ucsb-cs48-s20"
---

Final Report: Part 1 (Users Guide), Part 2 (Programmers Guide), Part 3 (Roles)"

In this lab, you'll complete  your final projct report. It will have three sections, each of which 
will be a Markdown file.

You'll complete this in a separate repo called, for example, [s0-t1-budget-REPORT](https://github.com/ucsb-cs48-s20/s0-t1-budget-REPORT), [s0-t2-env-REPORT](https://github.com/ucsb-cs48-s20/s0-t2-env-REPORT),
etc.  Those repos already exist (they were created for you): they are private and your team has admin access.

# Step 0: Create a README.md with links to the individual parts.

Your README.md file will have links to separate md files `users_guide.md`, `programmers_guide.md` and `roles.md`, as well as links to other items as shown below.

(You may omit the React Storybook Link if your team completed the Spring Boot alternative.)

```
# Team s0-t1-budget Final Report, CS48, S20

* Team Members: (List them here)
* Tech Stack: Put either Node.js or Spring Boot

## Sections
* [Part 1: Users Guide](./users_guide.md)
* [Part 2: Programmers Guide](./programmers_guide.md)
* [Part 3: Roles](./roles.md)

## Links
* Source Code: <url goes here>
* React Storybook: <url goes here>
* Production Link: <url goes here>

```

# Part 1: Users Guide (30 %)

Your Users Guide should provide a brief description of the purpose of your app, and how to use it.  It does not *necessarily* need to have detailed
screen shots of every *single* feature, but it should have enough detail that:

* A potential user can read through it and decide whether or not the app will meet their needs.
* If it *does* meet their needs, it describes the app in enough detail that they can make use of the app.

With that general advice, the length and level of detail is up to you.  If it meets the two criteria above fully, then it has enough detail.  
If not, then you may need to make it longer, or go deeper.

# Part 2: Programmers Guide (30 %)

The programmers guide should provide enough detail that a programmer knows:
* What technologies and APIs are used in the app.
* Where to learn more about each of those technologies.
* Anything that the programmer would need to understand about how your code is structured.

You do not need to *repeat* detail that is already covered in your deploy instructions, but you may want to make
reference to or link to those instructions.

Here are some examples of points to cover.  For each technology or product, provide a link to whether the programmer can learn more.

* Mention Next.js or Spring Boot
* Describe any React frameworks that you used  (e.g. additional React add on packages)
* Describe which database technologies you used (e.g. MongoDB, Postgres) and briefly describe the structure of your data (what tables do you have, and what kinds of data is stored in each?)
* Describe any APIs with which you are interacting, and what the purpose of each is
* Describe what authentication services you are using, especially if they go beyond the OAuth and/or Auth0 examples
  provided in the demo apps.
* Describe any libraries or open source code that you incorporated (e.g. chat application demos, game engines, etc.) and
  provide a link to where you got them from.
* If your app is divided into separate parts, e.g. a front-end and back-end in separate repos, describe that here, and why
  you had to implement it that way.
  
Also, if you had significant side-projects (e.g. proofs of concept, skunkworks projects, spikes) that your team worked on
that are part of your teams effort, but are not part of the main repo, describe that here.
  
# Part 3: Roles (40 %)

In this file, you should have a separate paragraph for each member of the team, describing their contributions to the project.

As a starting point, every team member should review the `/graphs/contributors` tab for your repo, e.g.
* <https://github.com/ucsb-cs48-s20/project-s0-t1-budget/graphs/contributors>
* <https://github.com/ucsb-cs48-s20/project-s0-t2-env/graphs/contributors>
* etc.

That page shows graphs of contributions to the repo over time at the level of commits. 

Link to that page in your repo.  

Note that this page cannot tell the whole story: just because  team member Alice had 20 commits while Beth had only 5 does not
necessarily mean that Alice did five times as much work as Beth.  Perhaps both Alice and Beth contributed to the team in
important ways, and the nature of their contributions was different.  Perhaps Beth contributed to significant skunk works project that is not shown, or perhaps her commits were much larger than Alice's individual ones.  In any case, a disparity between commits of a factor of 5 does tell some kind of story, and in your account of each team members contributions, you should help us understand that picture.

If indeed, some team members contributed more than others, this is an opportunity to have an honest conversation 
about that, and as a team, decide how to tell that story.


# Is the `Contributors` graph accurate?

Note that there can be big disparities between the contributors graph and ground truth.

One source is "misattributed commits".  As an example, see this page:

* <https://github.com/ucsb-cs48-s20/project-idea-reviewer/commits/master?after=e37a193735918fa2f25c9af93ad1e129caec2946+69>

Note that:
* *some* of the commits that Phill Conrad did on this page are attributed to his GitHub account, `pconrad`, and have his avatar (the icon/photo) next to his commit.
* but *other* commits are *not* attributed to that account, and just say "Phillip Conrad", and have a generic grey icon.

The difference has to do with whether the machine on which the commits were performed was configured to connect to a GitHub account or not.   This is a lesson learned for the future!  We'll cover how to fix this much earlier in the course next time.

It's too late to fix the commits, but it's NOT too late to offer an explanation in part 3 of your report.
* We are going to look at the data on the `/graphs/contributors` for your repo, but
* We are going to look *more* at your explanation of that data.

If the data and the explanation match, it's all good.

If you have a team member that you suspect has made lots of commits that are not being attributed to them, 
scroll through your commit log and see if you can find a few examples.

You can then link to a few of those in part 3 of your report.   For example, the link above shows lots of unattributed commits that have `pc -` in the initials, and show `Phillip Conrad authored and Phillip Conrad committed ` but that are not linked with the `pconrad` account.   If you can find similar data, it's helpful for providing context for team members with fewer commits on the graphs. 
