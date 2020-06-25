---
assigned: 2020-04-21 16:00
desc: MVP Demo Video
due: 2020-05-07 15:00
layout: lab
num: lab02
ready: true
github_org: ucsb-cs48-s20
gauchospace: https://gauchospace.ucsb.edu/courses/mod/assign/view.php?id=3919993
---

lab02 is a team-based grade for the MVP demo.

The YouTube video <https://youtu.be/k0Je8ASh4jo>
explains how you can create an MVP demo video using Zoom and YouTube:

<iframe width="560" height="315" src="https://www.youtube.com/embed/k0Je8ASh4jo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The [link on Gauchospace]({{page.gauchospace}}) is where you upload the link to your demo when it is complete.   The video may be public, or "unlisted", as you see fit.
Links to videos will be shared with the class, but the class is asked not to share links to non-public videos (unlisted videos)
with people other than enrolled students and course staff.

Your video should be no longer than 5 minutes and should follow the instructions given in <https://ucsb-cs48.github.io/s20/lectures/lect16/>,
which are repeated here:

# Demo from your prod app

Your demo should be from your production app (`prod` on Heroku), not from a version deployed on `localhost`.

Students in the class, as well as Instructors/TAs/LAs should be able to visit your production link and try out the app after watching your video.

So, make every effort to have your production version ready to go with a stable MVP on Thursday.

# Additional notes about the MVP demo

1. **Features beyond MVP are fine**  Note that if you have moved your production version on master "beyond" your MVP, 
   that's fine; as long as it contains all of the MVP functions.   If you are time restricted, you can focus the demo
   just on the MVP features and "save" the rest for later.
   
2. **Broken `master` is a problem.  You can fix with a `temp-prod` branch**.   
   If your `master` branch is currently "broken" in 
   some way that makes it impossible to do a decent demo from your `prod` Heroku app, then here's a quick fix:
   
   - (a) find an earlier commit that isn't broken 
   - (b) give that commit a branch name `temp-prod` for example 
     - use: `git checkout -b temp-prod` 
     - then `git reset --hard a1b2c3d4` where `a1b2c3d4` 
       is the sha of the commit that's good; 
     - then `git push origin temp-prod -f` 
   - (c) redeploy your prod app using `temp-prod` instead of the master branch.
   
   If you do this, please disclose that you are demoing from `temp-prod` and not master in your lab02 submission 
   so that we aren't confused when evaluating your MVP.  
   
   It's not ideal, but it won't be a major deduction.  It's better than demoing a broken `master` branch.
   
3. **A demo from `localhost` is better than nothing, but isn't really an MVP demo**.   If you absolutely 
   *cannot* do a meaningful demo from your production app, then you may demo from `localhost` as a last resort, rather
   than offering no demo at all.   However, that will result in a lower grade; 
   a localhost app isn't really "viable" in the sense that you can't put it in the hands of customers.   
