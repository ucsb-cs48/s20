---
desc: "Tuesday Lecture: 3rd Retro, Final Sprint Planning"
lecture_date: 2020-05-26
num: lect24
ready: true
lab06: https://ucsb-cs48.github.io/s20/lab/lab06/
lab07: https://ucsb-cs48.github.io/s20/lab/lab07/
lab09: https://ucsb-cs48.github.io/s20/lab/lab09/
new: '<span class="badge badge-warning">New Due Date</span>'
---

# Announcements

- New due dates for lab06 and lab07 to give you some extra time if you need it
- Column at <https://ucsb-cs48.github.io/s20/teams_page/> for storybooks; see how yours compares to others'

# TODAY
* Retro
* Sprint Planning
  - lab05 submission
  - lab09 assignments
  - organize "final demo prep" column on Kanban board



| Week | Monday        | Tuesday              | Wednesday |  Thursday      | Friday |
|------|---------------|----------------------|-----------|----------------|--------|
|  9   | No class (Memorial Day) | 5/26  <br/> Retro 3 <br /> Sprint Planning <br /> lab05 due <br />  Start [lab09]({{page.lab09}}) (Ops review) |   | 5/28  [lab06]({{page.lab06}}) due <br> {{page.new}}  | |
|  10   | 6/01  Ops review due (lab09)  | 6/02  [lab07]({{page.lab07}}) due <br> {{page.new}}  |        | 6/04 | |
| Finals |  |  | 6/10 [5pm final presentations](https://ucsb-cs48.github.io/s20/exam/5pm_section/) | 6/11 [3:30pm final presentations](https://ucsb-cs48.github.io/s20/exam/330pm_section/) | |
{:.table .table-sm .table-striped .table-bordered}

# Details

1. Decide who is the Sprint Planning leader, and who is the Retro leader today
2. While Retro leader does bookkeeping updates in `team/LEADERSHIP.md` and `team/RETROS.md` (see bottom of page), Sprint Planning leader take care of lab09 bookkeeping.
3. Do the Retro
4. Do the Sprint Planning


# (1) lab09 bookkeeping

For lab09, In the file `team/DEPLOY.md`, put in a table such as this one where you indicate how you are dividing up the 
reviewing.  Refer to <https://ucsb-cs48.github.io/s20/teams_page/> for the actual teams that are in your discussion
section.

```
# Deployment Testing
    
Our team: s0-t1-ride-share

Other Teams:
  
| Team                     | Who is reviewing | Issue Number |
|--------------------------|------------------|--------------|
| s0-t2-covid-19           | Alice, Bob       |   65         |
| s0-t3-restaurant-reviews | Chris, Danny     |   66         |
| s0-t4-dog-sitting        | Ellery           |   67         |
```
 
The final column for "issue number" reflects the fact that you should add issues on your kanban board with titles
such as those listed below, and then assign those issues to the folks that were assigend.  Track these on your Kanban board
like all other work in progress.  
* lab09 s0-t2-covid-19
* lab09 s0-t2-restaurant-reviews
* lab09 s0-t4-dog-sitting

## Get access needed to complete lab09

1. Each team member, join the slack channel of the team you are reviewing.  (You can leave the channel when you are done with lab09).  
   - e.g. Alice and Bob join the s0-t2-covid-19 channel, Chris and Danny join s0-t3-restaurant-reviews and Ellery joins s0-t4-dog-sitting  
   
2. On that channel, request:
   - read access to the other teams main code repo (unless it is public already)
   - request write access to the `-DEPLOY-FEEDBACK` repo for the other team (e.g. `s0-t2-covid-19-DEPLOY-FEEDBACK`)

LATER, after class today, look at your own team's channel.  Find the person from the other team revieiwng your repo, whose repo you are reviewing.  Give them the access they request.
* if Uma and Victoria from team s0-t2-covid-19 are reviewing s0-t1-ride-share, then Alice or Bob should respond to the requests from Uma and Victoria
* if Wally and Xavier  s0-t2-restaurant-reviews are reviewing s0-t1-ride-share, then Chris or Danny should respond to the requests from Wally and Xavier
* if Yolanda and Zach from s0-t4-dog-sitting are reviewing s0-t1-ride-share, then Ellery should respond to the requests from Yolanda and Zach.

Follow up between now and class on Thursday to ensure that you have all the access you need.

# (2) Retro

Reminder that during a retro, you should *gather input from everyone* before starting to discuss.

It is an "anti-pattern" to just jump into discussion before gathering input.   
* Staff, please intervene if you hear that happening!

Darby/Larsen's five stages of a successful retro:
* Open the Retro
  - check in, e.g. rose/thorn, personal weather report
* Gather input: * (1) before discussion (2) in writing (3) in silence (4) from everyone*
* Generate Insights: * each person reads their input, discussion leader facilitates grouping/categorizing *
  - also a good time to review info from last retro; what was the experiment, how did it turn out?
* Decide What To do: *come up with action plan.*
* Close The Retro
  - appreciations
  

  
# (3) Sprint Planning

Leader for Sprint Planning should be different from person that led the retro (see bookkeeping below)

### Share screen and review Kanban board

* First, check that anything in the "In Progress", "In Review", "Done" columns is accurate; i.e. if there are cards that should have been moved already, move them.
* If lab06 and/or lab07 are not yet complete, be sure that there are stories for them either in the "Final Iteration" column (if not yet started), or in "In Progress" if already underway.
* Second, make a column for the "Final Iteration".   Anything not already "in progress", "in review", or "done" that belongs in the Final Iteration should be put into that column.
  - You may get rid of columns for MVP, 2nd iteration, etc. if those have already served their purpose and are now empty.
  - You may be want to make a column called "Ice Box" or "Future" for any stories that you came up with that might be nice to have, but that you don't think are realistic for your final iteration.
* If lab06 and/or lab07 are not yet complete, be sure that there are stories for them either in the "Final Iteration" column (if not yet started), or in "In Progress" if already underway.
* Plan your final iteration    
  - Decide which stories go into the "Final Iteration".  The deadline is your demo date during finals week.
  - Do "grooming" on these stories (be sure they have clear acceptance criteria)
  - If you aren't sure about a story, better to put it in the icebox / future plans column.  You can always pull it out later.
* Make sure that everyone is assigned to at least one (and preferably at most one) story in the In-Progress column.

# Bookkeeping:

* Update `team/LEADERSHIP.md` with:
  * Who did 2nd iteration demo last Thursday 05/21
  * Who led 3rd retro today 05/26
  * Who is leading Sprint Planning today 05/26
* `team/RETROS.md` should have a section for the final retro with same items as for other retros
* everyone should fill out post-retro survey

For best results (including the best results in your final team grade) make sure there are NO REPEATS in leadership roles until each person on the team has taken a turn.

* If the team was unable to comply with this practice, e.g. due to a team member being absent or unprepared, please make a note in the `team/LEADERSHIP.md` and/or send a private communication to the instructor with an explanation.

