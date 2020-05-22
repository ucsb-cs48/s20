---
layout: lab
num: lab07
ready: false
desc: "Testing for Next.js Applications"
assigned: 2020-05-19 15:30
due: 2020-06-01 12:00
github_org: "ucsb-cs48-s20"
---

This lab is for project teams that are working with the next.js stack.

For teams using the  Spring Boot stack, please visit [lab07_sb](https://ucsb-cs48.github.io/s20/lab/lab07_sb/).


# Two types of testing: plain old unit testing, and end-to-end testing

There are many types of testing that one can perform on a software project.  The article [topics/testing](https://ucsb-cs48.github.io/topics/testing/) tries to provide
a more comprehensive look at this topic.  

In this lab, we are going to focus on just two types of testing:

1.  Plain old unit testing using jest of pure JavaScript code
2.  Cypress testing, which can be used for "end-to-end" testing of a Web Application.

# Step 1: Plain Old Unit Testing (50%)

For plain old unit testing, we recommend jest.

This article describes how jest testing working, and how to configure your project for jest testing:

* <https://ucsb-cs48.github.io/jstopics/testing_jest/>

Your job is to first find some bit of code in your app that is either:
* Already in the form of a pure javascript function, or
* Can be factored into a pure javascript function.

Put that function in its own file under `/utils/nameGoesHere.js` where `nameGoesHere` is some reasonable name for your module.

Use an import to call that function in the proper place in your application.

Then, write a series of jest tests for that function in a file `__tests__/nameGoesHere.js` following the example shown
in the example in the article <https://ucsb-cs48.github.io/jstopics/testing_jest/>.

Finally, configure your repo for jest testing, following the instructions in the article here:
* <https://ucsb-cs48.github.io/jstopics/testing_jest/>

You should do a PR with this branch and note that the jest testing is now part of what runs on GitHub actions when
you do a PR.

# Step 2: Cypress Testing  (50%)

Refer to <https://ucsb-cs48.github.io/jstopics/testing_cypress/>

Big picture: students should
* Configure project for Cypress
* Add at least one set of cypress tests (3-5 tests) for a feature.
* Exact scope is to be negotiated with the project mentor.

