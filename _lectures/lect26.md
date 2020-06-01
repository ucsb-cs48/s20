---
desc: "Last Monday Section: Final Project Report"
lecture_date: 2020-06-01
num: lect26
ready: false
lab10: https://ucsb-cs48.github.io/s20/lab/lab10/
---


# [lab10]({{page.lab10}}): Final project report

* In your meeting today, go over this and assign team members to do part 1, part 2, and part 3.
* Note that for part 3, *each team member* should initially write their own section.    
  - Suggestion: each team member should initially create a draft of their part in `part3_Alice.md`, `part3_Bob.md`, `part3_Carol.md`, `part3_Danny.md`
  - Then: the person writing the overall report can copy/paste those separate files into the unified file, and delete the 
    separate drafts.
* Today: Review the `/graphs/contributors` report for your project repo.    
  - You can find it by clicking "insights" then "contributors".
  
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

# Criteria for Final Project Assessment

In addition to the three parts of the report, here are four other aspects of your final project grade:
- Code hygeine: 
  - When we look at your code, does it have a clear structure?  Or is it spaghetti code, difficult to follow?
  - Is the code reasonably dry? Or does it have lots of copy/pasted parts that could and should have been refactored?
  - Are variables and methods named in ways that make the code clear, or are names chosen haphazardly?
  - For testing, linting, react storybook (as applicable), minimum or go beyond.
- Functionality:
  - Does the app address the user's needs?
  - Is it still very basic, or it is more ambitious?
  - Is it easy to use?
  - Is the UI attractive?
- Project Mechanics
  - Are PRs accompanied by explanations?
  - Are commit messages clear and complete?
  - Do issues have clear acceptance criteria?
- Final course presentation
  - Did the speaker(s) make the use case and the functionality of the app clear?
  - Were they clear and understandable?
  - Was the presentation enjoyable to listen to, i.e. did they "sell" the app?
  - Did they described at least one interesting technical aspects of the project?

Please note that it will be difficult to know how each of these will be weighted until we see which of these actually differentiates one project from another.   There are so many different ways that a project can be excellent (or mediocre).
There is no perfect fairness when evaluating disparate projects on criteria that contain some inherent subjectivity.  We 
will do our best to be sure that we balance each of the performance criteria when assigning a final grade to the project.

