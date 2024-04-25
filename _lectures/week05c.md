---
title: "Week 05c - 02.08 Thu"
lecture_date: 2024-02-08
description: "work on team02 or team03"
ready: true
layout: default
parent: lectures
slides:
github_org: ucsb-cs156-w24
num: team03
---

# For lecture today:

* Start with standup
* Organize "in progress" issues for team03 (even if not done with team02; see below)
* Discuss whether to appoint a scrum master, or share the responsiblity, and post your decision to your team channel
* Reminder: the Javascript homework on Gradescope (get it done so you are ready to start team03)

I would prefer not to make this a "participation assignment"; I'd prefer to invite the teams to hold one another accountable for these three items.

# Organizing In Progress issues for team03

Even if not finished with team02, please do the following *today during class*
* Find your repo and Kanban board for team03
* Find the first issue for your database table (the tables are the same as for team02).  This could be either the creation of your dokku dev deployment, or it could be migrating your @entity, @repository, controller and controller tests from team02 to team03.
* Drag that issue into In Progress and assign it to yourself on the Kanban board.

# The Scrum Master role

There is a particular structured approach to Agile called "Scrum" (a term from the sport of Rugby).  One of the roles in Scrum is the "Scrum Master", a team member that has responsibility for making sure that the issues on the Kanban board are getting assigned, worked on, reviewed, and merged.

Some teams assign a specific individual as the "Scrum Master".   Other teams make "the whole team" be the Scrum Master, i.e. everyone on the team shares the responsibility of "auditing" the board periodically to look for anomalies and try to help the team correct those.  By anomalies I mean such things as:

* A team member that is not assigned to any issue
* An issue "In Progress/In Review/Done" not assigned to any team member
* An issue "In Review" that has no connected Pull Request
* An issue "In Review" that has been in that status for more than 24 hours with no one actually doing a code review
etc...

Today, in lecture, I'll ask each team to decide whether to
* (a) appoint a specific scrum master
* (b) share that responsibility as a whole team.

Please discuss, and then post your decision to the slack channel.

I will add that if you decide to appoint a specific scrum master, you might ask that person to serve in that rule through week 6, and then either ask them to continue, switch to someone else as scrum master for weeks 7/8, or switch to "whole team scrummaster".   Contemplating that could be part of your next retro.


# Going forward: make sure you have an In Progress issue before standup

I'd like to suggest that for future standups, that this be a part of the process, i.e.
* As part of your sharing on the slack channel, make a note of whether you have something in the in progress column for the project the team is working on,
* If you don't personally have something in the "in progress" column, fix that before standup.
* During the out loud part of the standup, someone bring up the kanban board and verify that each person has an "in progress" issue.

The only time it would be normal to NOT have something there is if/when all of the issues for the team are "In Review" or "Done".
Even if all the issues for your database table are finished, if there are other issues to be done, you can assign yourself as a pair partner and help your teammates finish.



# Github Projects: Kanban / Table view

Each of your project boards (linked below) has two tabs labelled "Kanban" and "Table".  Please take a moment to familiarize yourself with the table view.  Note that you can sort by columns.

* The Kanban board view is better for getting a quick overview of the big picture status of the project
* The table view may be better for answering questions such as:
  * which issues in In Progress do/do not have team members assigned
  * which team members are/are not assigned to issues in the In Progress column
  * which issues under "In Review" do/do not have PRs connected to them

So whether you are the scrum master, or just a member of the team seeking to help keep the team on track, this can be a very useful tool.

## Team02

| 4pm | 5pm |
|-----|-----|
|[team02-{{site.qxx}}-4pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-4pm-1)|[team02-{{site.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-5pm-1)|
|[team02-{{site.qxx}}-4pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-4pm-2)|[team02-{{site.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-5pm-2)|
|[team02-{{site.qxx}}-4pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-4pm-3)|[team02-{{site.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-5pm-3)|
|[team02-{{site.qxx}}-4pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-4pm-4)|[team02-{{site.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-5pm-4)|
|[team02-{{site.qxx}}-4pm-5](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-4pm-5)|[team02-{{site.qxx}}-5pm-5](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-5pm-5)|
|[team02-{{site.qxx}}-4pm-6](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-4pm-6)|[team02-{{site.qxx}}-5pm-6](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-5pm-6)|
|[team02-{{site.qxx}}-4pm-7](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-4pm-7)|[team02-{{site.qxx}}-5pm-7](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-5pm-7)|
|[team02-{{site.qxx}}-4pm-8](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-4pm-8)|[team02-{{site.qxx}}-5pm-8](https://github.com/ucsb-cs156-{{site.qxx}}/team02-{{site.qxx}}-5pm-8)|


## Team03

| 4pm | 5pm |
|-----|-----|
|[team03-{{site.qxx}}-4pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-4pm-1)|[team03-{{site.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-5pm-1)|
|[team03-{{site.qxx}}-4pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-4pm-2)|[team03-{{site.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-5pm-2)|
|[team03-{{site.qxx}}-4pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-4pm-3)|[team03-{{site.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-5pm-3)|
|[team03-{{site.qxx}}-4pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-4pm-4)|[team03-{{site.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-5pm-4)|
|[team03-{{site.qxx}}-4pm-5](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-4pm-5)|[team03-{{site.qxx}}-5pm-5](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-5pm-5)|
|[team03-{{site.qxx}}-4pm-6](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-4pm-6)|[team03-{{site.qxx}}-5pm-6](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-5pm-6)|
|[team03-{{site.qxx}}-4pm-7](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-4pm-7)|[team03-{{site.qxx}}-5pm-7](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-5pm-7)|
|[team03-{{site.qxx}}-4pm-8](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-4pm-8)|[team03-{{site.qxx}}-5pm-8](https://github.com/ucsb-cs156-{{site.qxx}}/team03-{{site.qxx}}-5pm-8)|


# Reflection and the Instant Retro

While sprint retrospectives (retros) offer a structured opportunity for reflection, **reflection is a good practice at all times**.

There is a practice in Agile called the "**instant retro**", which is where, on any day, at any time, if something interesting happens (good or bad), the team may choose to go into "retro mode" for 5 minutes, or 15 minutes or whatever seems appropriate, to pause and reflect on that one interesting thing, and whether it suggests something the team wants to "stop", "start" or "continue".

Observations about things the team should "stop". "start" or "continue" may be made **at any time**, not just during formal structured retros.

You can also make "personal retro" observations about your own practice in the slack channel.  For example:
> Personal retro observation: <br />
> If I start running one test at a time with<br />
> `mvn test -Dtest=ControllerName\#method_name` instead of running the full `mvn test` every time, <br />
> then I expect that I'll find the root cause of failing tests faster and I will be more productive.

You are encouraged to consider adopting this practice.


# Staff Information
Information below is intended for staff.  You are welcome to look at it, but the intended audience is instructors/LAs/TAs

<details markdown="1">
<summary>
 Click triangle for information for staff
</summary>

Please check the kanban boards for your assigned teams to see that the team has six issues in progress, one per team member.



### team02

| Staff Member | team 1 | team 2 | team 3 | team 4 |
|-----|-----|-----|-----|-----|
| Sai        | [team02-{{site.qxx}}-5pm-1](https://github.com/orgs/{{page.github_org}}/projects/18) | [team02-{{site.qxx}}-5pm-2](https://github.com/orgs/{{page.github_org}}/projects/19) | [team02-{{site.qxx}}-6pm-1](https://github.com/orgs/{{page.github_org}}/projects/20) | [team02-{{site.qxx}}-6pm-2](https://github.com/orgs/{{page.github_org}}/projects/21) |
| Sangita       | [team02-{{site.qxx}}-4pm-3](https://github.com/orgs/{{page.github_org}}/projects/22) | [team02-{{site.qxx}}-4pm-4](https://github.com/orgs/{{page.github_org}}/projects/23) | [team02-{{site.qxx}}-7pm-3](https://github.com/orgs/{{page.github_org}}/projects/24) | [team02-{{site.qxx}}-7pm-4](https://github.com/orgs/{{page.github_org}}/projects/25) |
| Sanil      | [team02-{{site.qxx}}-5pm-3](https://github.com/orgs/{{page.github_org}}/projects/26) | [team02-{{site.qxx}}-5pm-4](https://github.com/orgs/{{page.github_org}}/projects/27) | [team02-{{site.qxx}}-6pm-3](https://github.com/orgs/{{page.github_org}}/projects/28) | [team02-{{site.qxx}}-6pm-4](https://github.com/orgs/{{page.github_org}}/projects/29) |
| William      | [team02-{{site.qxx}}-4pm-1](https://github.com/orgs/{{page.github_org}}/projects/30) | [team02-{{site.qxx}}-4pm-2](https://github.com/orgs/{{page.github_org}}/projects/31) | [team02-{{site.qxx}}-7pm-1](https://github.com/orgs/{{page.github_org}}/projects/32) | [team02-{{site.qxx}}-7pm-2](https://github.com/orgs/{{page.github_org}}/projects/33) |

### team03

| Staff Member | team 1 | team 2 | team 3 | team 4 |
|-----|-----|-----|-----|-----|
| Sai        | [team03-{{site.qxx}}-5pm-1](https://github.com/orgs/{{page.github_org}}/projects/34) | [team-03-{{site.qxx}}-5pm-2](https://github.com/orgs/{{page.github_org}}/projects/35) | [team-03-{{site.qxx}}-6pm-1](https://github.com/orgs/{{page.github_org}}/projects/36) | [team-03-{{site.qxx}}-6pm-2](https://github.com/orgs/{{page.github_org}}/projects/37) |
| Sangita       | [team-03-{{site.qxx}}-4pm-3](https://github.com/orgs/{{page.github_org}}/projects/38) | [team-03-{{site.qxx}}-4pm-4](https://github.com/orgs/{{page.github_org}}/projects/39) | [team-03-{{site.qxx}}-7pm-3](https://github.com/orgs/{{page.github_org}}/projects/40) | [team-03-{{site.qxx}}-7pm-4](https://github.com/orgs/{{page.github_org}}/projects/41) |
| Sanil      | [team-03-{{site.qxx}}-5pm-3](https://github.com/orgs/{{page.github_org}}/projects/42) | [team-03-{{site.qxx}}-5pm-4](https://github.com/orgs/{{page.github_org}}/projects/43) | [team-03-{{site.qxx}}-6pm-3](https://github.com/orgs/{{page.github_org}}/projects/44) | [team-03-{{site.qxx}}-6pm-4](https://github.com/orgs/{{page.github_org}}/projects/45) |
| William      | [team-03-{{site.qxx}}-4pm-1](https://github.com/orgs/{{page.github_org}}/projects/46) | [team-03-{{site.qxx}}-4pm-2](https://github.com/orgs/{{page.github_org}}/projects/47) | [team-03-{{site.qxx}}-7pm-1](https://github.com/orgs/{{page.github_org}}/projects/48) | [team-03-{{site.qxx}}-7pm-2](https://github.com/orgs/{{page.github_org}}/projects/49) |

</details>
