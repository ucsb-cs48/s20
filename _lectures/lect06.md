---
desc: "Monday Section: "
lecture_date: 2020-04-13
num: lect06
ready: false
---


# Homework

* Reminder than H01 is due midnight tonight. <https://ucsb-cs48.github.io/s20/hwk/h01/>
* We are assigning H02: <https://ucsb-cs48.github.io/s20/hwk/h02/>
* It is due Wednesday.

# Tomorrow

lab00 will be assigned tomorrow.    It is to get you oriented to deploying with your tech stack

* https://ucsb-cs48.github.io/s20/lab/lab00/

* The instructions are not 100% ready yet, but if you are doing the next.js version, they 95% ready, so you can get started
  if you want.
* The Spring Boot version should be ready by tomorrow morning.

# Today

* More work in your teams on MVP
* Add acceptance criteria to stories 

Acceptance criteria:
* are individual testable things things that "should be true" if the story is finished
* By "testable", in this case, we mean testable by a human using the app
* The sum total of the acceptance criteria, if *all* true, should define that the feature is correctly implemented.

So, include both the "happy path" as well as "error path" in your acceptance criteria.

To put them in an issue, use this syntax (which makes a list with checkboxes):

```
- [ ] There should be a login button if you are not logged in
- [ ] When you click on the login button, it should redirect you to a place where you can sign in
- [ ] If you correctly sign in, a new menu called "add item" should appear
- [ ] The "add item" menu item should not appear if you are not logged in
- [ ] If you are logged in, there should not be a login button, but a logout button instead.
- [ ] Clicking on the logout button should log you out
```

Later, we'll *also* discuss how to write automated tests for each acceptance criteria (in addition to testing manually).

For now, though, just focus on what the acceptance criteria for each story should be.

# If you are done

Go ahead and create additional columns for additional "iterations" beyond the MVP, i.e. a second iteration, third iteration, etc.  

Put stories into those, and "groom them", i.e. add acceptance criteria.
