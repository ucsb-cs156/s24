---
title: team04
desc: "Team Project: Reflections during legacy code phase"
assigned: 2024-05-15 17:00
due: 2024-06-01 11:59
github_org: ucsb-cs156-s24
layout: lab
layout: default
parent: lab
num: team04
nav_order: 204
ready: true
---

# {{page.title}} - {{page.desc}}

During the legacy code phase of the project, whenever anyone on the team merges a PR or closes a PR, a slack bot will prompt you in your team channel for reflections.

When this happens, at least two people should write a brief reflection as a reply to the post by the slack bot:

* The developer that did most of the coding
* The team member that did the code erview

You should focus on **what you learned from working with this PR**, regardless of whether that learning took place as you thought about the issue,
wrote the code, debugged errors, wrote tests, dealt with CI/CD errors, dealt with the code review--in short, any phase of the software development lifecycle.

Sometimes, a PR may be very trivial, and as a result, there may not be much to say. *That's ok*, but you *should still at least make a post*.

There will be a team grade added to the lab portion of your grade that is based on two factors:

* 50% of your grade: *Quantity*: What was the percentage of these prompts that were responded to (even if it was to say: this was a trival PR; there's not much to say)
* 50% of your grade: *Quality*: What was the overall quality of the team's reflections?  Here is where if you have "nothing to say" on 100% of your PRs, you may run into difficulties.  You should have some reflections on at least *some* of them!

If you have questions, please ask on the slack channel `#help-team04`  

## Example reflections

Here are some sample reflections written by staff members on their own PRs so that you can get an idea of what a thoughtful reflection might look like.

### PR: <https://github.com/ucsb-cs156-s24/STARTER-team03/pull/16>

The main takeaway from this PR is that having copies of the exact same code across multiple files, is not the ideal way to have a cohesive and concise program. And so in this PR, I factored out all of the common code from the two test files `ITOauth.java` and `ITRestaurant.java` into a parent class `WebTestCase.java` so that the two test files would not share almost 50 lines of identical code. But one of my main reflections, looking back on the PR, is... is it really the best idea to factor out everything? or does it sometimes make sense to leave some stuff in to increase the context available to someone who is reading the file for the first time.

My thought is that it depends on the case, but in this case I am torn whether it was the right decision to factor out everything. From a number of lines perspective, this is ideal. But considering that this code is what some students will be looking at for their first time seeing an integration/end-to-end test, it might be harder to understand how it works when separated into parent and child classes.
