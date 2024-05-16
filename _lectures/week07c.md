---
title: "Week 07c - 05.16 Thu"
lecture_date: 2024-05-16
description: "Looking ahead: Release Notes, Final Presentations; then work on legacy code project"
ready: true
layout: default
parent: lectures
slides:
---

# Review of yesterday in Section

* Yesterday in section, we introduced the legacy code projects
* We also made sure that each member of the team was assigned to an in-progress issue
  - Note: it should be a real issue, not a "draft" issue.
  - If you are assigned to a draft issue, please convert it to a real issue
  - Also: if your issue is "factored out" of another larger one, copy over the parts of the description that pertain, and update the acceptance criteria
  - The PR, in the end, needs to be linked to an issue with a list of acceptance criteria.  If it isn't, that will delay it getting merged, and delay your team getting the points.
  
# Goal for today: Deployments

You can't make progress on your issues if you can't deploy on localhost, and on dokku.

So today, the goal is that by the end of class, every student is able to run the the main branch of their legacy code app on localhost and create a personal dev deployment on dokku.

What you'll need:
* Create OAuth credentials
  - For courses, happycows, gauchoride, it works just like jpa03/team02/team03
  - BUT for organic, it's "same stuff, different provider".  It's a similar process, but not the same, because our OAuth provider is now Github instead of Google.
  - So, check the README and the docs directory for instructions
* Fix `ADMIN_EMAILS` (courses/happycows/gauchoride) or `ADMIN_GITHUB_LOGINS` (organic)
  - Just as before, you'll want to have a prod and qa site where members of your team and the staff can login and try the admin features
  - For courses/happycows/gauchoride, that's a comma separate list of ucsb emails in `ADMIN_EMAILS`
  - But for organic, it's a comma separated list of Github Logins in `ADMIN_GITHUB_LOGINS`
* Set up the database (just as you did for jpa03/team02/team03)


# Extra Steps for proj-courses

* You'll need to set a config var (or an .env var) called UCSB_API_KEY.  The value was distributed in your team channel.
* You'll also need to set up a value `MONGODB_URI`.  On your team channel there's a value for this with everything except the password; for example it may look like this:
  ```
  MONGODB_URI=mongodb+srv://dbuser:<password>@cluster0.alernhy.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
  ```
* There is a process for obtaining the password from the <https://mongodb.com> website.
* Once you've obtained that, please do NOT share the password in the regular team channel (though you may DM it to one another on slack).
* If the password is, for example, `1234567abcdefg98765` you'll need to substitute it in, removing the angle brackets.
  * Correct: `MONGODB_URI=mongodb+srv://dbuser:1234567abcdefg98765@cluster0.alernhy.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0`
  * Incorrect:  `MONGODB_URI=mongodb+srv://dbuser:<1234567abcdefg98765>@cluster0.alernhy.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0`
* You'll also want to set the variables `START_QTR` and `END_QTR`.  The first four digits are the year, and the last digit is:
  * `1` for Winter, `2` for Spring, `3` for Summer, `4` for Fall.
  * For example: `F20` is `20204`, W23 is `20231, and S24 is `20242`
* Finally, before you deploy, type in this: `dokku git:set appname keep-git-dir true`
  * This only has to be done once for the app
  * It sets a flag that tells dokku to keep the .git directory in the Docker container
  * This allows the endpoint `/app/systemInfo` to display information about the latest commit in the deployed code, which can be useful for debugging problems with dokku deployments
    
# team04 - reflections

* Reflection is built into Agile in the retrospective
* But that should not be the only time we engage in reflection
* Reflection, in general is a useful habit
* To encourage you to build that habit, we have built a Slackbot that will prompt for reflection after every merged PR (or PR closed with being merged)

After each PR that is merged or closed, you'll be prompted in your team channel to enter a short reflection.

Your team's grade for team04 will be based on the quantity and quality of your reflections.

See: <https://ucsb-cs156.github.io/s24/lab/team04.html> for details.

Here's an example of what that looks like "in the wild" (link to [post on slack](https://ucsb-cs156-s24.slack.com/archives/C06RP83BA83/p1715820746266849)).  This was a PR that the staff did to the
repo for <https://github.com/ucsb-cs156-s24/proj-gauchoride-s24-5pm-5> to debug an issue with the workflow for updating issues, so the staff entered their own reflections as an example.

<img width="1041" alt="image" src="https://github.com/ucsb-cs156/s24/assets/1119017/d2f3bf3d-197d-44b5-bec7-fbcb7285d98b">
<img width="387" alt="image" src="https://github.com/ucsb-cs156/s24/assets/1119017/83f16959-25b0-4f91-807d-95f66dc5d145">


# Looking Ahead

* Release Notes (due end of week 10)
* Final Presentation (due end of week 10)

# Brief Discussion of "Release Notes"

At the end of the legacy code phase, each team will be required to submit "release notes" for all of the features they added to the main branch (i.e. the difference between their main branch, and the main branch of the starter code for the project.)

These serve at least two purposes:

* **Functional**: These messages help them to be aware of, and use the new functionality.  Customers can't take advantage of new features if they don't know about them.

* **Marketing**: If you are running a software business, you are always concerned about "churn", which is the business term for when a paying customer stops paying you, and starts giving money to your competitor instead.   These messages need to convey to your customers that you have heard their concerns, and care about making their lives easier, more fun, less stressful—whatever the purpose of the app happens to be.
As we move into the legacy code phase of the course over the next few days, **your PR descriptions will be the source material** for these release notes for either HappyCows or Gauchoride, so it's important that they be written well.  This is why we ask for screenshots, etc. and that the PR descriptions include a description of new features not just from the programmer/developer perspective, but from the end-user perspective.

# Sample Release Notes

* courses: <https://github.com/ucsb-cs156/proj-courses/blob/main/docs/release-notes/proj-courses-w24-5pm-2.pdf>
* happycows: <https://github.com/ucsb-cs156/proj-happycows/blob/main/docs/release-notes/w24-4pm-2.pdf>
* organic: <https://github.com/ucsb-cs156/proj-organic/blob/main/docs/release-notes/w24-6pm-1.pdf>
* gauchoride: <https://github.com/ucsb-cs156/proj-gauchoride/blob/main/docs/release-notes/w24-7pm-1.pdf>

# A brief work about the final presentations

TODO: Talk about that here.
