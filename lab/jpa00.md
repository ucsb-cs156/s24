---
description: Getting Started
assigned: 2024-04-03
due: 2024-04-10 23:59
layout: default
title: jpa00
nav_order: 100
ready: false
layout: default
parent: lab
signup_app: https://ucsb-cs-github-linker.herokuapp.com/
slack: https://ucsb-cs156-s24.slack.com
course_org: https://github.com/ucsb-cs156-s24
course_org_name: ucsb-cs156-s24
starter_repo: https://github.com/ucsb-cs156-s24/STARTER-jpa00
course_software: https://ucsb-cs156.github.io/s24/info/software.html
---

This assignment is `jpa00`, i.e "Java Programming Assignment 00".

If you find typos or problems with the lab instructions, please report these via Slack:
* When class is in session (e.g. lecture or discussion) please use `#help-lecture-discussion`
* At other times, please use `#help-jpa00`, or if it is a configuration problem, use one of these channels as applicable:
  - `#help-macos`
  - `#help-windows`
  - `#help-wsl`

# Disk Quota Problems?

A common problem that CS156 students run into when working on CSIL is the error `disk quota exceeded`.  If you run into that, 
this article can help: <https://ucsb-cs156.github.io/topics/CSIL/csil_disk_quota.html>

# Goals

This lab checks that you can succesfully edit, compile, run and submit a simple
`Hello.java` to Gradescope for grading.

# Why so picky about the version?

To be honest, for this first lab, the version probably doesn't matter.

But later in the course, we'll be dealing with the Spring framework, which is a very complex Java framework with dozens of external dependencies.   In this case, version matters a lot!

Most large Java frameworks only target *Long Term Support (LTS)* versions of Java, not intermediate versions.  That means Java 11, or 17 or 21. Versions that are not LTS such as 22 and 23 may have incompatibilities that are not well documented or understood, and result in obscure, difficult to resolve bugs.

More info here: <https://ucsb-cs156.github.io/topics/java/java_versions.html>

# How to install Java 21 and Maven on your own machine

Note: these instructions were current as of S25 *as far as we know*.   Things change every quarter&mdash;sometimes even from day to day&mdash;and the only way we find out is when students try things and tell us.  (We don't have the bandwidth to try all of the instructions on every possible OS version combination.)

* For MacOS, this is fairly straightfoward; see instructions [here]({{ page.course_software }}).  If you need help, ask on the `#help-macos` channel on the Slack.
* For Windows, we recommend installing the Windows Subsystem for Linux (WSL), and then following the instructions for installation of Java 17 from [this page]( {{ page.course_software }} ).
  * For help with installing WSL, you can ask on the `#help-windows` Slack channel
  * For help *after* you've installed WSL, use the `#help-linux-wsl` Slack channel
* For Linux, there are instructions on  [this page]({{ page.course_software }}). that apply to Debian/Ubuntu like systems.  If those don't work for you, ask the staff for help on the `#help-linux-wsl` Slack channel


# Something for everyone to learn

Note that even if you have done Java programming before, **there
may be a few things about this `Hello.java` program that may be
unfamiliar to you**.  These have to do with setting us up for real world
programming practices used in large software projects.

* Rather than compiling with command line tools such as `javac` and running
  the program with the `java` command, we'll be using a package and build
  manager called *Maven*.  For a small `Hello World` type program,
  this will seem like overkill; but it will set us up for being able to
  manage much larger projects.
* We are setting our code up in a GitHub repo right from the start.
* We are going to be following the directory conventions required
  by Maven.  So it's important to have the correct directory structure
  within the GitHub repo.

There a few details, but they are all straightforward.  It shouldn't take
very long, and if it goes well, you'll be able to start on the next lab
right away.

That one may actually take quite a bit more work.


Step 0: Getting oriented
========================

Even if you aren't using CSIL for this assignment, it's still a good idea to make sure your CSIL account is working and configured.

If you've used CSIL before, there continue to be ongoing changes
to how we interact with CSIL.    So please read this carefully.

1. You should have a College of Engineering (CSIL) Account.   If you don't,
   you can create one by visiting <https://accounts.engr.ucsb.edu>

   If this is your first Computer Science course at UCSB, you'll definitely
   need to do that.

3. If you've ssh'd to `csil.cs.ucsb.edu` before, but haven't logged into that
   site recently, you might find that you get
   an error message when trying to login due to stale values in a file
   ion your system called `known_hosts`.  The old
   entry in that file for `csil.cs.ucsb.edu` will need to be deleted,
   since the `hostid` value has changed over the summer.

   Otherwise, any time you connect to `csil.cs.ucsb.edu`, the connection
   may be immediately closed.

   The exact location of this file may be different on different systems,
   but its likely in a directory called `.ssh` under your home directory.
   Keep in mind that `.ssh` may be a hidden file.

   So the command you need might be something like this:

   * `vim ~/.ssh/known_hosts` to edit the file and remove the line for `csil.cs.ucsb.edu`
   * `emacs ~/.ssh/known_hosts` if you prefer that editor
   * `rm ~/.ssh/known_hosts` if you just want to delete the file completely.

   Deleting that file will just mean that the first time you connect to any particular system, you'll be asked whether you *really* want to connect to that system, and store it's identifying information in your `known_hosts` file, and you'll have to respond `yes`.

3. If you already have used an SSH client before, you can continue using
   that same client, but specify `csil.cs.ucsb.edu` as the hostname.

   If you haven't used an ssh client before, consult these pages for
   hints:
   * Windows: <https://ucsb-cs156.github.io/topics/CSIL/csil_via_ssh_from_windows.html>
   * MacOS: <https://ucsb-cs156.github.io/topics/CSIL/csil_via_ssh_from_macos.html>
   * ECI's article with guides for Windows, Mac and Linux: <https://doc.engr.ucsb.edu/pages/viewpage.action?pageId=5112076>

   There are also channels on the course slack, <{{page.slack}}>, for
   `#help-windows` and `#help-macos`.  Use the `#help-linux-wsl` if you need
   help for a system other than Windows or Mac (e.g. Linux, Chromebook, etc.)

4. Ideally, you will already
   know the following things from previous courses (CMPSC 16, 24, 32).  It is possible that if you are joining UCSB for the first time in this course, some of this may be unfamiliar to you.   The rest of these instructions will assume you know how to do the items in the list below. If not, then let a member of the course staff know,
   and we'll point you to resources
   where you can come up to speed.

   -  knowing how to use a **basic
      text editor such as emacs or vim** to edit files.  (Here, for example, is some [basic instruction on vim](https://ucsb-cs156.github.io/topics/vim)
)
   -  knowing basic Unix/Linux
      commands to create directories, change directory, manipulate files, i.e. commands such as: `mkdir`, `cd`, `pwd`, `mv`, `rm`, `ls`.
   If those topics are new to you, please reach out to the instructor to let them know, and ask for pointers to resources where you can
   study up on these skills.

5. We strongly encourage the use of VSCode as an editor this course.   For this assignment, it will not matter what editor you use,
   but in future assignments, the use of an IDE will become more important.  We'll discuss this more in lecture.

# The rest of the lab: Step-by-Step

## Step 1: If you are on CSIL, configure your account for Java 17

If you are not working on CSIL
* You should have checked that you have Java 17 and Maven by following the steps here: <{{ page.course_software }}>
* If so, you can skip to Step 2.

Otherwise, login to your CSIL account, and start by checking whether `JAVA_HOME` is already defined. Type `echo $JAVA_HOME`

If it is *not* already defined, it should look like this:

Good:
```
[pconrad@csilvm-03 STARTER-jpa00]$ echo $JAVA_HOME

[pconrad@csilvm-03 STARTER-jpa00]$
```

If instead it looks like this, then you have an old definition of `JAVA_HOME` associated with your account, and we'll need to update it.

Bad:

```
[pconrad@csilvm-03 STARTER-jpa00]$ echo $JAVA_HOME
/usr/lib/jvm/java-11-openjdk
[pconrad@csilvm-03 STARTER-jpa00]$
```
Next, we need to figure out where your java-17 JVM is stored. For **MOST** users, this is `/usr/lib/jvm/java-17-openjdk`. However, it is good practice to check what it is called by:
```
cd /usr/lib/jvm/
ls
```
You should now see `java-17-openjdk` or similar (ex. `java-17-openjdk-arm64`). If it is **NOT** called `java-17-openjdk` exactly, replace `/usr/lib/jvm/java-17-openjdk` in the next set of commands with what you see in your `/usr/lib/jvm/` directory.
What you want is to add these lines to your `~/.bash_profile` file:

```
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk
export PATH=$JAVA_HOME/bin:$PATH
```

If you already had a definition of `JAVA_HOME` it was likely in `~/.bash_profile`, but to be sure, check also in `~/.bash_login` and `~/.bashrc` and remove any old versions of the definition of `JAVA_HOME`.

After making this change, logout and log back in again, and check `echo $JAVA_HOME`. It should now say: `/usr/lib/jvm/java-17-openjdk`

The next thing to check is that when you type `javac --version` for the Java compiler, that you get version 17, like this:

```
[pconrad@csilvm-03 STARTER-jpa00]$ javac --version
javac 17.0.1
[pconrad@csilvm-03 STARTER-jpa00]$
```

Then check that the Java Virtual Machine (the `java` command) gives you the correct version:

```
[pconrad@csilvm-03 STARTER-jpa00]$ java --version
openjdk 17.0.1 2021-10-19
OpenJDK Runtime Environment 21.9 (build 17.0.1+12)
OpenJDK 64-Bit Server VM 21.9 (build 17.0.1+12, mixed mode, sharing)
[pconrad@csilvm-03 STARTER-jpa00]$
```

Finally, check that when you run `mvn --version` which is the command for Maven, that it is pointing to Java 17 as your Java version.
* Notice the line in the output that says `Java version: 17.0.1, ...`
* If it says something else, that's a problem that needs to be fixed.

```
[pconrad@csilvm-03 STARTER-jpa00]$ mvn --version
Apache Maven 3.6.3 (Red Hat 3.6.3-8)
Maven home: /usr/share/maven
Java version: 17.0.1, vendor: Red Hat, Inc., runtime: /usr/lib/jvm/java-17-openjdk-17.0.1.0.12-13.rolling.fc34.x86_64
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "5.15.12-100.fc34.x86_64", arch: "amd64", family: "unix"
[pconrad@csilvm-03 STARTER-jpa00]$
```

## Step 2: Get setup with github and add yourself to our organization

I'm commenting this step out, because for s24 all students have already done this step.

<!--   COMMENTED OUT !!!!

We will be using github.com in this course. We have created an
organization called {{site.github_org}} on github.com where you can
create repositories (repos) for your assignments in this course.

The advantage of creating private repos under this organization is
that the course staff (your instructors and TAs) will be able to see
your code and provide you with help, without you having to do anything
special.

To join this organization, you need to do three things.

1. If you don't already have a github.com account, create one on the
"free" plan. Visit [https://github.com/](https://github.com/)

2. If you don't already have your `@ucsb.edu` email address
associated with your github.com account. go to "settings", add that
email, and confirm that email address.  (If you have an `@umail.ucsb.edu` address registered there, that also works.)

3. Visit our Github Sign Up Tool at <{{page.signup_app}}>.   Navigate to <{{page.signup_app}}>.  Login with your github.com account. Click "Home", find this course ({{site.course}}, {{site.qtr}}), and click the "Join course button".   That will automatically send you an invitation to join the course organization on github.

4. There should be a link to the invitation for the GitHub organization for this course (<https://github.com/{{site.github_org}}>). Click on the invitation link and accept it. You can also go straight to <https://github.com/{{site.github_org}}> and see the invitation there (if you're logged in). Accept the invitation that appears in your browser (from step 3) or log into your account on [https://github.com/](https://github.com/) to accept the invitation.

END COMMENTED OUT!!!   -->


## Step 3: Get setup with gradescope

We will use gradescope to grade all your homeworks, exams and lab/programming assignments. I have added everyone enrolled in the course to Gradescope by syncing the Canvas roster.   You should have received an email notification with instructions about logging into gradescope. Once you follow the instructions to set your password, you should have access to our course on Gradescope. You should see {{site.course}} in your {{site.quarter}} courses.

The lab assignment {{page.title}} should appear in your Gradescope dashboard in {{site.course}}. You will need to submit your code for {{page.title}} using this page.

## Step 4: Set up your local system for Java 17 and Maven

If you are doing this lab on CSIL then you don't have to do this step for now.

However, we *strongly encourage you do to this step sooner rather than later*.  The sooner you get a Java 17 + Maven environment working on your local system, the easier time you will
have with the rest of the work in this course.

What you'll need:

* git
* Java 17 JDK
* Maven

There are instructions [here]({{ page.course_software }}) for various platforms.


## Step 5: Configure your machine for git/GitHub

Whether you are working on CSIL, or on your own machine, you need to configure the environment you are working in for access to git/GitHub.

We want to be able to use `git` and GitHub with ssh links, so we need to set up public-key/private-key pairs.

We also want to set up `git` so that it records our commits properly.

1. `git` configuration: [Detailed Instructions](https://ucsb-cs156.github.io/topics/CSIL/csil_git_configuration.html)


2.  Configure ssh keys for git
    - Detailed instructions: [Configuring your ssh key for Github.com](https://ucsb-cs156.github.io/topics/GitHub/github_ssh_keys.html)


3.  If you are brand new to git and github, review a few basic facts about git and github.com
    - <https://ucsb-cs156.github.io/topics/git/git_overview.html>


## Step 6: Finding your jpa00 repo on GitHub

Open a web browser and login to GitHub, then navigate to the course organization page, <{{page.course_org}}>.

You should see that there is a private repo in this organization called `jpa00-yourGithubId`, where `yourGithubId` is replaced with your GitHub id.  This is the repo
that you'll be using for this assignment.

This is currently an empty repo.  In the next step, we'll clone this empty repo into a directory, either on your CSIL account, or on your local system.

## Step 7: Cloning the repo


1. If you are working on CSIL, login to your CSIL account,  create a `~/cs156` subdirectory, and change directory into it.  Otherwise, create a directory somewhere on your machine for cs156, and cd into that.

   ```
   mkdir ~/cs156
   cd ~/cs156
   ```

   You can actually use any directory you like, but for consistency, we'll refer
   to `~/cs156` throughout the rest of
   the instructions.

2. Now, go to the `github.com` web page, and find your `jpa00-userid` repo. The page should look something like this:


   <img width="513" alt="jpa00-cgaucho-50" src="https://user-images.githubusercontent.com/1119017/230218643-28916fd4-42ac-4be7-80e6-5b517ac6654e.png">

   You should see a button for `SSH`;
   select that button.  Then there is a button to copy the URL shown;
   click that to copy the URL.

3. Now type this command, replacing
   `url` with the url that you copied.

   That `url` should be something like
   <tt>git@github.com:{{page.course_org_name}}/{{page.title}}-cgaucho.git</tt> but with your GitHub id in place of <tt>cgaucho</tt>.

   ```
   git clone url
   ```

   You'll will see a warning message that you are cloning an empty repo; that's normal.


   <tt>Cloning into {{page.title}}-cgaucho...<br />
   warning: You appear to have cloned an empty repository<br /></tt>


4. If you use the `ls` command, you should now have a subdirectory called <tt>{{page.title}}-cgaucho</tt> (except <tt>cgaucho</tt> will be your GitHub username.)  Use
   a `cd` command to change directory
   into that directory, e.g.


   <tt>cd {{page.title}}-cgaucho</tt>


   An `ls -a` should reveal an empty
   directory except for the `.git` subdirectory indicating that this is a GitHub repo.

   ```
   % ls -a
   .	..	.git
   %
   ```

   We are now ready to pull in some starter code.

## Step 8: Locate the starter code.

First, let's take a look at this remote on GitHub, here:

* <{{page.starter_repo}}>

You should see that the `README.md` for this repo has an explanation of the contents of the starter code.  Read though this explanation to learn more about:
* Maven
* the `pom.xml`
* the required directory structure

Next, we'll add this starter code as a second *remote* for our repo.

## Step 9: A remote for starter

If you've used `git` before, you
may be familiar with the command:

```
git pull origin main
```

The word `origin` in this case refers to a *remote*, that is a repo that lives somewhere out there on the network.

The word `main` refers to the default branch of the repo.  The default branch of GitHub repos recently changed from `master` to `main`; we'll be using `main` throughout this course.

If you type the following command, you'll see that `origin` is defined as a remote for the repo that you cloned from.  Your output will look similar, except that you'll have your GitHub in place of `cgaucho`:

<tt>
% git remote -v<br />
origin	git@github.com:{{page.course_org_name}}/{{page.title}}-cgaucho.git (fetch)<br />
origin	git@github.com:{{page.course_org_name}}/{{page.title}}-cgaucho.git (push)<br />
% <br />
</tt>

Now, we are going to add a second remote.  This remote will use the URL for the starter code.

The image below shows how to copy that URL: (1) Click the green `Code` button.  (2) Select `SSH` to choose that as the network protocol for the URL (3) Click the icon to copy the URL to your clipboard.


<img width="192" alt="starter-ssh-url-50" src="https://user-images.githubusercontent.com/1119017/229932825-e2ce51b9-acc3-4b45-b314-50174a211d26.png">


Then, use this command to add a remote called `starter` for the starter code repo:

```
git remote add starter paste-url-here
```

After this command, use `git remote -v` to list all your remotes. Your output should look like this (except your GitHub id in place of `cgaucho`):

<tt>
% git remote -v<br />
origin	git@github.com:{{page.course_org_name}}/{{page.title}}-cgaucho.git (fetch)<br />
origin	git@github.com:{{page.course_org_name}}/{{page.title}}-cgaucho.git (push)<br />
starter	git@github.com:{{page.course_org_name}}/STARTER-{{page.title}}.git (fetch)<br />
starter	git@github.com:{{page.course_org_name}}/STARTER-{{page.title}}.git (push)<br />
%
</tt>

## Step 10: Pull Starter Code into your Repo

The next step is to pull the starter code into your repo, and then push
that code to your origin repo on GitHub.

Here are the three commands:

```
git checkout -b main
git pull starter main
git push origin main
```

After these three commands, go look at your repo on GitHub, i.e. the repo at this url (but substituting your GitHub id for cgaucho:)

* <https://github.com/{{page.course_org_name}}/{{page.title}}-cgaucho>

You should see that instead of an empty repo, you now have a copy of the starter code.

The starter code should compile and run, and can even be submitted to Gradescope for a grade.   Of course, it won't be for full credit, but we can at least make sure that the mechanisms are working.  So let's give it a try.

## Step 11: Compile and run the Starter code

To compile the starter code, return to a shell prompt in the directory where your cloned your repo.  You should see, when you type `ls`, that
the file `pom.xml` is in the current directory.  For best results, you should always run Maven from this directory.

To compile type `mvn compile`.

* If you see the message `The JAVA_HOME environment variable is not defined correctly...` plus a few more lines of output, see [this link](https://ucsb-cs156.github.io/topics/maven/maven_faq.html) for a fix.
* Otherwise, you should see no error messages
* There may be warning about missing `resources` and `UTF-8 encoding`, but you can safely ignore those for now.  If you are curious, see the the section "Warnings you May be able to Ignore" on [this page](https://ucsb-cs156.github.io/topics/maven/maven_hello_world.html).

Then, type `mvn package`.  You should see a lot of output, but somewhere in that output, something like this:

```
 [INFO] Building jar: target/hello-1.0.0.jar
```

That indicates that you have built a `.jar` (or Java Archive) file.  This file is a compressed archive of all of the compiled Java code from your program.  You can run it with this command:

```
java -cp target/hello-1.0.0.jar Hello
```

You should see output like this:

```
% java -cp target/hello-1.0.0.jar Hello
This is the wrong output!
%
```

* Note: If you are working on CSIL and see this instead:
  ```
  Error: A JNI error has occurred, please check your installation and try again
  ...
  ```
  followed by many lines of additional output, then try this instead:
  ```
  $JAVA_HOME/bin/java -cp target/hello-1.0.0.jar Hello
  ```
  This assumes you've done the [fix described here](https://ucsb-cs156.github.io/topics/maven/maven_faq.html) to define `JAVA_HOME` to point to Java 17.




The line `This is the wrong output!` is being produced by the line of code:

```
        System.out.println("This is the wrong output!");
```

You should eventually change this line to produce the correct output.
But, don't do that just yet.  Let's first see what happens when you submit a program with errors in it to Gradescope.



## Step 12: Submit incorrect Java code to Gradescope

In this step, we'll see what happens when you submit two incorrect program to Gradescope.  We aren't grading this step, so you *could* skip it, but we strongly encourage you to do it anyway, because it's important to be able to understand how the autograders work on a simple case before dealing with a more complex case.


First, we'll submit the starter code "as is" to Gradescope.  Gradescope will be expecting a program that produces, as it's output `Hello, World!` (followed by a newline).

Instead, your code currently produces: `This is the wrong output!` followed by a newline.

We want to see what the Gradescope output looks like in that case.

To submit to Gradescope, navigate to:
<https://gradescope.com>.

You should have an account invitation in your email.  If you don't, ask an instructor, TA or mentor for assistance.

To submit your work, you should be able to click on the GitHub link in Gradescope, and locate your repo.  The first time you do this, it may take a while; be patient before giving up.   If it still doesn't work after a while, you can either (a) ask the staff for assistance, or submit a zip file as an alternative.

* For instructions on submitting a Zip file, see: [Gradscope Zip Submission](https://ucsb-cs156.github.io/topics/gradescope/gradescope_zip_submission.html)


After you submit, it will take some time for Gradescope to process your submission.  Once it's processsed, you should see output similar to this:

<img width="294" alt="jpa00-gs-starter-code-50" src="https://user-images.githubusercontent.com/1119017/229932774-25157e0d-5911-4df9-877e-7d35d9a01c00.png">


The most important part is this:

```
FAILED:
expected:<[Hello, World]!
> but was:<[This is the wrong output]!
>
```

Note that it tells you exactly what was different between the expected and actual output (the part in `[]`).  The `!` is the same in both parts, so it is outside the `[]`.


Once you've understood this output,
let's move on and see what happens when you submit code with a syntax error.

Go into the file `src/main/java/Hello.java`, and remove the semicolon at the end of the statement:

```
 System.out.println("This is the wrong output!");
 ```

 So that it reads:

 ```
  System.out.println("This is the wrong output!")
 ```

This, of course, has a syntax error.

Try using `mvn compile` and see what happens when you submit this.

Then, commit this change to Github.

(Normally, we would NOT push code that has a syntax error, but for purposes of this experiment, we will.)

Add/Commit/Push with these commands:

```
git add src/main/java/Hello.java
git commit -m "commit code with syntax error to test autograder"
git push origin main
```

Now, submit to Gradescope again.  You should see output like this:

* At the right hand side, you'll see the following:


  <img width="162" alt="mvn-compile-failed-50" src="https://user-images.githubusercontent.com/1119017/229932738-b85ff1a3-1dac-43d6-899f-92f1cedb7dd3.png">

  This is how you'll know that the Maven compile failed on Gradescope.

  But where can you see what went wrong?  Read on:


* Look in the main window, for
  output with `mvn compile failed` at the top.  It will probably be very
  long (the whole output is not shown):

  <img width="414" alt="mvn-compile-failed-top-50" src="https://user-images.githubusercontent.com/1119017/229932691-f8411e99-3131-4062-b504-387e0cd55f5f.png">

  This output is really long because it shows every single file that was
  downloaded by Maven in order to do it's work (which is quite a few).  However,
  the really useful output is at the bottom, so you have to scroll down a while:

* Look at the bottom of this section, and eventually you should see:

  <img width="412" alt="mvn-compile-failed-bottom-50" src="https://user-images.githubusercontent.com/1119017/229932642-703fbdd2-022e-436c-81ad-5a74c3d82b71.png">


  Here, finally, you can see what's wrong with the compile (the missing semicolon).

Now that you understand what a failed compile looks like, let's finally fix the code
and finish the lab.

## Step 13: Submit correct Java code to Gradescope

Now, fix the code so that it produces the correct output.  Change the file `src/main/java/Hello.java` so that the `System.out.println` method call reads:

```
        System.out.println("Hello, World!");
```

Test this locally by compiling and running the code:

```
mvn compile
mvn package
java -cp target/hello-1.0.0.jar Hello
```

You should see the correct output, `Hello, World!`.

Now, commit this change:

```
git add src/main/java/Hello.java
git commit -m "correct the output"
git push origin main
```

Then submit to Gradescope again.


Once you see that you have a score of 100 for {{page.title}} on Gradescope, you are *done* with the *required* work for {{page.title}}. However, you are encouraged to look at the README.md file in your lab00 repo and go through the explanation of the files in the repo.  Some of this may be review, but some if it may be new to you, especially if you have not used Maven before.   We'll be using Maven throughout the course, so it's good to get familiar with how Maven works in this very small `Hello World` program before we see a more complex example.



# Staff Info

<details markdown="1">
<summary markdown="1">Information in this section is for staff.  You can click on the triangle to see the staff info if you like.</summary>

## Before this lab

* Set up STARTER-jpa00
* Set up autograder on Gradescope
* Create jpa00 student repos (student access is admin, visibility is private as shown below)

<img width="343" alt="image" src="https://github.com/ucsb-cs156/s24/assets/1119017/8562f4e8-fbe0-4fa4-8fe4-016e9d548d75">

# Common issues

* Disk quota issues.  Refer them to <https://ucsb-cs156.github.io/topics/CSIL/csil_disk_quota.html>
  
</details>
