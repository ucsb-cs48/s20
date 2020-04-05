---
desc: Monday Section, 
lecture_date: 2020-04-06
num: lect03
ready: false
---

# Teams are Assigned

You should have been:
- invited to a team channel on the [Slack](https://ucsb-cs48-s20.slack.com)
- added to one of the [teams](https://github.com/ucsb-cs48-s20/teams) on the [ucsb-cs48-s20 Github org](https://github.com/ucsb-cs48-s20).
- given admin access to a project repo for your team
- given read-only access to a FEEDBACK repo for your team

You'll also be put into a Breakout Room with your team during section today.    

# The Slack: `_articles` vs. `_help` channels

On the Slack, there are several pairs channels that have the endings `_articles` and `_help`, for example:
* [`#git_articles`](https://app.slack.com/client/T0102CZLS2W/C0104TA8UV8), [`#git_help`](https://app.slack.com/client/T0102CZLS2W/C010678LAAF)
* [`#nextjs_articles`](https://app.slack.com/client/T0102CZLS2W/C010XJZ06K0), [`#nextjs_help`](https://app.slack.com/client/T0102CZLS2W/C010VM01BU5)
* [`#spring_articles`](https://app.slack.com/client/T0102CZLS2W/C010KGW5A2K), [`#spring_help`](https://app.slack.com/client/T0102CZLS2W/C01069WV6M9)
* etc.

In each case:
* *If you want to share a useful article, tip, blog post, video, etc.* about the topic,  post in the `_articles` channel for the topic.
* *If you need help* with the topic, i.e. you want to ask a question, post in the `_help` channel for the topic.   You are also encouraged to provide help in the `_help` channel if you think you know the answer to someone's question.

# The `#nextjs_*` channels are for everything JavaScript related

Note that the [`#nextjs_articles`](https://app.slack.com/client/T0102CZLS2W/C010XJZ06K0) and [`#nextjs_help`](https://app.slack.com/client/T0102CZLS2W/C010VM01BU5) channels will also be used for all technologies that relate to the `next.js` stack, including:
* JavaScript
* node
* express
* React
* Cypress testing
* etc.
  
# The `#spring_*` channels are for everything Java related

Similarly that the [`#spring_articles`](https://app.slack.com/client/T0102CZLS2W/C010KGW5A2K), [`#spring_help`](https://app.slack.com/client/T0102CZLS2W/C01069WV6M9) channels will also be used for:
* Java
* Thymeleaf
* Maven
* JUnit
* etc.  
  
# If you aren't sure, you can always use [`#general`](https://app.slack.com/client/T0102CZLS2W/C010GVBB6T1)

If you aren't sure where to post or ask something, you can always use the [`#general`](https://app.slack.com/client/T0102CZLS2W/C010GVBB6T1) channel.

A few more special purpose channels:

* Always monitor the channel for your team
* Always monitor the channel for your discussion section or lecture section *during lecture or section*

# Absences

If you need to miss class for an unavoidable reason, please notify:
* *FIRST*, your team, on your team channel
* *SECOND*, DM the instructor.

Please send these notifications:
* in advance where possible. 
* as soon as possible after the fact, when advance notification isn't possible.

This is a matter of showing respect for your team.

Then, as soon as possible after the class, *check with your team* to see what you missed.  It should be a team responsibility to help one another with unavoidable absences.

Unavoidable reasons might include:
* Being too ill to participate in class
* Family emergency
* Internet outage
* An online job interview that could not be scheduled at another time.

Of course, unavoidable absences should be rare if you are going to remain in good standing with your fellow team members, folks that are depending on you to do your part for the team.

# Breakout work today

Today, during your breakout sessions, you should accomplish the following tasks:

(1) Add an initial README.md, .gitignore, and LICENSE.md, and team/AGREEMENTS.md to your repo. (Details below)
(2) Start a discussion of your team agreements / team norms. (Details below)
(3) Record whatever agreements you are able to reach in team/AGREEMENTS.md
    
# If you run out of time

If you run out of time, the agreement discussion can be continued outside of class over the slack, and during the next lecture.

# If you finish early

If you finish all of the above, you can start on a discussion of the following things.  These are discussions that will carry over into Tuesday and Thursday lectures, but you can start them now if you've finished the items above.

* Which tech stack your group plans to use
* Some initial planning about what what you want your app to do for the user.

# Which tech stack

We've provided a lot of information for you already, and when we formed groups, we took tech stack preferences into account.  So in most groups, there is likely to be a quick consensus on which tech stack to use.  But you should still discuss the pros/cons of each, and share your preferences with one another.

If you have questions, or need guidance, ask the course staff (Prof. Conrad, Scott, Andrew L, Bryan T, Cole B., Kristin H, and Victor S.).

# Planning your app 

How many different kinds of users are there, and what are their roles?

Examples: 
* A ride share app mvp has two kinds of users: those looking for rides, and those offering rides.  
  * A third kind of user role you might need is site admins, users that can have the power to delete anyone's posting.
* A game app might have only one kind of user: game player
* A Recipe sharer app might have two kinds:
  * Users that look up recipes, but can't add new data to the system
  * Admins that can upload new data to the system
  * Later, you might also allow user contributed content; in that case, you might want admins to have the ability to delete inappropriate content.

Think about the fact that your app will be available on the public internet.  If your app allows user contributed content of any kind, there is the potential for inappropriate content (spam, or worse) to be added.   One option is restrict your user base to folks with an `@ucsb.edu` login; we can provide example code for both Spring Boot and next.js that you can build on to add this feature to your app.




