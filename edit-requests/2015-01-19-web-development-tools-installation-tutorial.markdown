---
layout: post
title:  "Web Development Tools: Installation Tutorial"
date:   2015-01-19 17:04:00
categories: [tutorial, git, rvm, ruby, nodejs, homebrew]
tags: [tutorial, git, rvm, ruby, nodejs, homebrew]
permalink: /blog/:title
---

## Introduction
The following tutorial will help you install [Homebrew][homebrew], an awesome package-manager for OS X, [RVM][rvm] and [Ruby][ruby], and [NodeJS][nodejs]. These tools will help you get started on having a computer configured for web development.

**Note**: Before you continue, do remember to back up your computer just in case some system files are harmed. I don’t think the following steps will do that, but you never know.

## Dependencies
Before you start installing Homebrew and Ruby, you need to make sure you have have Xcode and Xcode command line tools installed.

### Xcode
Download Xcode from the Mac App Store [here][xcode]. Once downloaded, open it up and navigate to Preferences —> Downloads —> Components. Find “Command Line Tools” and click “Install”.

Alternatively, you can install the Command Line Tools without needing to download the full installation of Xcode, by using Terminal.

To do so, open up Terminal, which can be found in Applications —> Utilities —> Terminal (or just use Spotlight). Inside Terminal , type
{% highlight sh %}
$ xcode-select —install
{% endhighlight %}

A pop-up window should appear asking you whether you want to install the tools, click “Install”.

After installation using either method, open up Terminal and enter the following command to verify the tools were installed correctly.
{% highlight sh %}
$ gcc —version
{% endhighlight %}

If the terminal prints back something like, “Configured with: —prefix=/Xcode.app/…”, then you are ready to move on to the next step.

If the terminal did not print out something like that or if it printed some sort of error, follow the previous steps again or try to debug the problem.

## Homebrew
Ok, now on to [Homebrew][homebrew]. Homebrew is an awesome tool for Macs because it manages all of your open-source installed packages and allows for easy updates, reinstalls, and uninstalls.

Type the following command into the Terminal.

{% highlight sh %}
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
{% endhighlight %}
**Note**: Before typing this command in, check the Homebrew website to verify that this is the command to install the package.

After the installation completes, Terminal should print 
>Installation successful!

If it does not, google search the error message and debug the problem.

Next, verify that Homebrew is able to start downloading packages by entering this command into the Terminal.

{% highlight sh %}
$ brew doctor
{% endhighlight %}

If the system prints back,
>Your system is ready to brew

then move on to the next step. If not, google search the error and try to debug the problem. Usually, Homebrew will tell you how to fix the error when you run 
{% highlight sh %}
$ brew doctor
{% endhighlight %}

## Install Git
If you don’t know what [Git][git] is, you’re missing out. Git is a version control system that helps you manage your code, collaborate with developers more easily, and reverse some unwanted changes. Also, git works well with any file, not just code. Many writers use it for more effective revision tools.

To install Git, type the following commands into Terminal.
{% highlight sh %}
$ brew update
$ brew install git
{% endhighlight %}

After installation, type in
{% highlight sh %}
$ which git
{% endhighlight %}
to verify that your Mac is pointing to the installation Homebrew did.

If terminal prints 
>/usr/local/bin/git

then you successfully installed git using Homebrew. If it does not show this, google how to fix this error and try to debug it.

Next, make sure you configure Git, so you can use it to commit and clone without problems.

Enter the following commands into the Terminal, changing the name and email address when appropriate.

{% highlight sh %}
$ git config --global user.name "Your Full Name"
$ git config --global user.email "Your Email Address"
{% endhighlight %}

## Install RVM and Ruby
[RVM][rvm] will act as your Ruby Version Manager for your computer. This is important to have because it allows you to switch between multiple versions of Ruby and different gems when working in a different environment. Also, RVM makes it easier to stay updated with the latest stable release of Ruby, and makes sure the latest Ruby installation does not affect the system-installed Ruby.

You can find some different installation options at their website [here][rvm-install]. But the one that installs RVM and the latest stable version of Ruby is the following.

Type this command into Terminal:
{% highlight sh %}
$ \curl -sSL https://get.rvm.io | bash -s stable --ruby
{% endhighlight %}

After the installation is complete, quit Terminal completely (Command-Q), and open it up again.

Type in the following command to verify that RVM was installed properly.
{% highlight sh %}
$ type rvm | head -1
{% endhighlight %}

If the terminal prints, 
>rvm is a function

then RVM was successfully installed.

Finally, make sure RVM is configured to use the latest Ruby for current and future shell sessions.

Type in:
{% highlight sh %}
$ rum use 2.2.0 —default
{% endhighlight %}

Then, verify by typing in:
{% highlight sh %}
$ ruby -v
{% endhighlight %}

If it prints back the latest stable version of Ruby, then you are all set.

## Install NPM and Node.js
[Node.js][nodejs] is an important tool for any web developer. Node.js allows you to write any Javascript code and run it locally on your computer free of any web browser.

However, to use Node.js, you need some Node.js package manager to help you with your plugins and code.

Install Node.js and NPM using Homebrew.

Type into Terminal:
{% highlight sh %}
$ brew install node
{% endhighlight %}

## Conclusion
That’s it! You’re done. Now you have successfully configured your computer to work well in a web-development environment.

If you have any questions, comment below.

[homebrew]: http://brew.sh/
[rvm]: https://rvm.io/
[ruby]: https://www.ruby-lang.org/en/
[nodejs]: http://nodejs.org/
[xcode]: https://itunes.apple.com/us/app/xcode/id497799835?mt=12
[git]: http://git-scm.com/
[rvm-install]: https://rvm.io/rvm/install