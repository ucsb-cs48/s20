---
desc: "Thursday Lecture: user stories and MVP, then next.js intro, OR user stories"
lecture_date: 2020-04-07
num: lect05
ready: true
---

# Outline of today

* Hwk for Monday <https://ucsb-cs48.github.io/s20/hwk/h01/>
* A few remarks about Agile
* A brief MVP (minimum viable product) case-study
* A choice
  - Lecture/Demo by Scott Chow on next.js based on <https://nextjs.org/learn/basics/getting-started/setup>
  - Work in your teams on defining your MVP

# Homework for Monday Midnight 

* <https://ucsb-cs48.github.io/s20/hwk/h01/>
* It's an intro to Agile
* Note: on the "dates" question 
  - I am not usually one for memorizing dates
  - I'm making an exception in this case because it's important to know how long Agile has been around.
  - Many folks act as if it's either "brand new", or "has been around for ever"
  - The actual age of Agile is important to putting it into context

# What is important about Agile?

* **Inspect and Adapt**
  * This is the most important Agile principle
  * The idea is to be empirical, scientific, flexible
  * **Dogmatic** adherence to process is the **opposite** of true agile
* Inspect and Adapt what?
  * What/Why: The product we are building, based on user/customer feedback
  * How: The process by which we build it, based on periodic retrospectives

# Where do user stories fit in?

* They drive the process of development
* They keep the focus on what the user needs and why they need it
* In these projects: **you are your own user**
  * Note that it's a mantra of software development: **You are not your user**
  * In most real world settings, that literally true
  * That's one way this course differs from real world Agile
* Keep in mind what *hat* you are wearing
  * The user hat or the developer hat

# Pitfalls

* Suggesting features that would be "fun to build" 
* Suggesting features that would be "a good learning experience".
* Suggesting building a feature "just because you can"

All of those are fine for
* a "hackathon project" or a "side project"
* in the real world: "10% time", "Future Focused Friday", "Hack Day"

BUT: 
* It is NOT how you should suggest features for a *real* product
* Even though this is a university course and the main objective is learning...
* ... what we are trying to learn mostly is the *process* of developing *real* software.

Thus:

Learning the self-discipline of driving features from user needs, in *this* course, is *more* important than learning a paricular API, technology, etc.

# Minimum Viable Product

* A case study: putting a card game online.
* The card game: <https://dl.acm.org/doi/10.1145/3328778.3366989>

  
> Colleen M. Lewis and Phillip Conrad. 2020. Teaching Practices Game: Interactive Resources for Training Teaching Assistants. In Proceedings of the 51st ACM Technical Symposium on Computer Science Education (SIGCSE ’20). Association for Computing Machinery, New York, NY, USA, 1110–1111. DOI:https://doi.org/10.1145/3328778.3366989


Game Rules for each round:

1. One person (the *Leader* for this round) draws a card and reads the bold text at the top.
2. The *Leader* then asks the group: What would you do in that situation? <br>
   Each member of the group answers the question or passes
3. After hearing all answers (or 3 minutes), the *Leader* reads the sample answer from the card aloud and picks their favorite answer (the *Winner* for this round). The *Winner* keeps the card to tally who won the most times.
4. The leader rotates clockwise.

At the end of the game, the overall *Winner* is the one with the most cards.

Some sample cards:

![card01]({{'/lectures/lect05/card01_25pct.png' | relative_url }})
![card02]({{'/lectures/lect05/card02_25pct.png' | relative_url }})
![card03]({{'/lectures/lect05/card03_25pct.png' | relative_url }})
![card04]({{'/lectures/lect05/card04_25pct.png' | relative_url }})

Now, consider these four proposals for building this product.  This illustrates an iterative approach to getting to an MVP.

These are actual excerpts from an email conversation between Phill Conrad and
Colleen Lewis, shared with permission.

# Proposal 1

Email from Phill to Colleen:

> What if I made an online version of the game so that folks could play over Zoom (or other video conference tool)
>
> I.e. a website with the content that
> * allows anywhere from three to six players to join a session
> * keeps track of whose turn it is
> * displays the next card
> * gives each person except the one who's "it" a chance to type in their answer
> * when everyone has typed in an answer reveals them all at the same time
> * allows the person who is "it" to select the winner for that round
>
> I'm teaching a web dev course this quarter and I need a demo project to work on anyway.  
>
> Let me know your thoughts.

# Proposal 2

Collen's reply to Phill:

> That's awesome! If you're up for making it! That's great!
> 
> I can imagine a version - using zoom - where it would be a bit more similar to playing in person. I added some text in bold and crossed out things that then wouldn't be relevant. But - if you have a different vision for it -go for it! 
>
> * allows anywhere from three to six players to join a session 
> * keeps track of whose turn it is
> * displays the next card and people can say what they would do or pass.
> * ~~gives each person except the one who's "it" a chance to type in their answer~~
> * ~~when everyone has typed in an answer reveals them all at the same time~~
> * allows the person who is "it" to select the winner for that round
> * allows the person who is "it" to see the sample answer and read that. 
>
> :-) 
> - Colleen

# Proposal 3

Phill to Colleen:

> Sounds good to me... These revisions make it closer to a "minimum viable product" which is a good thing.   
>
> ...
>
> In fact, it occurs to me that the most minimum viable product is simply a site that would shuffle the deck and display the next card.     Period.
>
> On a video conf session, the host brings this up and does "share screen".   Who is "it" and the rest of game play can simply be done by the participants coordinating verbally.
>
> This makes the app something feasible to deliver very quickly.


# Proposal 4

Colleen to Phill:

> Sure! Totally! That's a great point! I can even [imagine] a minimal viable product is a slide deck that has the questions and then on the next slide the question & answer on it. That would be cool to be able to show a client right away :-) 

# Resolution

Phill back to Colleen

> That's perfect, because it illustrates the point that the MVP doesn't always involve code!

My email to Colleen went on to note [this story from the founders of Doordash](https://www.productdone.com/doordash-concierge-mvp/) about how their initial  MVP was nothing more than a static html page with a list of a few restaurants, each with a link to a scanned pdf of the menu, and a phone number to call.   

From that, you iterate, and only write the code you really need.

The article mentions the idea of a [Concierge MVP](https://www.shortform.com/blog/concierge-mvp/) which is an important idea in an approach known as "Lean Business" (which is a "cousin" of the Agile methodology).   

# "Concierge MVP"

A "Concierge MVP" is a product that:
* you can get set up quickly
* *involves human intervention* in steps that might later be partially or fully automated
* has, as its main purpose: market validation and information gathering
* is not intended as a long-term strategy (and is likely not viable or sustainable long-term)

It's the *human intervention* that defines a "Concierge MVP".

# Final Roadmap for the TA Training Card Game:

Note that you might never build the later iterations; you only keep developing as long as the extra features really, really add value.

* Iteration 1: Powerpoint

* Iteration 2: Webapp that mirrors the Powerpoint functionality.
  * Iteration 2a: Just all the cards in order, with a button to reveal the sample answer.
  * Iteration 2b: Randomizing the cards.

* Iteration 3: Add a way to keep track of who is playing, and whose turn it is to be "it".

* Iteration 4: Add "keeping score".  But the game is still shared over a zoom screen by just one participant.

* Iteration 5: Add folks being "join a game" and see the screen for themselves (eliminating the need for anything more than a shared audio channel).

* Iteration 6: A game that could be completely self contained over text chat that takes place inside the app.   Folks might still *want* to have audio and/or video open, but it would be an enhancement rather than necessary.    


# Breakout work today

Two options:

# Option 1:

* A demonstration/lecture by Scott Chow about how to get started with next.js
* Link: <https://nextjs.org/learn/basics/getting-started/setup>

# Option 2:

* Add an MVP column to your Kanban board.

We'll put you all in breakout groups.

* In your group discuss whether you want to hear the next.js lecture/demo or work on your teams on your MVP.
* If you want to hear the next.js lecture, just return to the main group.
* Otherwise, work in your teams.
* If you have questions, click the "Ask for Help button".


