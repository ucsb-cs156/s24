---
title: Software
description: "What you need to install"
layout: default
parent: info
---

# Software to Install or Configure (and/or update as needed)

Instructions on installing these follow below.

* The latest version of git
* Java 21
* Maven 3.8
* nvm
* Node 16
* npm 8
* Heroku CLI

## Recommmended for Everyone

1. Zoom Client 

   Be sure that you have the *latest* version of the Zoom client.  Older versions may not have some of the features we'll need for this course.
    
   If you click on "About Zoom" inside zoom, you want a version that is 5.9.1 or later.
   
   Download it here: <https://zoom.us/download>

2. UCSB VPN Client (Pulse Secure) (Optional)

   What it does:
   * Reroutes all your network traffic through the UCSB network, so that it appears that
     your machine is directly connected to the UCSB Campus network

   What it allows you to do:

   * Access the textbooks for the course online without having to buy them.
   * Mount your CSIL home directory as a shared network drive using Samba
   * Graphically remote into CSIL


   **Note:** In order to use Pulse Secure, you need to setup DUO (a two factor authentication app).
   Here is a link for the instructions on how to set it up: <https://www.it.ucsb.edu/getting-started-mfa-duo/enroll-push-notification>

   Where to get Pulse Secure:  <https://www.it.ucsb.edu/pulse-secure-campus-vpn/get-connected-vpn>

3. Samba Access to your CSIL home directory (Optional)

   What it does:

   * Mounts your CSIL home directory "as if" it were connected directly to your
     computer.


   What it allows you to do:
   * Click on files on CSIL and open them in software on your own machine
     (e.g. an editor such as Sublime Text, VSCode, or a web browser.)

   Where to get it:
   * You don't have to download anything (though you do need the UCSB VPN Client first)
   * Instead, follow the instructions here:

     | Platform | Text Instructions | YouTube Video Instructions |
     |-|-|-|
     | MacOS | [Text](https://ucsb-cs156.github.io/topics/csil_mount_drive_to_macOs_using_samba/)  | [Video](https://youtu.be/FTlxjhjwbt0) |
     | Windows | [Text](https://ucsb-cs156.github.io/topics/CSIL/csil_mount_drive_to_windows_using_samba.html) | [Video](https://www.youtube.com/watch?v=fgORcrGWBH0) |
     | Linux | (ask staff) | |
     {:.table .table-sm .table-striped .table-bordered}

4. VSCode Text Editor for your local computer

   While `vim` and `emacs` are perfectly fine for the work you may have done in CS16/24/32, when it comes to 
   professional level application development, it's time to graduate to some more professional tools.
   
   We have found that VSCode (a free download for Windows/Mac/Linux) is in the sweet spot between too few features, and too complicated.
  
   If you haven't worked with it before, we suggest you download it and start getting used to it.
   
   What it does for you:
   * Autocompletion
   * Syntax highlighting and checking
   * Automatic import detection
   * Ability to see an entire directory tree at once
   * Search and replace across multiple files
   * and much much more...
   
   Download it here: <https://code.visualstudio.com/download>

Note: If you have **already** tried using VSCode and genuinely feel like you are more of a pro at `vim`, `nano`, `neovim`, or other project/code/text editors, feel free to use whatever is convenient for you. We are suggesting VSCode for ease of all-round use.
  
  
6. Install Java 21 on your local system.  **Please install Java 21**, and NOT Java 8, Java 11, or a preview version of Java 18, 19 or 20.   It won't matter for the `"Hello World"` program in the first week, but when we move on to complex Java applications involving third-party libraries, it will definitely matter.
   
For Mac users, instructions for installing with Homebrew appear below.
  
<!-- 6. Docker

   Docker provides a way for you to run a standardized Linux environment inside another platform (whether that be Windows, Mac, or Linux).  It gives us the ability
   to have a consistent development environment, but running on your own machine.
   
   https://www.docker.com/products/docker-desktop
   
   We'll be recommending Docker as a platform for running the legacy code applications later in the quarter. -->

## Recommmended for MacOS Users

If you have questions about this section, please ask on the [`#help-macos`]({{site.help_macos_link}}) channel on the Slack

1. Command Line Tools XCode for MacOS, including `git`

   On MacOS, `git` typically gets installed as part of the "Command Line XCode Tools" the first time you ask to use it.  To be sure that `git` is installed,
   try typing:
   
   ```
   git --version
   ```
   
   If it shows something like this, you are good:
   
   ```
   git version 2.24.3 (Apple Git-128)
   ```

   Otherwise, you might get a message that you need to install the XCode Command Line Tools.  In that case, please just follow the instructions given.

2. Brew (package manager)

   For MacOS, we'll be installing several packages for Java and JavaScript (node) development.  
   In many cases, installing those is easier if you *first* install the brew package manager.
   
   To install `brew`, visit <https://brew.sh/> and follow the instructions.
   
3. Java 21
   
   To install Java with homebrew, use:
   
   ```
   brew update
   brew install openjdk@21
   ```
   
   After this command finishes executing, there will be a line printed in the terminal that looks like this:
   ```
   sudo ln -sfn /usr/local/opt/openjdk/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk.jdk
   ```
   
   You will need to find this line in the text outputted by `brew install openjdk@21` and run it in the terminal. It should be near the end of the output. 
  
   The command pasted above **will not work**; it is an example provided so you know what you're looking for. This links the software you just installed with the path **your** computer expects – some macs are different and will have different file structures. That's why you must use the command outputted by `brew install openjdk@21`.

   To check if you now have Java 21, open a new Terminal window and do:

   ```
   java -version
   ```

   If it worked, you should see something like this:

   ```
   # java -version
   openjdk 21.0.1 2021-10-19
   OpenJDK Runtime Environment Homebrew (build 21.0.1+1)
   OpenJDK 64-Bit Server VM Homebrew (build 21.0.1+1, mixed mode, sharing)
   ```

4. Maven

   After installing Java 21, you can use `brew` to install Maven:

   ```
   brew update
   brew install maven
   ```

   Or if you already have Maven installed, do this to upgrade your version to the latest one:

   ```
   brew update
   brew upgrade maven
   ```

   Then to check that it is installed, do:

   ```
   mvn --version
   ```

   Be sure that you have Maven version 3.8 or higher, as Java 21 requires this version to work.

   When you type `mvn --version` if you are getting a version of Java other than Java 21, the fix is described
   in [this article](https://euedofia.medium.com/fix-default-java-version-on-maven-on-mac-os-x-156cf5930078) but that article is a little out of date, so here's the updated instructions:

   To update the maven configuration, file, edit this file; note that the version number may be different
   by the time you are reading these instructions:

   ```
   vim /opt/homebrew/Cellar/maven/3.9.6/bin/mvn
   ```

   In that file, change the line that starts with `JAVA_HOME=` to this:

   ```
   JAVA_HOME="${JAVA_HOME:-$(/usr/libexec/java_home 21)}" exec "/opt/homebrew/Cellar/maven/3.9.6/libexec/bin/mvn" "$@"
   ```
   Or if you find that the above does not work after typing `mvn --version` then try:
    ```
   JAVA_HOME="${JAVA_HOME:-/usr/local/opt/openjdk@21/libexec/openjdk.jdk/Contents/Home}" exec "/usr/local/Cellar/maven/3.9.6/libexec/bin/mvn" "$@"
   ```
   For Apple Silicon (M1/M2/M3), try replacing the first `openjdk` with `openjdk@21`, like this:
    ```
   JAVA_HOME="${JAVA_HOME:-/opt/homebrew/opt/openjdk@21/libexec/openjdk.jdk/Contents/Home}" exec "/opt/homebrew/Cellar/maven/3.9.6/libexec/bin/mvn" "$@"
   ```
    
   Again, you may need to adjust the version number `3.9.6` to whatever your version of Maven is.  After doing
   this, if you type `mvn --version` it should show Java 21, like this:

   ```
   Apache Maven 3.9.6 (bc0240f3c744dd6b6ec2920b3cd08dcc295161ae)
   Maven home: /opt/homebrew/Cellar/maven/3.9.6/libexec
   Java version: 21.0.9, vendor: Homebrew, runtime: /opt/homebrew/Cellar/openjdk@21/21.0.9/libexec/openjdk.jdk/Contents/Home
   Default locale: en_US, platform encoding: UTF-8
   OS name: "mac os x", version: "14.1", arch: "aarch64", family: "mac"
   ```
   
4. nvm, Node, and npm

   It is recommended to install Node and npm through Node Version Manager (nvm). The instructions for installing this are the same as those for Linux and WSL users, so please follow the instructions listed there.

   [Install nvm and Node on WSL](https://ucsb-cs156.github.io/topics/windows/windows_wsl.html#install-nvm-and-node-on-wsl)

   [Update npm on WSL](https://ucsb-cs156.github.io/topics/windows/windows_wsl.html#update-npm-on-wsl)

## Recommmended for Windows Users

Install Windows Subsystem for Linux.

It turns out that almost everything in terms of installing software (Java, Maven, Node, etc.) is easier under Linux than under native Windows.
Therefore we strongly suggest that if you have a Windows environment, you install the Windows Subsystem for Linux (WSL) and then follow the 
instructions under Linux/WSL.
   
If you are unable to install WSL because of limitations on your machine, please reach out to the course staff via Slack using the [#help-windows]({{site.help_windows_link}}) channel on Slack. In that case, we will try to find an alternative for you.
 
## Recommended for Ubuntu Linux / WSL Users
 
Instructions for installing Windows Subsystem for Linux (WSL), as well as environment setup instructions for Ubuntu systems, is available here: [https://ucsb-cs156.github.io/topics/windows_wsl/](https://ucsb-cs156.github.io/topics/windows/windows_wsl.html)

Native Ubuntu users (those not using Ubuntu through WSL) can skip the Windows-specific setup and go directly to [Install / Update Git on WSL](https://ucsb-cs156.github.io/topics/windows/windows_wsl.html#install--update-git-on-wsl) and follow all instructions from there on.

The following programs will be installed in the above guide:

* The latest version of git
* Java 21
* Maven 3.8
* nvm
* Node 16
* npm 8
* Heroku CLI

If you're using a Linux distribution that is not Ubuntu (or a similar Debian-based distribution with access to `apt`), the commands listed in the setup guide linked above may not work. The staff cannot provide support on finding equivalent commands for your desired distribution, but community resources such as Stack Overflow can help here.
