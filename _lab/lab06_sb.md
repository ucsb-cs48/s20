---
layout: lab
num: lab06_sb
ready: false
desc: "Linting for Spring Boot applications"
assigned: 2020-05-18 12:00
due: 2020-05-26 15:30
github_org: "ucsb-cs48-s20"
---

This is an alternative to [lab06](https://ucsb-cs48.github.io/s20/lab/lab06/) for teams that are not using React.

This lab is for teams using the Spring Boot web framework, and focuses on introducing tools for linting source code.

Example Tools include:
* [checkstyle](https://checkstyle.sourceforge.io/) - a tool for checking code formatting style rules 
* [astyle](http://astyle.sourceforge.net/) - a tool for automatically reformatting code to comply with style rules
* [ArchUnit](https://www.archunit.org/) - a tool to check whether certain architectural principles are being followed
* [PMD](https://pmd.github.io/latest/) - a static code analyzer that looks for many code anti-patterns

We are going to focus only on the first two of these tools for now, unless it appears that the other tools are more interesting to your team, and/or more viable to incorporate.

The purpose of this lab exercise is to:
* introduce you to professional code standards, using the Google Java Style Guide as an illustration
  - Note that this guide is enforced internally at Google for all Java projects.
  - There are similar style guides for Python, Go, and other langauges used at Google.
* introduce you to tools used to enforce code style, using `checkstyle` as an illustration
* introduce you to the process of getting code into proper style, and maintaining it in proper style, using a combination of techniques, each where it is appropriate, including:
  - automated tools, e.g. `astyle`
  - manual code edits
  - IDE formatting support
  - declared exceptions to the rules (`checkstyle` refers to these as "suppressions", and stores them in a file `suppressions.xml`).

The page <https://ucsb-cs48.github.io/javatopics/code_style_checkstyle/> on the CS48 website describes each of these techniques.

Your initial job (70% of your grade) is to:
* incorporate checkstyle into the `pom.xml` for your repo, using a custom `checks.xml` file as illustated at <https://ucsb-cs48.github.io/javatopics/code_style_checkstyle/>
* modify the code to enforce the "no tabs" rule, using astyle as illustrated

You can then earn an additional 30% by incorporating a few more rules into your `checks.xml` and modifying the code so that these rules are enforced.  You should work with your mentor to decide which rules, and how much each is worth.  We suggest that three more rules is a good target, with 10% for each rule, but it depends on the level of effort required, which is not something we are able to predict well up front.  

So we encourage you to work closely with your mentor throughout your work on the lab so that you are both satsified with the outcome.

When you are finished, you'll submit the URLs of one or more PRs that incorporate the formatting rule modifications.  There will be a place on Gauchospace for you to make this submission.

