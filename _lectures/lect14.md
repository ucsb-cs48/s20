---
desc: "Thursday Lecture: "
lecture_date: 2020-04-28
num: lect14
ready: false
---

# public vs. private?

- Be sure to audit for `.env, secrets-localhost.properties, secrets-heroku.properties`
- Be sure to audit for secrets embedded in your code (e.g. from tutorials from other sources)
- If you have any of these, even on older commits or other branches, do NOT make repo public unless/until you invalidate old secrets.

# opting in to "limited" sharing within the class

If you are willing to allows us to give other class teams "read only" access to your code, pleae let us know.

# Integrating with 3rd Parties

* Approach 1: Find any old javascript tutorial, and the wedge it into next.js
* Approach 2: Actually look for React + Plaid, or Next.js + socket.io, etc.

# Big picture patterns

* socket.io for real time communication
  - Missile, Spotify Queues, Poker?, Mafia?
* loading big datasets
  - new-city (Spring Boot), other teams?
* OAuth other than Google
  - Plaid API (has it's own OAuth), Slack-Bot (Slack has it's own OAuth).
  
