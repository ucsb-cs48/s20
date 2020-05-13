---
desc: "Thursday Lecture:  "
lecture_date: 2020-05-14
num: lect20
ready: false
---

# Ops Video / Instructions

One of the important aspects of Software Development that often gets overlooked in the academic curriculum is "operations".   

Operations refers to the things other than your code that are necessary to deploy a running application.   This includes:
* configuring the platform on which the software is deployed
* configuring external dependencies such as authorization servers, databases, API credentials, etc.
* configuring initial accounts (for example, accounts for admins, etc.)

Each of your production and QA applications has some "operations" that are necessary to get it deployed on Heroku.

This assignment has five parts:

*   **Part One: Written Deployment Instructions** 

    You will prepare a set of instructions with all of the steps necessary to start with nothing but "read only" access to
    your repo, and end with a running instance of your app on Heroku.  
    
    The running instance that your instructions enable should be *entirely separate* from the running instances for your
    own team.  That is:
    * You should not share any database credentials
    * You should not share any OAuth or Auth0 credentials
    * You should not share any 3rd party API credentials (e.g. Firebase, Spotify, Google, etc.)
    
    Instead of sharing the credentials, you should share *instructions for obtaining those credentials*,
    and instructions for configuring those credentials for your application.

    These instructions should be in Markdown format, and stored in a file called `/docs/DEPLOY.md` in your repo.
    (It is ok to factor this out into separate pages also stored under `/docs` and linked to from `docs/DEPLOY.md`)
    
    There should be a link to `./docs/DEPLOY.md` from your main `README.md` file of your repo, e.g.
    
    ```
    * [Deployment Instructions](./docs/DEPLOY.md)
    ```

    Today, I suggest that you create a story on your Kanban board for the creation of the deployment instructions, and
    assign it to an individual or a pair on your team.

*   **Part Two: Deployment Video**

    Working from your written deployment instructions, you'll make a video where you follow the instructions yourselves,
    step by step, and show what the deployment looks like.   You can use the instructions [here](https://youtu.be/k0Je8ASh4jo) for how to make such a video
    using Zoom and YouTube; you may also use another tool if you have access to one and prefer it.

    If in the course of making that video, you end up showing
    values of secrets (e.g. database passwords, OAuth tokens, etc.) you should go back and *invalidate* those tokens before
    releasing the video.
    
    Today, I suggest that you create a story on your Kanban board for the creation of the deployment video, and put it 
    wherever you keep stories that are not ready to start yet; you will eventually assign that story to someone, but
    you aren't ready to start it until you have the written instructions done.
    
    Ideally the video will be made be someone other than the person that wrote the written instructions.  That makes it more
    likely that if there are any ambiguities, errors, or omissions in the instructions, you'll find them before the video
    is finished.
    
*   **Part Three: In pairs or trios, follow another team's instructions **

    As a team, you are now going to divide up the three other teams apps from your discussion section among the 
    individuals on your team, and working as individuals or in pairs, you'll try following the other teams 
    instructions.
   
    In the file `team/DEPLOY.md`, put in a table such as this one where you indicate how you are dividing up the 
    reviewing.  Refer to <https://ucsb-cs48.github.io/s20/teams_page/> for the actual teams that are in your discussion
    section.

    ```
    # Deployment Testing
    
    Our team: s0-t1-ride-share

    Other Teams:
  
    | Team    | Who is reviewing |
    |----------------|------------------|
    | s0-t2-covid-19 | Alice, Bob       |
    | s0-t3-restaurant-reviews | Chris, Danny |
    | s0-t4-dog-sitting | Ellery |
    ```
    
    Each of you should then try deploying the app from the other discussion sections assigned to you.   We'll distribute
    links to the videos with the deployment instructions.
 
    If you run into difficulties, join that team's channel and ask questions.   Do your best to work with the team
    to help them refine their instructions, just as your classmates help you refine yours.
 
*   **Part Four: Provide feedback **

    Each of the pairs or individuals should now prepare a brief writeup with  feedback on the written instructions and
    the video.   

    * Were you able to successfully bring up the application?
    * Where did you run into difficulties?
    * What suggestions did you make to 

*   **Part Five: Refine your own instructions **

    Based on the feedback you receive both during step three, and from step four, refine your own instructions so that
    when the course staff tries to follow your instructions, they are very unlikely to run into any problems.
    

    
    

        
