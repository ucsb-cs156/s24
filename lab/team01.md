---
title: team01
desc: "Team Project 01: Spring Boot Backend, part 1 (unauthenticated RESTFul APIs)"
assigned: 2024-04-16 17:00
due: 2024-02-01 23:59
github_org: ucsb-cs156-s24
layout: default
parent: lab
num: team01
nav_order: 201
ready: true
starter: https://github.com/ucsb-cs156-s24/STARTER-team01
software: https://ucsb-cs156.github.io/s24/info/software.html
qxx: s24
org: ucsb-cs156-s24
participation_activity_num: p07
participation_activity_date: "Tuesday 04/16/2024"
demo_deployment: http://team01.dokku-00.cs.ucsb.edu
sample_team: s24-4pm-3
teams_list: https://bit.ly/cs156-s24-teams
canvas: 
---

Canvas link: <{{page.canvas}}>

# First team programming assignment: Spring Backend, and working with APIs

This is a team programming assignment.  Each team has it's own repo to complete this assignment, and
you will work as a team.

## Work on your own laptop, not CSIL

You should be working with a Java setup on your
own laptop by this point, not on CSIL.

For advice on what to install, see:

* <{{page.software}}>

If this presents a difficulty, please contact the instructor ASAP so that some arrangement can be made for your situation.

# Grading

* You will submit on Canvas for manual grading.

# Working with a Kanban Board

In this assignment, we'll start practicing with a *Kanban Board*, which is a basic tool used by many software development organizations.

- Every organization has some approach to what is called the *Software Design Life Cycle* or *SDLC*
- Some organizations adopt a formal framework such as *Agile* or *Scrum*
- Others use a more informal or hybrid approach, choosing bits and pieces from various frameworks, keeping what works, and setting aside what doesn't.
- I put myself in that category, embracing a core principle from Agile: *Inspect and Adapt*.
- More on that later.

## What you'll do: Process

From a process standpoint, you are working with a Kanban board.

- A Kanban board is a "visualization of work in progress"
- If you've ever worked with a Trello board, it's a similar idea.
- Originally, a Kanban board was a corkboard, and each item was an index card pinned to it with a thumbtack.
- These days, they are mostly online tools.

In this course, we typically work with four columns labelled:
* "todo", "in progress", "in review" and "done".

There may be more columns or fewer, though typically at a minimum, there is:
* "todo", "in progress" and "done".

Here's how that will play out in detail:


1. Navigate to the web page for the GitHub organization, i.e. <https://github.com/{{page.github_org}}>.  You'll see a tab for `Projects`. Click on that tab.  You should then see a project for your team for the team01 assignment, e.g. `team01-s24-5pm-1`, `team01-s24-5pm-2`,etc.
2. Open the link for your team's Project.  You should find four columns: `Todo`, `In Progress`, `In Review`, `Done`
3. The `Todo` column will be populated with a set of tasks, which are called *Issues* in the GitHub implementation of Kanban.  These correspond to the Issues that we'll also see in the `Issues` column of your repo.
4. Now navigate to your repo for {{page.num}}, which will have a url such as: <https://github.com/{{page.github_org}}/{{page.num}}-{{page.sample_team}}>.  You will see a tab for `Issues`. Click on that tab.
4. You should now see a list of issues.  These are the work items your team needs to complete to do the the work for the team01 assignment. They are the same issues that you find in the "To Do" column of your Kanban board (i.e. your `Project`, to use the GitHub terminology).
5. There may also be some additional housekeeping steps that you need to complete in order for the {{page.num}} assignment to be considered completed; the issues on the Kanban board are not necessarily the only things you need to complete to earn full credit for the assignment.  But these issues are the bulk of the work you need to divide up as a team.
6. Note that you are allowed and even encouraged to add cards on the Kanban board and/or Issues for any other items you find in the assignment description that need to be completed.  Tracking this on the Kanban board can be a helpful way to make sure that it get done, and to signal to other team members when it has been done.
7. Each team member will take on an issue, one at a time, assign it to themselves, and move it from the "To Do" column of the Kanban board to the "In Progress" column as you start the issue.  When you are finished with the issue, you move it into the "In Review" column when you've made a "Pull Request" to indicate that the issue is ready for your team members to review.
8. Ideally, each team member should have exactly one (and only one) issue assigned to them in the In Progress column at a time.
9. Once a pull request is complete for a given task, you move it into the `In Review` column
   - At this stage, you seek a code review from a member of the team that
     was not involved in the coding.
   - Also, at this stage, if the PR is not "green on CI",
     meaning that all of the GitHub actions scripts show green checks, this is when you
     should address that, before merging the pull request.
6. Only when the PR is merged does the issue get moved into the `Done` column.

Please note that each team has a mentor (those are listed [here]({{page.teams_list}}) that will be keeping an eye on your Kanban boards.  As long as you are not done with your contribution to the project, you should always have at least one issue in the `In Progress` column (the thing you are working on to contribute to the team's work.)

# The Kanban board belongs to the team

The staff has pre-populated your Kanban board with a number of issues to help you get started.  However, please be aware of these important points:

* There may be things in this assignment description, or other things that your team needs to get done that are *not* included on the Kanban board.
* As/when you find such things, feel free to *add them to the Kanban board yourself*.

The purpose of the Kanban board is primarily to *serve the team* as a visual representation fo the work in progress.

It is true that since this is a *course*, there is an aspect that you are maintaining the Kanban board for a "grade", as part of an "assignment"&mdash;but the hope is that ultimately, you'll see the intrinsic value of keeping a board like this up-to-date so that the team has way to see what's going on with the project at a glance.

# What are we actually building?

Now let's turn from a discussion of process, to a discussion of the product itself.

This video goes with this introduction:
* On YouTube (public): [team-intro (10:13)](https://youtu.be/jY2BLuEfAgk)

You are building a Spring Boot webapp that *only has a backend*.  The front end code will built in a later team project.

We will use a tool called *Swagger-ui* that:
* builds a temporary front-end that can be used by developers to test the backend.
* provides a way for programmers to automatically build documentation for their backend.

If you want to see an example of what the working web app should look like, you can visit this site:

* <{{page.demo_deployment}}>

The following link is a better example of what we'll be doing:
* <{{page.demo_deployment}}/swagger-ui/index.html>

This is an exercise in working with three kinds of APIs as explained in [this short article on APIs](https://ucsb-cs156.github.io/topics/apis.html)

The starter code you are given contains three "controllers", each of which implements a separate backend API:

* The Java class [`EarthquakesController`](https://github.com/{{page.org}}/STARTER-TEAM01/blob/main/src/main/java/edu/ucsb/cs156/spring/backenddemo/controllers/EarthquakesController.java) implements an API endpoint that provides information about earthquakes within a given distance from Storke Tower, that have a magnitude that is greater than or equal to some minimum specified.
* The Java class [`CountryCodeController`](https://github.com/{{page.org}}/STARTER-TEAM01/blob/main/src/main/java/edu/ucsb/cs156/spring/backenddemo/controllers/CountryCodeController.java) implements an API endpoint that, given the name of a country, provides information about that country, including a list of latitude and longitude points that mark the outline of that country.
* The Java class [`CollegeSubredditsController`](https://github.com/{{page.org}}/STARTER-TEAM01/blob/main/src/main/java/edu/ucsb/cs156/spring/backenddemo/controllers/CollegeSubredditsController.java) provides an endpoint that gives a list of subreddits on the social networking site Reddit.com that correspond to various colleges and universities.   This endpoint doesn't need any input.

These three controllers, in turn, rely on three Java classes that each provide a "service".  The service provided, in each case, is a method `getJSON(p1,p2,...)` that may or may not take parameters.  The parameters are the ones that were input to each of the controllers
* the [`EarthquakeQueryService`](https://github.com/{{page.org}}/STARTER-TEAM01/blob/main/src/main/java/edu/ucsb/cs156/spring/backenddemo/services/EarthquakeQueryService.java) implements `getJSON(String distance, String minMag)` which is used by the `EarthquakesController`.
* the [`CountryCodeQueryService`](https://github.com/{{page.org}}/STARTER-TEAM01/blob/main/src/main/java/edu/ucsb/cs156/spring/backenddemo/services/CountryCodeQueryService.java) implements `getJSON(String country)` which is used by the `CountryCodeController`
* the [`CollegeSubredditQueryService`](https://github.com/{{page.org}}/STARTER-TEAM01/blob/main/src/main/java/edu/ucsb/cs156/spring/backenddemo/services/CollegeSubredditQueryService.java) implements `getJSON()` (with no parameters) which is used by the `CollegeSubredditsController`

For each of these controller / service pairs, there are also tests:

| Controller  | Controller Test | Service  | Service Test |
|-|-|-|-|
| `EarthquakesController` | `EarthquakesControllerTest` | `EarthquakeQueryService` | `EarthquakeQueryServiceTest` |
| `CountryCodeController` | `CountryCodeControllerTest` | `CountryCodeQueryService` | `CountryCodeQueryServiceTest` |
| `CollegeSubredditsController` | `CollegeSubredditsControllerTest` | `CollegeSubredditQueryService` | `CollegeSubredditQueryServiceTest` |
{:.table .table-sm .table-striped .table-bordered}


So you are given those twelve classes.   Your job, as a team of six developers, is to implement 24 more classes (4 each for each of the six rows of the following table).

Important: Initially, each team member should take responsibility for one row of the table, but ultimately, you are all responsible, as a team, for all six rows.

| Controller  | Controller Test | Service  | Service Test |
|-|-|-|-|
| `JokeController` | `JokeControllerTest` | `JokeQueryService` | `JokeQueryServiceTest` |
| `LocationController` | `LocationControllerTest` | `LocationQueryService` | `LocationQueryServiceTest` |
| `PublicHolidaysController` | `PublicHolidaysControllerTest` | `PublicHolidayQueryService` | `PublicHolidayQueryServiceTest` |
| `TidesController` | `TidesControllerTest` | `TidesQueryService` | `TidesQueryServiceTest` |
| `UniversityController` | `UniversityControllerTest` | `UniversityQueryService` | `UniversityQueryServiceTest` |
| `ZipCodeController` | `ZipCodeControllerTest` | `ZipCodeQueryService` | `ZipCodeQueryServiceTest` |

Here's some information on the APIs that these services are based on.

| Service                     | Example |  More info |
|-----------------------------|----------|-------------|
| `JokeQueryService` | <https://v2.jokeapi.dev/joke/Programming?amount=2> | [Documentation](https://sv443.net/jokeapi/v2/)
| `LocationQueryService`       | <https://nominatim.openstreetmap.org/search.php?q=Oxnard&format=jsonv2> | [Documentation](https://nominatim.org/release-docs/develop/api/Overview/) |
| `PublicHolidayQueryService` | <https://date.nager.at/api/v2/publicholidays/2023/us> |[Documentation](https://date.nager.at/Api) |
| `TidesQueryService`         | <https://api.tidesandcurrents.noaa.gov/api/prod/datagetter?application=ucsb-cs156&begin_date=20230710&end_date=20230712&station=9411340&product=predictions&datum=mllw&units=english&time_zone=lst_ldt&interval=hilo&format=json> |[Documentation](https://api.tidesandcurrents.noaa.gov/api/prod/) |
| `UniversityQueryService`    | <http://universities.hipolabs.com/search?name=Stanford> |[Documentation](https://github.com/Hipo/university-domains-list-api) |
| `ZipCodeQueryService`       | <http://api.zippopotam.us/us/93106> |[Documentation](https://api.zippopotam.us/) |


You can also see what those services will look like in Swagger by looking at this example of the finished app running:

* <{{page.demo_deployment}}/swagger-ui/index.html>

That will also give you an idea of what the documentaiton should look like when you've put in all the proper values for the various annotations (the things
that start with `@` in the code.)

# Note: This is an exercise

To be clear: this particular application (with backend services and controllers based on these six APIs) is just an "exercise"; similar to a scrimmage for a sports team, or playing "scales" on a musical instrument. The application we are building doesn't necessarily make sense as a piece of working software, but it will help us to practice some important skills.

The nice thing about this first team activity is that we've structured it so that, for the most part, each contributor's code is independent of the others&mdash; you'll get a first taste of working as a team, but for the most part, your contributions will succeed (or not) independent of your other team members.

This will probably be the last time that is true, however, so you are encouraged to get to know one another, and help and encourage one another.

# The Repos you will work in

Here are the links to the repos:



| 4pm | 5pm | 
|-----|-----|
|[team01-{{page.qxx}}-4pm-1](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-4pm-1)|[team01-{{page.qxx}}-5pm-1](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-1)|
|[team01-{{page.qxx}}-4pm-2](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-4pm-2)|[team01-{{page.qxx}}-5pm-2](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-2)|
|[team01-{{page.qxx}}-4pm-3](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-4pm-3)|[team01-{{page.qxx}}-5pm-3](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-3)|
|[team01-{{page.qxx}}-4pm-4](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-4pm-4)|[team01-{{page.qxx}}-5pm-4](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-4)|
|[team01-{{page.qxx}}-4pm-5](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-4pm-5)|[team01-{{page.qxx}}-5pm-5](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-5)|
|[team01-{{page.qxx}}-4pm-6](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-4pm-6)|[team01-{{page.qxx}}-5pm-6](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-6)|
|[team01-{{page.qxx}}-4pm-7](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-4pm-7)|[team01-{{page.qxx}}-5pm-7](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-7)|
|[team01-{{page.qxx}}-4pm-8](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-4pm-8)|[team01-{{page.qxx}}-5pm-8](https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-8)|


And here are the Kanban boards:

| 4pm | 5pm |
|-----|-----|
| [team01-{{page.qxx}}-4pm-1](https://github.com/orgs/ucsb-cs156-s24/projects/2) | [team01-{{page.qxx}}-5pm-1](https://github.com/orgs/ucsb-cs156-s24/projects/10) |
| [team01-{{page.qxx}}-4pm-2](https://github.com/orgs/ucsb-cs156-s24/projects/3) | [team01-{{page.qxx}}-5pm-2](https://github.com/orgs/ucsb-cs156-s24/projects/11) |
| [team01-{{page.qxx}}-4pm-3](https://github.com/orgs/ucsb-cs156-s24/projects/4) | [team01-{{page.qxx}}-5pm-3](https://github.com/orgs/ucsb-cs156-s24/projects/12) |
| [team01-{{page.qxx}}-4pm-4](https://github.com/orgs/ucsb-cs156-s24/projects/5) | [team01-{{page.qxx}}-5pm-4](https://github.com/orgs/ucsb-cs156-s24/projects/13) |
| [team01-{{page.qxx}}-4pm-5](https://github.com/orgs/ucsb-cs156-s24/projects/6) | [team01-{{page.qxx}}-5pm-5](https://github.com/orgs/ucsb-cs156-s24/projects/14) |
| [team01-{{page.qxx}}-4pm-6](https://github.com/orgs/ucsb-cs156-s24/projects/7) | [team01-{{page.qxx}}-5pm-6](https://github.com/orgs/ucsb-cs156-s24/projects/15) |
| [team01-{{page.qxx}}-4pm-7](https://github.com/orgs/ucsb-cs156-s24/projects/8) | [team01-{{page.qxx}}-5pm-7](https://github.com/orgs/ucsb-cs156-s24/projects/16) |
| [team01-{{page.qxx}}-4pm-8](https://github.com/orgs/ucsb-cs156-s24/projects/9) | [team01-{{page.qxx}}-5pm-8](https://github.com/orgs/ucsb-cs156-s24/projects/17) |

# Part 1: Team divides up the work

# Step 1.1: Divide up the services among your team

This step is a part of participation assignment ({{page.participation_activity_num}}), in class on {{page.participation_activity_date}}.

In the "To do" column on the Kanban board, you'll find issues for implementing the six services.

(If you are on a team with fewer than six members, you may skip one of the six; we'll manually  adjust your grades to give you credit for the missing work.  Or someone on the team can go ahead and do it for practice.)

Divide these up among the members of your team.  When each team members claims one of the services, they should drag the issue for that service into the `In Progress` column, and then assign the issue to themselves.

The six services are:

* Joke look up (enter a category and number of jokes, get back that many jokes in that category).
* Location look up (enter a string, get back locations in the world along with their latitude/longitude)
* Look up public holidays (enter a year and a country code), get back public holidays
* Tides query (enter a start and end date, and a station id, get back high and low tides during that period)
* University query (enter part of a university name, get back all matching universities)
* Zip Code query (enter a zip code, get back information about that zip code).

Each member of the team is responsible for implementing one of these services, the matching controller, and the tests that go along with them.

**NOTE: to get the participation grade for today's class, you MUST actually claim the issue and drag it into the `In Progress` column on the Kanban board during the class period for the participation activity.   If you are not present in class (either in person or online), you might get assigned one of these by your team.
But you only get the particpation grade if you actually did the Kanban board steps in class on the day this was assigned.

# Step 1.2: Deploy the repo, as is, to Dokku

A member of your team should find the issue on the Kanban board for deploying the repo to Dokku wiht the name <tt>{{page.num}}</tt> should drag that issue into `In Progress`, and assign that task to themselves.

Deploying to Dokku is straightforward for this app; see the [/docs/dokku.md](https://github.com/{{page.org}}/STARTER-{{page.num}}/blob/main/docs/dokku.md) file in the starter code repo
for details.

Once the app is deployed, these links should work:

| Team | Link |
|-|-|
| s24-4pm-1 | <https://team01.dokku-01.cs.ucsb.edu> |
| s24-4pm-2 | <https://team01.dokku-02.cs.ucsb.edu> |
| s24-4pm-3 | <https://team01.dokku-03.cs.ucsb.edu> |
| s24-4pm-4 | <https://team01.dokku-04.cs.ucsb.edu> |
| s24-4pm-5 | <https://team01.dokku-05.cs.ucsb.edu> |
| s24-4pm-6 | <https://team01.dokku-06.cs.ucsb.edu> |
| s24-4pm-7 | <https://team01.dokku-07.cs.ucsb.edu> |
| s24-4pm-8 | <https://team01.dokku-08.cs.ucsb.edu> |
| s24-5pm-1 | <https://team01.dokku-09.cs.ucsb.edu> |
| s24-5pm-2 | <https://team01.dokku-10.cs.ucsb.edu> |
| s24-5pm-3 | <https://team01.dokku-11.cs.ucsb.edu> |
| s24-5pm-4 | <https://team01.dokku-12.cs.ucsb.edu> |
| s24-5pm-5 | <https://team01.dokku-13.cs.ucsb.edu> |
| s24-5pm-6 | <https://team01.dokku-14.cs.ucsb.edu> |
| s24-5pm-7 | <https://team01.dokku-15.cs.ucsb.edu> |
| s24-5pm-8 | <https://team01.dokku-16.cs.ucsb.edu> |


The result of visiting the home page of the app in the browser should be something like this:

```json
{"api-documentation":"http://localhost:8080/swagger-ui/index.html","greeting":"Greetings from Spring Boot","repo":"https://github.com/ucsb-cs156-s24/STARTER-team01","team":["Andrew L.","Bryan T.","Calvin J.","Jacqui M.","Mara D.","Max L.","Phill C.","Wade V."]}
```

It might also be nicely formatted, depending on whether you have any browser extensions installed for processing JSON:
```json
{
  api-documentation: "https://starter-team01.herokuapp.com/swagger-ui/",
  greeting: "Greetings from Spring Boot",
  repo: "https://github.com/ucsb-cs156-s24/STARTER-team01",
  team: [
    "Andrew L.",
    "Bryan T.",
    "Bryan Z.",
    "Kevin H.",
    "Phill C.",
    "Pranav M.",
    "Seth V."
  ]
}
```

At a later step (Step 3.2) you'll customize this with links for your team and with the names of your team members.  But we're getting ahead of ourselves.

# Part 2: Work as an individual on your service

In this part of the lab, you work as an individual, on your part.  You may get help from other team members&mdash;in fact you are strongly encouraged to do so!  Pairing on this is a great idea!  But, you should be doing the commits and pull requests from your github account so that you and your team gets credit.

This Video (about 40 minutes) walks you through steps 2.0 through 2.4
* [On Youtube](https://youtu.be/mdh9LJ3RSOQ)

* It's a little longer than I had hoped, because part way through I run into a mistake, and have to debug my way out of it.
* This was already my second attempt at making this one, so rather than start over *again*, I just rolled with it.
* It's a great opportuntiy to see if you can spot my mistake before I do, and to see what steps I took to try to figure out what was going on.

A video for steps 2.5, 2.6, and 2.8 (about 15 minutes) appears here: [Team01 Steps 2.5, 2.6 and 2.8](https://youtu.be/QtlirGJjkz4)

Please note that in the video, the following annotations are used:
* `@Api, @ApiOperation, @ApiParam`

However, those come from a package that has  been deprecated (i.e. they are no longer supported).  Instead, we are now using equivalent annotations from a different package that has ongoing support:
* `@Tag, @Operation, @Parameter`

Please use the new ones.

## Step 2.0: Optional, but recommended: install VSCode extension for Lombok

This step is optional, but highly recommended.  If you like, you may come back and do this later
as the need arises.

In this lab, we'll be using a package called Lombok. Lombok makes many things easier,
by writing boring "cookie-cutter" (also known as "boilerplate") code for you!   However this can cause VSCode to
get confused; VSCode says: "dude, you don't have getters and setters!" or "your variable `log` is undefined!"

To help VSCode not be confused, look under VSCode Extensions, and install this one:

* <https://marketplace.visualstudio.com/items?itemName=GabrielBB.vscode-lombok>


## Step 2.1: Clone the repo to your own machine (or CSIL account)

Clone the team's repo to your own machine or CSIL account, with `git clone repo-url`, then cd into the repo and open it up in your editor (we suggest VSCode).

Then try running `mvn spring-boot:run` and opening up the server on <http://localhost:8080>.

Try navigating to <http://localhost:8080/swagger-ui/index.html> and trying out the various APIs.

Then when you are ready to start coding, we'll move on to Step 2.2.

## Step 2.2: Create a new branch

First come up with a branch name, using this convention: `Firstname-Servicename`, for example:
* If your name is Chris, and you are working on the `PublicHolidayService`, call your branch `Chris-PublicHoliday`
* If your name is Taylor, and you are working on the `ZipCodeService`, call your branch `Taylor-ZipCode`

To create your branch, cd into your cloned repo, and use this command:

```
git checkout main
git pull origin main
git checkout -b Chris-PublicHoliday
```

This creates a new branch `Chris-PublicHoliday` that is branched off a fresh copy of the main branch.

You'll do all of your work in this branch, and when you are done, you'll do a *Pull Request* to get your code into the `main` branch.

* *Note that using this workflow is a required part of the assignment*.
* We are practicing a workflow (the GitHub feature-branch/pull-request workflow) that will become super important later in the course, and even more important when you work on real world projects.

## Step 2.2a: Make a first commit

To get this new branch to appears on Github, we will need to make at least one commit.

I suggest the following: open up the service that you were assigned to; a file for it should already be in the directory `src/main/java/edu/ucsb/cs156/spring/backenddemo/services`.  For example, for ZipCode, it looks like this (I'm leaving out the imports section):

```java
@Service
public class ZipCodeQueryService {

    private final RestTemplate restTemplate;

    public ZipCodeQueryService(RestTemplateBuilder restTemplateBuilder) {
        restTemplate = restTemplateBuilder.build();
    }

    public static final String ENDPOINT = "";

    public String getJSON(String zipcode) throws HttpClientErrorException {
       return "";
    }
}
```

One small change you can make (it's not enough to implement the service, but it's a good start) is to add in the definition of the `ENDPOINT` variable.  It's currently an empty string.  You'll find the necessary value in the table below.  Note the values in `{braces}`; these are variables that will get substituted into the URL at a later step.

| Service                     | Endpoint |
|-----------------------------|----------|
| `JokeService` | `https://v2.jokeapi.dev/joke/{category}?amount={numJokes}` |
| `LocationService`       | `https://nominatim.openstreetmap.org/search/search.php?q={location}&format=jsonv2` |
| `PublicHolidayQueryService` | `https://date.nager.at/api/v2/publicholidays/{year}/{countryCode}` |
| `TidesQueryService`         | `https://api.tidesandcurrents.noaa.gov/api/prod/datagetter?application=ucsb-cs156&begin_date={beginDate}&end_date={endDate}&station={station}&product=predictions&datum=mllw&units=english&time_zone=lst_ldt&interval=hilo&format=json` |
| `UniversityQueryService`    | `http://universities.hipolabs.com/search?name={name}` |
| `ZipCodeQueryService`       | `http://api.zippopotam.us/us/{zipcode}` |

Make this change, and then do a commit.  After doing `git add .`, always do a `git status` to make sure you didn't accidentally add something unintentional; the only file you should be adding to the commit is the `.java` file for your service.  Also use *your* initials, not literally `xy` unless those are your initials, e.g. if your name is Xifeng Yan.

Note that `XY-ZipCode` in the example below is the name of your branch.

```
git add .
git status
git commit -m "xy - define ENDPOINT for zip code service`
git push origin XY-ZipCode
```

At this point, you should see your branch on Github.  The following table shows all branches for each of the teams' repos; check that yours appears.

| 4pm | 5pm 
|-|-|
| [s24-4pm-1 branches](https://github.com/ucsb-cs156-s24/team01-s24-4pm-1/branches) |[s24-5pm-1 branches](https://github.com/ucsb-cs156-s24/team01-s24-5pm-1/branches) |
| [s24-4pm-2 branches](https://github.com/ucsb-cs156-s24/team01-s24-4pm-2/branches) |[s24-5pm-2 branches](https://github.com/ucsb-cs156-s24/team01-s24-5pm-2/branches) |
| [s24-4pm-3 branches](https://github.com/ucsb-cs156-s24/team01-s24-4pm-3/branches) |[s24-5pm-3 branches](https://github.com/ucsb-cs156-s24/team01-s24-5pm-3/branches) |
| [s24-4pm-4 branches](https://github.com/ucsb-cs156-s24/team01-s24-4pm-4/branches) |[s24-5pm-4 branches](https://github.com/ucsb-cs156-s24/team01-s24-5pm-4/branches) |
| [s24-4pm-5 branches](https://github.com/ucsb-cs156-s24/team01-s24-4pm-5/branches) |[s24-5pm-5 branches](https://github.com/ucsb-cs156-s24/team01-s24-5pm-5/branches) |
| [s24-4pm-6 branches](https://github.com/ucsb-cs156-s24/team01-s24-4pm-6/branches) |[s24-5pm-6 branches](https://github.com/ucsb-cs156-s24/team01-s24-5pm-6/branches) |
| [s24-4pm-7 branches](https://github.com/ucsb-cs156-s24/team01-s24-4pm-7/branches) |[s24-5pm-7 branches](https://github.com/ucsb-cs156-s24/team01-s24-5pm-7/branches) |
| [s24-4pm-8 branches](https://github.com/ucsb-cs156-s24/team01-s24-4pm-8/branches) |[s24-5pm-8 branches](https://github.com/ucsb-cs156-s24/team01-s24-5pm-8/branches) |

## Step 2.3: Implement the Service you were assigned

Now, in the directory `src/main/java/edu/ucsb/cs156/spring/backenddemo/services`, you should find the "stub" for the service that you are asked to create.

Each of these services provides a method `getJSON` (which may or may not have parameters, depending on the specifics of the service.)  This `getJSON` method encapsulates a web request to another web application that is our source of information.
Our backend is going to aggregate information from many sources and then, eventually, make it all available to a front-end user interface.

Each of these service works roughly the same as the example `EarthquakeQueryService` or the `CountryCodeQueryService`, so use those services as templates for how to write yours.
* The `EarthquakeQueryService` and `CountryCodeQueryService` are both provided for you as examples.  Please read over them; we'll also go over them in lecture.
* The `CollegeSubredditQueryService` is also provided for you, but it works a bit differently; it uses a CSV file as it's data source rather than a JSON web service.  So don't use that as a model for your services. We'll discuss that one in lecture and how it differs from the others.

You will find that often in this course, you are asked to write some code by using some other code as an example. This "copy/paste/edit" approach, as it turns out, is *very common to how lots of real world code is written*, especially when you
are new to a code base.  You may find that as you work through, you are not really understanding 100% of what you are writing.
That's ok at first; as long as it works, you can just power through some of that.   You are encouraged to ask questions,
and look into what's going on in the code, as long as it doesn't slow you down too much.

Open up the stub file for your service, and start adding code based on what you see in the two example services.

The first piece of information you need is a value for the endpoint.

You should see a variable `public static final String ENDPOINT` that is set to an empty string; instead, set that to the value
in the table below (you may have already done this in Step 2.2a above).
Note the values in `{braces}`; these are variables that will get substituted into the URL at a later step.

| Service                     | Endpoint |
|-----------------------------|----------|
| `JokeService` | `https://v2.jokeapi.dev/joke/{category}?amount={numJokes}` |
| `LocationService`       | `https://nominatim.openstreetmap.org/search/search.php?q={location}&format=jsonv2` |
| `PublicHolidayQueryService` | `https://date.nager.at/api/v2/publicholidays/{year}/{countryCode}` |
| `TidesQueryService`         | `https://api.tidesandcurrents.noaa.gov/api/prod/datagetter?application=ucsb-cs156&begin_date={beginDate}&end_date={endDate}&station={station}&product=predictions&datum=mllw&units=english&time_zone=lst_ldt&interval=hilo&format=json` |
| `UniversityQueryService`    | `http://universities.hipolabs.com/search?name={name}` |
| `ZipCodeQueryService`       | `http://api.zippopotam.us/us/{zipcode}` |

A line of code you may see occasionally is something like this:

```
        log.info("distance={}, minMag={}", distance, minMag);
```

This is debugging output.  Each of the `{}` symbols is  replaced  in the output with the value of the corresponding variable.  This debugging output is enabled with the annotation `@Slf4j` in front of the class; that annotation requires the following import:

```
import lombok.extern.slf4j.Slf4j;
```

Since the `log.info()` method call is just debugging output, it's optional, but if you retain it, you may want to print out
the value of the parameters; for example, for the `LocationQueryService`, you might use:

```
        log.info("location={}", location);
```

You will also a statement such as this one:
```
  Map<String, String> uriVariables = Map.of("minMag", minMag, "distance", distance, "latitude", ucsbLat,
                "longitude", ucsbLong);
```

The parameter to `Map.of` is a list of strings in key/value pairs; i.e. `"minMag"` is a key, and then the value of the variable
`minMag` becomes its value.  The next key here is `"distance"`, with the value of `distance` as its value, and so forth.  The `Map.of` method turns these pairs into a `Map<String, String>` data structure which functions like a hash table, or a Python dictionary; you can look up a key and get its value.

This map is used later to translate the keys in braces in the URL template, e.g. the keys `{minMag}`, `{distance}`, `{latitude}` and `{longitude}` in this URL:

```
    public static final String ENDPOINT = "https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson&minmagnitude={minMag}&maxradiuskm={distance}&latitude={latitude}&longitude={longitude}";
```

You will need to adjust the value passed to `Map.of` based on whatever `{key}` values you find in the URL for your service.  For example, for the LocationQueryService, it should look like this:

```
        Map<String, String> uriVariables = Map.of("location", location);
```

You may also need some additional documentation about the parameters that your API call takes.  You can find this on the swagger-ui pages of staff solution, here:

* <{{page.demo_deployment}}/swagger-ui/index.html>

NOTE: The `EarthquakeQueryService` (along with the test for it) has two hard coded parameters in addition to the ones that
are exposed through the api (i.e. `minMag` for minimum magnitude, and `distance` (for distance in km from Storke Tower).   We
could have chosen to make those parameters that the user of the API could supply.  And indeed, it would feasible (though
it isn't part of this assignment) to implement a separate service that allows the user to supply those, or to make
the lat/long of Storke Tower the default if and only if the user doesn't supply values for those.

But, the bottom line is that *none of the other services you are implementing needs latitude and longitude, especially not that of Storke Tower,
in the implementation.*   So those should not appear in your code for anything other than the `EarthquakeQueryService` and the
`EarthquakeQueryServiceTests`.   Some might say that the `EarthquakeQueryService` is therefore a bad example for you to work from&mdash;I choose to
think of it differently; it's an example that forces you to really think about what's going on, and what parameters you should retain, vs. which ones
you should not retain.


When you're done implementing the first draft, try compiling with: `mvn compile`.  You won't really be able to
test the service beyond "does it compile" without first writing a test, and then implementing the controller as well.

Once you have a first draft that compiles, make a commit with a meaningful commit message:

* Use your initials at the start of your commit message (e.g. `cg` for "Chris Gaucho")
* Separate your initials from your message with a hyphen
* Your message should describe what you did

Examples:

* `git commit -m "cg - added service to get information on zip codes"`
* `git commit -m "cg - correct typo in endpoint url for zip code service"`

Having meaningful commit messages is a component of your grade for this assignment, so please do put some thought into what you write.

As you make commits, push them to your branch, for example:

```
git push origin Chris-Zipcode
```

A few handy commands:
* `git status` shows what branch you are on, among other things
* `git branch -a` shows all current branches
* `git fetch` updates information about branches by pulling new branch names from GitHub

## Step 2.4: Implement the test for the service you were assigned

In the directory `src/test/java/edu/ucsb/cs156/spring/backenddemo/services` you will find tests for the three sample services.  Use these as a model to write a test for your service.

There is no stub; you'll need to create a new file in that directory; be sure to follow the existing naming convention, and put
your test in the same directory as the others.

We'll go over the code for these tests in lecture; and they are covered in the video here:
* [On Youtube](https://youtu.be/mdh9LJ3RSOQ)

Here are also a few notes:

The following code contains the `@Autowired` annotation, which is something you'll see a lot in Spring Boot:
```
    @Autowired
    private MockRestServiceServer mockRestServiceServer;

    @Autowired
    private EarthquakeQueryService earthquakeQueryService;
```

What's going on here is that Spring Boot is doing some magic so that we don't have to manually invoke the constructor like this:

```
 private EarthquakeQueryService earthquakeQueryService = new EarthquakeQueryService(); // We don't typically do this
```

Instead, `@Autowired` asks Spring Boot to go look for an appropriate class with an appropriate constructor, and call it for us *automatically*.

But it's even more than that; having Spring Boot invoke constructors for us instead of us doing it ourselves enables a helpful
design pattern called *Dependency Injection*.  The idea is that in a unit test, we don't want to use the real location API,
because then the test will fail if the API is down, or we don't have an internet connection.  Instead, we set up
a *mock* service that will be a kind of "stand-in" for the real API.

That's what this code does:
```
        String fakeJsonResult = "{ \"fake\" : \"result\" }";

        this.mockRestServiceServer.expect(requestTo(expectedURL))
                .andExpect(header("Accept", MediaType.APPLICATION_JSON.toString()))
                .andExpect(header("Content-Type", MediaType.APPLICATION_JSON.toString()))
                .andRespond(withSuccess(fakeJsonResult, MediaType.APPLICATION_JSON));
```

The  `mockRestServiceServer` will take precedence over the real service that connects to the internet to get the result
of the API call; and this allows us to make sure that the test uses our fake service, so that the outcome is predictable.
In essence we are only testing to make sure that the call is made to the correct endpoint with the correct parameters.

The are pros/cons to this style of testing; we'll discuss in class.

Another important line of code is this one, which you will find as an annotation on the `EarthquakeQueryServiceTests` class:
```
@RestClientTest(EarthquakeQueryService.class)
```

This is necessary to set up the whole mocking of the API endpoint using the `MockRestServiceServer`; the parameter is the service class you are testing.  When creating, for example, the `LocationQueryServiceTests`, you'll need a line like this one:

```
@RestClientTest(LocationQueryService.class)
```

The import that goes along with that is:
```
import org.springframework.boot.test.autoconfigure.web.client.RestClientTest;
```

Run the tests by running `mvn test` and then check the test coverage with:
* `mvn test jacoco:report`
* `mvn test pitest:mutationCoverage`

When the tests pass and you have full coverage, make a commit, and then do a Pull Request for the branch you've created so far.

* Navigate to your repo on the GitHub website
* Go to the Pull Requests tab
* Click to create a new pull request
  - the `base` branch should be `main` (this is where your code will be "pulled into")
  - the `compare` branch should be your feature branch, e.g. `Chris-Zipcode`
  - for the title, put in something like "Add ZipCode Service and Controller"
* For the PR description, enter something like this.  DO NOT leave the description blank.
  It is very important to develop good habits around writing clear PR descriptions.

  The `Closes #5` text is also super important; use the number of the issue that you are
  working on. When you type `Closes #5` it will link the PR to issue 5, and if/when the PR is
  merged, it will automatically close the issue and move it into the Done column on the Kanban board.

  ```
  In this PR, we add an service that wraps the Location API from
  https://nominatim.openstreetmap.org/search.php?q={location}&format=json";

  Closes #5
  ```
* Then, once the PR is created, add your team members as code reviewers
* Do not merge your own PR.  You should wait until another member of your team has code reviewed it, and then they can do the merge.
* Once you've made your PR, drag the card for your issue into the `In Review` column on GitHub
* Link your PR to the issue. One way to do this by putting `Closes #13` in the text of the PR description (where `13` is the issue number.)  There are also ways to link issues with PRs in the GitHub web interface.

Then, make a new branch from the one you have.  For example, if your branch is `Chris-Locations`, while on that branch, do:

```
git pull origin Chris-Locations
git checkout -b Chris-Locations-Controller
```

It is important to *make a new branch* once you've made a pull request; otherwise any commits you make on that branch will affect the pull request.  We want a pull request to not be a moving target; it should be stable so that it can be reviewed.

There times when a reviewer may suggest changes to a branch with an outstanding PR (e.g. `Chris-Locations`); when that happens, we can get those changes into, for example, `Chris-Locations-Controller`, if necessary, in a variety of ways.  We'll cross that bridge when we come to it.
into the later branch

Once you've made a PR for the branch containing your service and tests, and made a new branch from that one,
proceed with  building the controller and the controller test so that you can try out your service.


## Step 2.5: Implement the controller for the service

Before starting to build the controller, be sure you've made a PR for your service and tests, and started a new branch
from that older branch.

A video for steps 2.5, 2.6, and 2.8 appears here: [f22 Team01 Steps 2.5, 2.6 and 2.8](https://youtu.be/QtlirGJjkz4)

In a Spring Boot application, a controller class is one that implements backend endpoints (i.e. provides a web service
on a URL).   You will now implement a controller so that users of your app (in practice, typically, the front end code)
can access the information provided by your service.

The documentation at the staff solution to the lab <{{page.demo_deployment}}> shows the urls of the endpoints you'll be implementing; they
are also shown in this table:


|  Controller                | Endpoint     |
|----------------------------|--------------|
|  `JokeController`          | `/api/jokes/get` |
|  `LocationController`      | `/api/locations/get` |
|  `PublicHolidayController` | `/api/publicholidays/get` |
|  `TidesController`         | `/api/tides/get` |
|  `UniversityController`    | `/api/university/get` |
|  `ZipCodeController`       | `/api/zipcode/get` |


You'll see additional information in the Swagger-ui that is provided by annotations such as these found in the `EarthquakesController`

Please note that the syntax of these annotations may be different in the videos; I just upgraded from
an older version of the software that used different annotation names.  Please use the
ones that are found in the current code base, not the ones in the video.   Here are the new annotation names:

* `@Tag(name="Earthquake info from USGS")`
* `@Operation(summary = "Get earthquakes a certain distance from UCSB's Storke Tower", description = "JSON return format documented here: https://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php")`
`
* `@Parameter(name="distance", description="distance in km from Storke Tower", example="100")`

Please:
* Take note of how those are used in the `EarthquakesController`
* Note the similar information that appears in the Swagger-ui interface of the staff solution here: <{{page.demo_deployment}}>/swagger-ui/index.html>
* Add these annotations in the appropriate places in your own Controller so that the documentation matches that of the staff solution.  This is another component of your grade for this assignment.

To check if your controller endpoint is operational, you can run:

```
mvn spring-boot:run
```

And then visit the `/swagger-ui/index.html` endpoint.  You should then be able to test your service interactively.

When it appears to be working, make a commit, and then we'll move on to the coding part for the individual phase: writing a test for your controller.

## Step 2.6: Write the controller test

In the directory: `src/test/java/edu/ucsb/cs156/spring/backenddemo/controllers` you'll find example controller tests.

Using those as a model, implement a controller test for your controller.

Run the tests by running `mvn test` and then check the test coverage with `mvn test jacoco:report`

## Step 2.7: Deploy your branch to a dev deployment

Next, you are going to create a development deployment (`dev` for short) on Dokku to try out the changes on your branch (instead of only testing on localhost).  It's important to test on
Dokku separately, because sometimes things that work on localhost can break when you deploy
them to Dokku (or vice-versa.)

To create your deployment, login to your team's dokku server and type the following, substituting your  Github id in place of `cgaucho`, and your branch name in place of `Chris-Earthquakes`,
and your team name in place of {{page.sample_team}}

<tt>
dokku apps:create {{page.num}}-cgaucho-dev <br />
dokku git:sync {{page.num}}-cgaucho-dev https://github.com/{{page.org}}/{{page.num}}-{{page.sample_team}} Chris-Earthquakes <br />
dokku ps:rebuild {{page.num}}-cgaucho-dev <br />
</tt>

This builds a separate dokku deployment where you can test your branch before you do
a pull request to make sure it is working properly.  You can also provide a link to this
deployment to other team members that are reviewing your pull request so that they
don't have to switch to your branch on their own machine to test it.

Test the functionality on your new dev deployment.  If it works, then you are ready
for a pull request.

## Step 2.8: Make a Pull Request for your Controller and Tests

* Navigate to your repo on the GitHub website
* Go to the Pull Requests tab
* Click to create a new pull request
  - the `base` branch should be `main` (this is where your code will be "pulled into")
  - the `compare` branch should be your feature branch, e.g. `Chris-Zipcode`
  - for the title, put in something like "Add ZipCode Service and Controller"
* For the PR description, enter something like this.  DO NOT leave the description blank.
  It is very important to develop good habits around writing clear PR descriptions.

  ```
  In this PR, we add an endpoint `/api/zipcode/get` that can be used to get information
  about the location of a particular zipcode.
  ```
* If you have a `dev` deployment (and you should after step 2.7), add a link to it in the PR
  description.  This will help other people on your team to review your code.
* Then, once the PR is created, add your team members as code reviewers
* Do not merge your own PR.  You should wait until another member of your team has code reviewed it, and then they can do the merge.
* Once you've made your PR, drag the card for your issue into the `In Review` column on GitHub
* Link your PR to the issue. One way to do this by putting `Closes #13` in the text of the PR description (where `13` is the issue number.)  There are also ways to link issues with PRs in the GitHub web interface.


# Part 3: Back to the team

## Step 3.1: Review and merge the PRs

Now, as a team, look at one another's PRs.  You should be able to do a code review (we'll demonstrate how that works in class), and approve the PR with the comment `LGTM` (`Looks Good To Me`, or `Let's Get This Merged`).
* Note that "commenting LGTM" is not the same as doing an "Approving Code Review" with the comment `LGTM`.  You need the latter.
* It's also a good idea to try it out. Here are three ways:
  - You can check out the branch (`git fetch; git checkout Other-Branch`), then run `mvn spring-boot:run` to test the code.
  - If the PR author left a link to a dev deployment in the PR, you can test it there.
* When the *team* is satisfied with the code for one of the branches, you can merge that branch into main by clicking the "Merge" button on the PR.

When a PR is merged:
* drag it's card into the Done column on the Kanban board.
* Update your production Dokku instance with these commands: change `6pm-3` to your
  actual team name:

  ```
  dokku git:sync team01 https://github.com/ucsb-cs156-s24/team01-s24-6pm-3 main
  dokku ps:rebuild
  ```

## Step 3.2: Customize the `HomeController`

Now, someone on the team should assign themeslves the issue for customizing the Home Controller and should drag that issue into the "In Progress" column.

Make a branch, `YourName-HomeController` (e.g. `Alex-HomeController`), and
update the code in `HomeController` so that:

* instead of a list of the staff names, there is a list of the names of the people on your team that contributed to this repo
* instead of a link to <tt>https://github.com/ucsb-cs156-{{page.qxx}}/STARTER-team01</tt>, there is a link to your team's private repo (e.g. <tt>https://github.com/ucsb-cs156-{{page.qxx}}/team01-{{page.qxx}}-5pm-1</tt>

Make these changes, test them, and then make a PR for this, and merge it. (Following the usual steps of dragging to the `In Review` column, and then the `Done` column.)

## Step 3.3: Finish the changes to the README.md

Now, someone else on the team should assign themselves the issue for making
changes to the README.

Make a  branch, `YourName-READMEFixes` (e.g. `Alex-READMEFixes`), and
update README.md, so that all of the places that say "TODO" are replaced with the appropriate content.

Make these changes, test them, and then make a PR for this, and merge it. (Following the usual steps of dragging to the `In Review` column, and then the `Done` column.)

When items 3.1, 3.2, and 3.3 are done, and all of the PRs are merged, you are ready to submit for your team on Gauchospace.


# Part 4: Submission

## Step 4.1  Deploy your main branch on Dokku

One last time, be sure that your main branch is up-to-date with Dokku; change `6pm-3` to your
actual team name:

```
dokku git:sync team01 https://github.com/ucsb-cs156-s24/team01-s24-6pm-3 main
dokku ps:rebuild
```

Double check that:

* the running app shows your team members names (i.e. that Step 3.2 above was done correctly)
* that each of the other controllers works properly and returns good results (check this by interactively testing through the swagger-ui interface)

## Step 4.2  One team member submits on Canvas on behalf of the team.

Be sure to follow the instructions:
* Submit a link to the repo, not the running app
* Be sure that the README for the repo has an updated link to the running app
* Be sure that the tests are passing (green check)
* Be sure that the Github pages site is publishing properly.


(End of assignment)

# Instructor Resources


<details markdown="1">
<summary>
Click the triangle for a list of tasks the instructor should do prior releasing this lab.
</summary>

* Create team01 repos using the <https://ucsb-cs-github-linker.herokuapp.com>

  <img width="465" alt="image" src="https://github.com/ucsb-cs156/f23/assets/1119017/434dceb9-77a3-4ce6-9c28-a5faf4e0be1d">

* Set up starter code in the course organization, and update links
* Create a Canvas assignment for team01; update the due dates and publish it
* Create projects for all of the groups. You can find a script for this here:
  * <https://github.com/ucsb-cs156-w24/project-creator/blob/main/scripts/team01-projects.sh>
  You will probably need to make a new copy of that repo for this quarter in this
  quarter's organization and update the scripts.
* After running the script, there are three aspects of setting up the projects that
  are manual:
  * set view to board
  * add "In Review" column
  * change team access to admin
    
    ![set-team-access-admin](https://github.com/ucsb-cs156/s24/assets/1119017/aeff9ce9-4a21-42f4-84ce-cc0cce7a12d4)

* Make sure the app <{{page.demo_deployment}}> is up and running, and is sync'd with the starter code:

  i.e, on dokku-00 for example, do:
  ```
  dokku git:sync team01 https://github.com/ucsb-cs156-s24/PRIVATE-team01 main
  dokku ps:rebuild team01
  ```
* Proofread the instructions in this file, and request that the staff (TAs/LAs do also)
* Consider assigning at least one TA/LA (preferably the one with the least prior experience with the course) to complete the lab in it's entirety to debug the starter code and instructions
* Be sure that the organization settings are set like this, in, for example, <https://github.com/organizations/ucsb-cs156-s24/settings/actions>

  This is needed so that the github actions scripts have write access to the directory.

  <img width="943" alt="image" src="https://github.com/ucsb-cs156/f23/assets/1119017/de8c9efe-7bcd-48a1-97d5-0c0aa68a68db">


  This setting is probabaly also a good idea:

  <img width="972" alt="image" src="https://github.com/ucsb-cs156/f23/assets/1119017/99fead23-d9d0-4373-a435-466c5ef9e752">


</details>

