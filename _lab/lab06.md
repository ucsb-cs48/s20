---
layout: lab
num: lab06
ready: false
desc: "Storybook "
assigned: 2020-05-18 12:00
due: 2020-05-26 15:30
github_org: "ucsb-cs48-s20"
---

# React Storybook 

This lab deals with React Storybook, a tool for cataloging, documenting and testing React components.

For teams that are not using React, alternative lab06 instructions are provided at the links below:
* For `s0-t4-new-city`, follow [lab06-sb](https://ucsb-cs48.github.io/s20/lab/lab06-sb/) (Linting for Java)

# Example Storybooks

Here are some example storybooks from CS48 sample code:

| Storybook | Repository | 
|-----------|------------|
| [project-idea-reviewer-nextjs-storybook](https://ucsb-cs48-s20.github.io/project-idea-reviewer-nextjs-storybook) | [project-idea-reviewer-nextjs](https://github.com/ucsb-cs48-s20/project-idea-reviewer-nextjs) |
| [cs48-s20-nextjs-tutorial-storybook](https://ucsb-cs48-s20.github.io/cs48-s20-nextjs-tutorial-storybook) | [cs48-s20-nextjs-tutorial](https://github.com/ucsb-cs48-s20/cs48-s20-nextjs-tutorial) |
{:.table .table-sm .table-striped .table-bordered}

# Lots of information about Storybook

Lots of information about Storybook can be found here:
* <https://ucsb-cs48.github.io/jstopics/react_storybook/>

This includes:
* Explanation of sample code, including how to write story code for a React component
* How to add Storybook to your next.js project
* How to bring up your Storybook on localhost
* How to publish your Storybook to a GitHub pages site

# Your job in lab06

Minimally (for 70% credit):

* Add Storybook to your project
* Add at least one React components to your Storybook, including at least one with Knobs
* Your storybook should be able to run on localhost with `npm run storybook`

Better: For 80% credit: 

* Also, deploy your storybook to the repo that has the same name as your repo, 
  but with `-storybook` appended, using GitHub pages.  Instructions are contained within <https://ucsb-cs48.github.io/jstopics/react_storybook/>.  The repos should already exist.


Even better (for 90% credit):

* Add at least two more (total of three) React components to your Storybook, including at least one with Knobs

Best (for 100% credit):

* Add all existing React components in your project to Storybook, with or without multiple stories, and with or
  without knobs as appropriate.
* If you have only three React components in your Storybook, consider refactoring some additional UI elements out of your
  existing pages, creating React components for them.
* Ideally, there should be at least five components: BUT, don't create components "just for the sake of the grade".  If you
  honestly don't see opportunities to create more than three components, consult with the staff, and if we agree, we can give
  you a waiver.  (There may be some teams where this is true, depending on your project.)
