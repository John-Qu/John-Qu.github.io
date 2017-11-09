---
layout: post
title:  "Chapter 1 From zero to deploy - RUBY ON RAILS TUTORIAL (RAILS 5)"
date: 2017-11-09 10:03:05 +0800
categories: book
---

# [Chapter 1From zero to deploy](https://www.railstutorial.org/book/beginning#cha-beginning)

Welcome to [*Ruby on Rails Tutorial: Learn Web Development with Rails*](http://www.railstutorial.org/book). The purpose of this book is to teach you how to develop custom web applications, and our tool of choice is the popular [Ruby on Rails](http://rubyonrails.org/) web framework. In addition to focusing on general principles of web development (rather than on Rails specifically), the [Ruby on Rails Tutorial](http://railstutorial.org/) teaches the broader skill of *technical sophistication* ([Box 1.1](https://www.railstutorial.org/book/beginning#aside-technical_sophistication)),[1](https://www.railstutorial.org/book/beginning#cha-1_footnote-1) which is a principal theme developed by the [Learn Enough to Be Dangerous](http://learnenough.com/story) tutorials.[2](https://www.railstutorial.org/book/beginning#cha-1_footnote-2) In particular, the Learn Enough introductory sequence consists of a series of tutorials that are suitable as prerequisites to the [Ruby on Rails Tutorial](http://railstutorial.org/), starting with [*Learn Enough Command Line to Be Dangerous*](http://learnenough.com/command-line-tutorial),[3](https://www.railstutorial.org/book/beginning#cha-1_footnote-3)which (unlike the present tutorial) is aimed at complete beginners.

Box 1.1. Technical sophistication

The [Ruby on Rails Tutorial](http://railstutorial.org/) is part of the [Learn Enough to Be Dangerous](http://learnenough.com/story) family of tutorials, which develop the theme of *technical sophistication*: the combination of hard and soft skills that make it seem like you can magically solve any technical problem ([Figure 1.1](https://www.railstutorial.org/book/beginning#fig-tech_support_cheat_sheet)).Web development, and computer programming in general, are essential components of technical sophistication, but there’s more to it than that—you also have to know how to click around menu items to learn the capabilities of a particular application, how to clarify a confusing error message by [Googling it](http://lmgtfy.com/), or when to give up and just reboot the darn thing.

Because web applications have so many moving parts, they offer ample opportunities to develop your technical sophistication. In the context of Rails web development, some specific examples of technical sophistication include making sure you’re using the right Ruby gem versions, running `bundle install` or `bundle update`, and restarting the local webserver if something doesn’t work. (Don’t worry if all this sounds like gibberish; we’ll cover everything mentioned here in the course of completing this tutorial.)

As you proceed through this tutorial, in all likelihood you will occasionally be tripped up by things not immediately working as expected. Although some particularly tricky steps are explicitly highlighted in the text, it is impossible to anticipate all the things that can go wrong. I recommend you embrace these inevitable stumbling blocks as opportunities to work on improving your technical sophistication. Or, as we say in [geek speak](https://www.learnenough.com/command-line-tutorial#aside-speak_geek): *It’s not a bug, it’s a feature!*

![images/figures/tech_support_cheat_sheet](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/tech_support_cheat_sheet.png)

Figure 1.1: “[Tech Support Cheat Sheet](https://m.xkcd.com/627/)” (via [xkcd](http://xkcd.com/)).

The *Ruby on Rails Tutorial* is designed to give you a thorough introduction to web application development, including a basic grounding in Ruby, Rails, HTML & CSS, databases, version control, testing, and deployment—sufficient to launch you on a career as a web developer or technology entrepreneur. If you already know web development, this book will quickly teach you the essentials of the Rails framework, including MVC and REST, generators, migrations, routing, and embedded Ruby. In any case, when you finish the *Ruby on Rails Tutorial* you will be in a position to benefit from the many more advanced books, blogs, and screencasts that are part of the thriving programming educational ecosystem.[4](https://www.railstutorial.org/book/beginning#cha-1_footnote-4)

The *Ruby on Rails Tutorial* takes an integrated approach to web development by building three example applications of increasing sophistication, starting with a minimal *hello* app ([Section 1.3](https://www.railstutorial.org/book/beginning#sec-the_hello_application)), a slightly more capable *toy* app ([Chapter 2](https://www.railstutorial.org/book/toy_app#cha-a_toy_app)), and a real *sample* app ([Chapter 3](https://www.railstutorial.org/book/static_pages#cha-static_pages)through [Chapter 14](https://www.railstutorial.org/book/following_users#cha-following_users)). As implied by their generic names, the applications developed in the *Ruby on Rails Tutorial* are not specific to any particular kind of website. The final sample application bears more than a passing resemblance to [Twitter](http://twitter.com/) (which, coincidentally, was also originally written in Rails), but the emphasis throughout the tutorial is on general principles, so you will have a solid foundation no matter what kinds of web applications you want to build.

In this first chapter, we’ll get started with Ruby on Rails by installing all the necessary software and by setting up our development environment ([Section 1.2](https://www.railstutorial.org/book/beginning#sec-up_and_running)). We’ll then create our first Rails application, called `hello_app`. The *Rails Tutorial* emphasizes good software development practices, so immediately after creating our fresh new Rails project we’ll put it under version control with Git ([Section 1.4](https://www.railstutorial.org/book/beginning#sec-version_control)). And, believe it or not, in this chapter we’ll even put our first app on the wider web by *deploying* it to production ([Section 1.5](https://www.railstutorial.org/book/beginning#sec-deploying)).

In [Chapter 2](https://www.railstutorial.org/book/toy_app#cha-a_toy_app), we’ll make a second project, whose purpose is to demonstrate the basic workings of a Rails application. To get up and running quickly, we’ll build this *toy app*(called `toy_app`) using scaffolding ([Box 1.2](https://www.railstutorial.org/book/beginning#aside-scaffolding)) to generate code; because this code is both ugly and complex, [Chapter 2](https://www.railstutorial.org/book/toy_app#cha-a_toy_app) will focus on interacting with the toy app through its *URIs*(often called *URLs*)[5](https://www.railstutorial.org/book/beginning#cha-1_footnote-5) using a web browser.

The rest of the tutorial focuses on developing a single large *real sample application* (called `sample_app`), writing all the code from scratch. We’ll develop the sample app using a combination of *mockups*, *test-driven development* (TDD), and *integration tests*. We’ll get started in [Chapter 3](https://www.railstutorial.org/book/static_pages#cha-static_pages) by creating static pages and then add a little dynamic content. We’ll take a quick detour in [Chapter 4](https://www.railstutorial.org/book/rails_flavored_ruby#cha-rails_flavored_ruby) to learn a little about the Ruby language underlying Rails.Then, in [Chapter 5](https://www.railstutorial.org/book/filling_in_the_layout#cha-filling_in_the_layout) through [Chapter 12](https://www.railstutorial.org/book/password_reset#cha-password_reset), we’ll complete the foundation for the sample application by making a site layout, a user data model, and a full registration and authentication system (including account activation and password resets). Finally, in [Chapter 13](https://www.railstutorial.org/book/user_microposts#cha-user_microposts) and [Chapter 14](https://www.railstutorial.org/book/following_users#cha-following_users) we’ll add microblogging and social features to make a working example site.

Box 1.2. Scaffolding: Quicker, easier, more seductive

From the beginning, Rails has benefited from a palpable sense of excitement, starting with the famous [15-minute weblog video](http://www.youtube.com/watch?v=Gzj723LkRJY) by Rails creator David Heinemeier Hansson. That video and its successors are a great way to get a taste of Rails’ power, and I recommend watching them. But be warned: they accomplish their amazing fifteen-minute feat using a feature called *scaffolding*, which relies heavily on *generated code*, magically created by the Rails `generate scaffold` command.

When writing a Ruby on Rails tutorial, it is tempting to rely on the scaffolding approach—it’s [quicker, easier, more seductive](http://en.wikipedia.org/wiki/Dark_side_(Star_Wars)). But the complexity and sheer amount of code in the scaffolding can be utterly overwhelming to a beginning Rails developer; you may be able to use it, but you probably won’t understand it. Following the scaffolding approach risks turning you into a virtuoso script generator with little (and brittle) actual knowledge of Rails.

In the *Ruby on Rails Tutorial*, we’ll take the (nearly) polar opposite approach: although [Chapter 2](https://www.railstutorial.org/book/toy_app#cha-a_toy_app) will develop a small toy app using scaffolding, the core of the *Rails Tutorial* is the sample app, which we’ll start writing in [Chapter 3](https://www.railstutorial.org/book/static_pages#cha-static_pages). At each stage of developing the sample application, we will write *small, bite-sized* pieces of code—simple enough to understand, yet novel enough to be challenging. The cumulative effect will be a deeper, more flexible knowledge of Rails, giving you a good background for writing nearly any type of web application.

## [1.1 Introduction](https://www.railstutorial.org/book/beginning#sec-introduction)

Ruby on Rails (or just “Rails” for short) is a web development framework written in the Ruby programming language. Since its debut in 2004, Ruby on Rails has rapidly become one of the most powerful and popular tools for building dynamic web applications. Rails is used by companies as varied as [Airbnb](http://airbnb.com/), [Basecamp](http://basecamp.com/), [Disney](http://disney.com/), [GitHub](http://github.com/), [Hulu](http://hulu.com/), [Kickstarter](http://kickstarter.com/), [Shopify](http://shopify.com/), [Twitter](http://twitter.com/), and the [Yellow Pages](http://yellowpages.com/). There are also many web development shops that specialize in Rails, such as [ENTP](http://entp.com/), [thoughtbot](http://thoughtbot.com/), [Pivotal Labs](http://pivotallabs.com/), [Hashrocket](http://hashrocket.com/), and [HappyFunCorp](http://www.happyfuncorp.com/), plus innumerable independent consultants, trainers, and contractors.

What makes Rails so great? First of all, Ruby on Rails is 100% open-source, available under the generous [MIT License](http://www.opensource.org/licenses/mit-license.php), and as a result it also costs nothing to download or use.Rails also owes much of its success to its elegant and compact design; by exploiting the malleability of the underlying [Ruby](http://ruby-lang.org/) language, Rails effectively creates a [domain-specific language](http://en.wikipedia.org/wiki/Domain_Specific_Language) for writing web applications. As a result, many common web programming tasks—such as generating HTML, making data models, and routing URLs—are easy with Rails, and the resulting application code is concise and readable.

Rails also adapts rapidly to new developments in web technology and framework design.For example, Rails was one of the first frameworks to fully digest and implement the REST architectural style for structuring web applications (which we’ll be learning about throughout this tutorial). And when other frameworks develop successful new techniques, Rails creator [David Heinemeier Hansson](http://loudthinking.com/) and the [Rails core team](http://rubyonrails.org/core) don’t hesitate to incorporate their ideas. Perhaps the most dramatic example is the merger of Rails and Merb, a rival Ruby web framework, so that Rails now benefits from Merb’s modular design, stable [API](http://en.wikipedia.org/wiki/Application_programming_interface), and improved performance.

Finally, Rails benefits from an unusually enthusiastic and supportive community. The results include thousands of open-source [contributors](http://contributors.rubyonrails.org/), fun and informative [conferences](http://railsconf.com/), a huge number of [gems](https://rubygems.org/) (self-contained solutions to specific problems such as pagination and image upload), a rich variety of informative blogs, and a cornucopia of discussion forums and IRC channels. The large number of Rails programmers also makes it easier to handle the inevitable application errors: the “Google the error message” algorithm nearly always produces a relevant blog post or discussion-forum thread.

### [1.1.1 Prerequisites](https://www.railstutorial.org/book/beginning#sec-prerequisites)

There are no formal prerequisites to this book, and the *Ruby on Rails Tutorial* contains integrated tutorials not only for Rails, but also for the underlying Ruby language, the default Rails testing framework (minitest), the Unix command line, [HTML](http://en.wikipedia.org/wiki/HTML), [CSS](http://en.wikipedia.org/wiki/CSS), a small amount of [JavaScript](http://en.wikipedia.org/wiki/JavaScript), and even a little [SQL](http://en.wikipedia.org/wiki/SQL). That’s a lot of material to absorb, though, and I generally recommend having some HTML and programming background before starting this tutorial. If you’re new to software development, I recommend starting with the tutorials at [Learn Enough to Be Dangerous](http://learnenough.com/) instead:[6](https://www.railstutorial.org/book/beginning#cha-1_footnote-6)

1. Developer Fundamentals
   1. [*Learn Enough Command Line to Be Dangerous*](http://www.learnenough.com/command-line-tutorial)
   2. [*Learn Enough Text Editor to Be Dangerous*](http://www.learnenough.com/text-editor-tutorial)
   3. [*Learn Enough Git to Be Dangerous*](http://www.learnenough.com/git-tutorial)
2. Web Basics
   1. [*Learn Enough HTML to Be Dangerous*](http://www.learnenough.com/html-tutorial)
   2. [*Learn Enough CSS & Layout to Be Dangerous*](http://www.learnenough.com/css-and-layout-tutorial)
   3. [*Learn Enough JavaScript to Be Dangerous*](http://www.learnenough.com/javascript-tutorial)
3. Intro Ruby Web Development
   1. [*Learn Enough Ruby to Be Dangerous*](http://www.learnenough.com/ruby-tutorial)
   2. [*Learn Enough Sinatra to Be Dangerous*](http://www.learnenough.com/sinatra-tutorial)
   3. [*Learn Enough Ruby on Rails to Be Dangerous*](http://www.learnenough.com/ruby-on-rails-tutorial)
4. Professional Ruby Web Development
   - [*The Ruby on Rails Tutorial*](http://www.railstutorial.org/)

One common question when learning Rails is whether to learn Ruby first. The answer depends on your personal learning style and how much programming experience you already have. If you prefer to learn everything systematically from the ground up, or if you have never programmed before, then learning Ruby first might work well for you, and in this case I recommend following the full Learn Enough sequence listed above. On the other hand, many beginning Rails developers are excited about making *web* applications, and would rather not wait to finish a whole book on Ruby before ever writing a single web page.In this case, I recommend giving this tutorial a go and switching to the Learn Enough sequence if it proves too challenging.

At the end of this tutorial, no matter where you started, you should be ready for the many more intermediate-to-advanced Rails resources out there. Here are some I particularly recommend:

- [The Learn Enough Society](http://learnenough.com/story): Premium subscription service that includes a special enhanced version of the *Ruby on Rails Tutorial* book and 15+ hours of streaming screencast lessons filled the kind of with tips, tricks, and live demos that you can’t get from reading a book. Also includes text and videos for the other [Learn Enough](http://learnenough.com/)tutorials. Scholarship discounts are available.
- [Code School](https://www.codeschool.com/): Good interactive online programming courses
- The [Turing School of Software & Design](http://turing.io/): A full-time, 27-week training program in Denver, Colorado
- [Bloc](http://bloc.io/): An online bootcamp with a structured curriculum, personalized mentorship, and a focus on learning through concrete projects. Use the coupon code BLOCLOVESHARTL to get $500 off the enrollment fee.
- [Launch School](http://launchschool.com/railstutorial): A good online Rails development bootcamp (includes advanced material)
- [Firehose Project](http://www.thefirehoseproject.com/?tid=HARTL-RAILS-TUT-EB2&pid=HARTL-RAILS-TUT-EB2): A mentor-driven, online coding bootcamp focused on real-world programming skills like test-driven development, algorithms, and building an advanced web application as part of an agile team. Two-week free intro course.
- [Thinkful](http://www.thinkful.com/a/railstutorial): An online class that pairs you with a professional engineer as you work through a project-based curriculum
- [Pragmatic Studio](https://pragmaticstudio.com/refs/railstutorial): Online Ruby and Rails courses from Mike and Nicole Clark. Along with *Programming Ruby* author Dave Thomas, Mike taught the first Rails course I took, way back in 2006.
- [RailsApps](https://tutorials.railsapps.org/hartl): A large variety of detailed topic-specific Rails projects and tutorials
- [Rails Guides](http://guides.rubyonrails.org/): Topical and up-to-date Rails references

#### [Exercises](https://www.railstutorial.org/book/beginning#sec-exercises_prerequisites)

The [Ruby on Rails Tutorial](http://railstutorial.org/) contains a large number of exercises. Solving them as you proceed through the tutorial is strongly recommended.

In order to keep the main discussion independent of the exercises, the solutions are not generally incorporated into subsequent code listings. (In the rare circumstance that an exercise solution is used subsequently, it is explicitly solved in the main text.) This means that over time your code may diverge from the code shown in the tutorial due to differences introduced in the exercises. Learning how to resolve such discrepancies is a valuable exercise in technical sophistication ([Box 1.1](https://www.railstutorial.org/book/beginning#aside-technical_sophistication)).

To record your answers and see solutions, you can join the [Learn Enough Society](http://learnenough.com/story), a subscription service from [Learn Enough to Be Dangerous](http://learnenough.com/story) that includes a special enhanced version of the [Ruby on Rails Tutorial](http://railstutorial.org/).

Many of the exercises are challenging, but we’ll start out with some easy ones just to get warmed up:

1. Which website hosts the *Ruby gem* for Ruby on Rails? *Hint*: When in doubt, [Google it](http://lmgtfy.com/?q=ruby+gem).
2. What is the current version number of Rails?
3. As of this moment, how many total times has Ruby on Rails been downloaded?

### [1.1.2 Conventions used in this book](https://www.railstutorial.org/book/beginning#sec-conventions)

The conventions used in this book are mostly self-explanatory. In this section, we’ll go over some that may not be.

Many examples in this book use command-line commands. For simplicity, all command line examples use a Unix-style command line prompt (a dollar sign), as follows:

```
$ echo "hello, world"
hello, world

```

Rails comes with many commands that can be run at the command line. For example, in [Section 1.3.2](https://www.railstutorial.org/book/beginning#sec-rails_server) we’ll run a local development webserver with the `rails server` command:

```
$ rails server

```

As with the command-line prompt, the *Rails Tutorial* uses the Unix convention for directory separators (i.e., a forward slash `/`). For example, the sample application `production.rb` configuration file appears as follows:

```
config/environments/production.rb

```

This file path should be understood as being relative to the application’s root directory, which will vary by system; on the cloud IDE ([Section 1.2.1](https://www.railstutorial.org/book/beginning#sec-development_environment)), it looks like this:

```
/home/ubuntu/workspace/sample_app/

```

Thus, the full path to `production.rb` is

```
/home/ubuntu/workspace/sample_app/config/environments/production.rb

```

I will typically omit the application path and write just `config/environments/production.rb` for short.

The *Rails Tutorial* often shows output from various programs. Because of the innumerable small differences between different computer systems, the output you see may not always agree exactly with what is shown in the text, but this is not cause for concern. In addition, some commands may produce errors depending on your system; rather than attempt the [Sisyphean](http://en.wikipedia.org/wiki/Sisyphus) task of documenting all such errors in this tutorial, I will delegate to the “Google the error message” algorithm, which among other things is good practice for real-life software development ([Box 1.1](https://www.railstutorial.org/book/beginning#aside-technical_sophistication)). If you run into any problems while following the tutorial, I suggest consulting the resources listed in the [Rails Tutorial help page](http://www.railstutorial.org/help).[7](https://www.railstutorial.org/book/beginning#cha-1_footnote-7)

Because the *Rails Tutorial* covers testing of Rails applications, it is often helpful to know if a particular piece of code causes the test suite to fail (indicated by the color red) or pass (indicated by the color green). For convenience, code resulting in a failing test is thus indicated with **red**, while code resulting in a passing test is indicated with **green**.

Finally, for convenience the *Ruby on Rails Tutorial* adopts two conventions designed to make the many code samples easier to understand. First, some code listings include one or more highlighted lines, as seen below:

```
class User < ApplicationRecord
  validates :name,  presence: true
  validates :email, presence: true
end

```

Such highlighted lines typically indicate the most important new code in the given sample, and often (though not always) represent the difference between the present code listing and previous listings. Second, for brevity and simplicity many of the book’s code listings include vertical dots, as follows:

```
class User < ApplicationRecord
  .
  .
  .
  has_secure_password
end

```

These dots represent omitted code and should not be copied literally.

## [1.2 Up and running](https://www.railstutorial.org/book/beginning#sec-up_and_running)

Even for experienced Rails developers, installing Ruby, Rails, and all the associated supporting software can be an exercise in frustration. Compounding the problem is the multiplicity of environments: different operating systems, version numbers, preferences in text editor and integrated development environment (IDE), etc. The [Ruby on Rails Tutorial](http://railstutorial.org/)offers two recommended solutions to this problem. One possibility is to follow the full [Learn Enough](http://learnenough.com/) intro sequence mentioned in [Section 1.1.1](https://www.railstutorial.org/book/beginning#sec-prerequisites), which will automatically lead to a system configured for this tutorial.

The other possibility, recommended for newer users, is to sidestep such installation and configuration issues by using a *cloud integrated development environment*, or cloud IDE.The cloud IDE used in this tutorial runs inside an ordinary web browser, and hence works the same across different platforms, which is especially useful for operating systems (such as Windows) on which Rails development has historically been difficult. It also maintains the current state of your work, so you can take a break from the tutorial and come back to the system just as you left it.

### [1.2.1 Development environment](https://www.railstutorial.org/book/beginning#sec-development_environment)

Considering various idiosyncratic customizations, there are probably as many development environments as there are Rails programmers. To avoid this complexity, the *Ruby on Rails Tutorial* standardizes on the excellent cloud development environment [Cloud9](http://c9.io/). In particular, I am pleased to be partnering with Cloud9 to offer a free development environment specifically tailored to the needs of this tutorial. The resulting Rails Tutorial Cloud9 workspace comes pre-configured with most of the software needed for professional-grade Rails development, including Ruby, RubyGems, Git. (Indeed, the only big piece of software we’ll install separately is Rails itself, and this is intentional ([Section 1.2.2](https://www.railstutorial.org/book/beginning#sec-installing_rails)).)

Although you are welcome to develop your application locally, setting up a Rails development environment can be challenging, so I recommend the cloud IDE for most readers. For those who want to go the local route, try the steps at [InstallRails.com](http://installrails.com/), and be prepared for a challenging exercise in technical sophistication ([Box 1.1](https://www.railstutorial.org/book/beginning#aside-technical_sophistication)).

The cloud IDE includes the three essential components needed to develop web applications: a text editor, a filesystem navigator, and a command-line terminal ([Figure 1.2](https://www.railstutorial.org/book/beginning#fig-ide_anatomy)). Among other features, the cloud IDE text editor supports the “Find in Files” global search that I consider essential to navigating any large Ruby or Rails project.[8](https://www.railstutorial.org/book/beginning#cha-1_footnote-8)Finally, even if you decide not to use the cloud IDE exclusively in real life (and I certainly recommend learning other tools as well), it provides an excellent introduction to the general capabilities of text editors and other development tools.

![images/figures/ide_anatomy](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/ide_anatomy.png)

Figure 1.2: The anatomy of the cloud IDE.

Here are the steps for getting started with the cloud development environment:

1. [Sign up for a free account at Cloud9](https://c9.io/web/sign-up/free).[9](https://www.railstutorial.org/book/beginning#cha-1_footnote-9) In order to prevent abuse, Cloud9 requires a valid credit card for signup, but the Rails Tutorial workspace is 100% free, and your card will not be charged.
2. Click on “Go to your Dashboard”.
3. Select “Create New Workspace”.
4. As shown in [Figure 1.3](https://www.railstutorial.org/book/beginning#fig-cloud9_new_workspace), create a workspace called “rails-tutorial” (*not* “rails_tutorial”), set it to “Private to the people I invite”, and select the icon for the Rails Tutorial (*not*the icon for Ruby on Rails).
5. Click “Create workspace”.
6. After Cloud9 has finished provisioning the workspace, it should start automatically.

Because using two spaces for indentation is a near-universal convention in Ruby, I also recommend changing the editor to use two spaces instead of the default four. As shown in [Figure 1.4](https://www.railstutorial.org/book/beginning#fig-cloud9_two_spaces), you can do this by clicking the gear icon in the upper right and then selecting “Code Editor (Ace)” to edit the “Soft Tabs” setting. (Note that this takes effect immediately; you don’t need to click a “Save” button.)

![images/figures/cloud9_new_workspace_4th_ed](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/cloud9_new_workspace_4th_ed.png)

Figure 1.3: Creating a new workspace at Cloud9.

![images/figures/cloud9_two_spaces](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/cloud9_two_spaces.png)

Figure 1.4: Setting Cloud9 to use two spaces for indentation.

### [1.2.2 Installing Rails](https://www.railstutorial.org/book/beginning#sec-installing_rails)

The development environment from [Section 1.2.1](https://www.railstutorial.org/book/beginning#sec-development_environment) includes all the software we need to get started except for Rails itself. To install Rails, we’ll use the `gem` command provided by the *RubyGems* package manager, which involves typing the command shown in [Listing 1.1](https://www.railstutorial.org/book/beginning#code-installing_rails) into your command-line terminal. (If developing on your local system, this means using a regular terminal window; if using the cloud IDE, this means using the command-line area shown in [Figure 1.2](https://www.railstutorial.org/book/beginning#fig-ide_anatomy).)

Listing 1.1: Installing Rails with a specific version number.

```
$ gem install rails -v 5.1.2

```

Here the `-v` flag ensures that the specified version of Rails gets installed, which is important for getting results consistent with this tutorial.

## [1.3 The first application](https://www.railstutorial.org/book/beginning#sec-the_hello_application)

Following a [long tradition](http://www.catb.org/jargon/html/H/hello-world.html) in computer programming, our goal for the first application is to write a “hello, world” program. In particular, we will create a simple application that displays the string “hello, world!” on a web page, both on our development environment ([Section 1.3.4](https://www.railstutorial.org/book/beginning#sec-hello_world)) and on the live web ([Section 1.5](https://www.railstutorial.org/book/beginning#sec-deploying)).

Virtually all Rails applications start the same way, by running the `rails new` command.This handy command creates a skeleton Rails application in a directory of your choice. To get started, users *not* using the Cloud9 IDE recommended in [Section 1.2.1](https://www.railstutorial.org/book/beginning#sec-development_environment) should make a `workspace` directory for your Rails projects if it doesn’t already exist ([Listing 1.2](https://www.railstutorial.org/book/beginning#code-mkdir_rails_projects)) and then change into the directory. ([Listing 1.2](https://www.railstutorial.org/book/beginning#code-mkdir_rails_projects) uses the Unix commands `cd` and `mkdir`; see [Box 1.3](https://www.railstutorial.org/book/beginning#aside-unix_commands)if you are not already familiar with these commands.)

Listing 1.2: Making a `workspace` directory for Rails projects (unnecessary in the cloud).

```
$ cd                  # Change to the home directory.
$ mkdir workspace     # Make a workspace directory.
$ cd workspace/       # Change into the workspace directory.

```

Box 1.3. A crash course on the Unix command line

For readers coming from Windows or (to a lesser but still significant extent) macOS, the Unix command line may be unfamiliar. Luckily, if you are using the recommended cloud environment, you automatically have access to a Unix (Linux) command line running a standard [shell command-line interface](http://en.wikipedia.org/wiki/Shell_(computing)) known as [Bash](http://en.wikipedia.org/wiki/Bash_(Unix_shell)).

The basic idea of the command line is simple: by issuing short commands, users can perform a large number of operations, such as creating directories (`mkdir`), moving and copying files (`mv` and `cp`), and navigating the filesystem by changing directories (`cd`).Although the command line may seem primitive to users mainly familiar with graphical user interfaces (GUIs), appearances are deceiving: the command line is one of the most powerful tools in the developer’s toolbox. Indeed, you will rarely see the desktop of an experienced developer without several open terminal windows running command-line shells.

The general subject is deep, but for the purposes of this tutorial we will need only a few of the most common Unix command-line commands, as summarized in [Table 1.1](https://www.railstutorial.org/book/beginning#table-unix_commands). For a more thorough introduction to the Unix command line, see the first of the [Learn Enough](http://learnenough.com/)tutorials, [*Learn Enough Command Line to Be Dangerous*](http://learnenough.com/command-line-tutorial).[10](https://www.railstutorial.org/book/beginning#cha-1_footnote-10)

| **Description**                     | **Command**            | **Example**               |
| ----------------------------------- | ---------------------- | ------------------------- |
| list contents                       | `ls`                   | `$ ls -l`                 |
| make directory                      | `mkdir <dirname>`      | `$ mkdir workspace`       |
| change directory                    | `cd <dirname>`         | `$ cd workspace/`         |
| cd one directory up                 |                        | `$ cd ..`                 |
| cd to home directory                |                        | `$ cd ~` or just `$ cd`   |
| cd to path incl. home dir           |                        | `$ cd ~/workspace/`       |
| move file (rename)                  | `mv <source> <target>` | `$ mv foo bar`            |
| copy file                           | `cp <source> <target>` | `$ cp foo bar`            |
| remove file                         | `rm <file>`            | `$ rm foo`                |
| remove empty directory              | `rmdir <directory>`    | `$ rmdir workspace/`      |
| remove nonempty directory           | `rm -rf <directory>`   | `$ rm -rf tmp/`           |
| concatenate & display file contents | `cat <file>`           | `$ cat ~/.ssh/id_rsa.pub` |

Table 1.1: Some common Unix commands.

The next step on both local systems and the cloud IDE is to create the first application using the command in [Listing 1.3](https://www.railstutorial.org/book/beginning#code-rails_command). Note that [Listing 1.3](https://www.railstutorial.org/book/beginning#code-rails_command) explicitly includes the Rails version number as part of the command. This ensures that the same version of Rails we installed in [Listing 1.1](https://www.railstutorial.org/book/beginning#code-installing_rails) is used to create the first application’s file structure. (If the command in [Listing 1.3](https://www.railstutorial.org/book/beginning#code-rails_command) returns an error like “`Could not find ’railties’`”, it means you don’t have the right version of Rails installed, and you should double-check that you followed the command in [Listing 1.1](https://www.railstutorial.org/book/beginning#code-installing_rails) exactly as written.)

Listing 1.3: Running `rails new` (with a specific version number).

```
$ cd ~/workspace
$ rails _5.1.2_ new hello_app
      create
      create  README.md
      create  Rakefile
      create  config.ru
      create  .gitignore
      create  Gemfile
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/javascripts/application.js
      create  app/assets/javascripts/cable.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      .
      .
      .
      create  tmp/cache/assets
      create  vendor/assets/javascripts
      create  vendor/assets/javascripts/.keep
      create  vendor/assets/stylesheets
      create  vendor/assets/stylesheets/.keep
      remove  config/initializers/cors.rb
         run  bundle install
Fetching gem metadata from https://rubygems.org/..........
Fetching additional metadata from https://rubygems.org/..
Resolving dependencies...
Installing rake 11.1.2
Using concurrent-ruby 1.0.2
.
.
.
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
         run  bundle exec spring binstub --all
* bin/rake: spring inserted
* bin/rails: spring inserted

```

As seen at the end of [Listing 1.3](https://www.railstutorial.org/book/beginning#code-rails_command), running `rails new` automatically runs the `bundle install` command after the file creation is done. We’ll discuss what this means in more detail starting in [Section 1.3.1](https://www.railstutorial.org/book/beginning#sec-bundler).

Notice how many files and directories the `rails` command creates. This standard directory and file structure ([Figure 1.5](https://www.railstutorial.org/book/beginning#fig-directory_structure_rails)) is one of the many advantages of Rails: it immediately gets you from zero to a functional (if minimal) application. Moreover, since the structure is common to all Rails apps, you can immediately get your bearings when looking at someone else’s code.

A summary of the default Rails files appears in [Table 1.2](https://www.railstutorial.org/book/beginning#table-rails_directory_structure). We’ll learn about most of these files and directories throughout the rest of this book. In particular, starting in [Section 5.2.1](https://www.railstutorial.org/book/filling_in_the_layout#sec-the_asset_pipeline)we’ll discuss the `app/assets` directory, part of the *asset pipeline* that makes it easy to organize and deploy assets such as cascading style sheets and JavaScript files.

![images/figures/directory_structure_rails_4th_edition](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/directory_structure_rails_4th_edition.png)

Figure 1.5: The directory structure for a newly created Rails app.

| **File/Directory** | **Purpose**                              |
| ------------------ | ---------------------------------------- |
| `app/`             | Core application (app) code, including models, views, controllers, and helpers |
| `app/assets`       | Applications assets such as cascading style sheets (CSS), JavaScript files, and images |
| `bin/`             | Binary executable files                  |
| `config/`          | Application configuration                |
| `db/`              | Database files                           |
| `doc/`             | Documentation for the application        |
| `lib/`             | Library modules                          |
| `lib/assets`       | Library assets such as cascading style sheets (CSS), JavaScript files, and images |
| `log/`             | Application log files                    |
| `public/`          | Data accessible to the public (e.g., via web browsers), such as error pages |
| `bin/rails`        | A program for generating code, opening console sessions, or starting a local server |
| `test/`            | Application tests                        |
| `tmp/`             | Temporary files                          |
| `vendor/`          | Third-party code such as plugins and gems |
| `vendor/assets`    | Third-party assets such as cascading style sheets (CSS), JavaScript files, and images |
| `README.md`        | A brief description of the application   |
| `Rakefile`         | Utility tasks available via the `rake` command |
| `Gemfile`          | Gem requirements for this app            |
| `Gemfile.lock`     | A list of gems used to ensure that all copies of the app use the same gem versions |
| `config.ru`        | A configuration file for [Rack middleware](http://rack.github.io/) |
| `.gitignore`       | Patterns for files that should be ignored by Git |

Table 1.2: A summary of the default Rails directory structure.

### [1.3.1 Bundler](https://www.railstutorial.org/book/beginning#sec-bundler)

After creating a new Rails application, the next step is to use *Bundler* to install and include the gems needed by the app. As noted briefly in [Section 1.3](https://www.railstutorial.org/book/beginning#sec-the_hello_application), Bundler is run automatically (via `bundle install`) by the `rails` command, but in this section we’ll make some changes to the default application gems and run Bundler again. This involves opening the `Gemfile` with a text editor. (With the cloud IDE, this involves clicking the arrow in the file navigator to open the sample app directory and double-clicking the `Gemfile` icon.)Although the exact version numbers and details may differ slightly, the results should look something like [Figure 1.6](https://www.railstutorial.org/book/beginning#fig-cloud9_gemfile) and [Listing 1.4](https://www.railstutorial.org/book/beginning#code-default_gemfile). (The code in this file is Ruby, but don’t worry at this point about the syntax; [Chapter 4](https://www.railstutorial.org/book/rails_flavored_ruby#cha-rails_flavored_ruby) will cover Ruby in more depth.) If the files and directories don’t appear as shown in [Figure 1.6](https://www.railstutorial.org/book/beginning#fig-cloud9_gemfile), click on the file navigator’s gear icon and select “Refresh File Tree”. (As a general rule, you should refresh the file tree any time files or directories don’t appear as expected.)[11](https://www.railstutorial.org/book/beginning#cha-1_footnote-11)

![images/figures/cloud9_gemfile_4th_ed](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/cloud9_gemfile_4th_ed.png)

Figure 1.6: The default `Gemfile` open in a text editor.

Listing 1.4: The default `Gemfile` in the `hello_app` directory.

```
source 'https://rubygems.org'

git_source(:github) do |repo_name|
  repo_name = "#{repo_name}/#{repo_name}" unless repo_name.include?("/")
  "https://github.com/#{repo_name}.git"
end


# Bundle edge Rails instead: gem 'rails', github: 'rails/rails'
gem 'rails', '~> 5.1.2'
# Use sqlite3 as the database for Active Record
gem 'sqlite3'
# Use Puma as the app server
gem 'puma', '~> 3.0'
# Use SCSS for stylesheets
gem 'sass-rails', '~> 5.0'
# Use Uglifier as compressor for JavaScript assets
gem 'uglifier', '>= 1.3.0'
# Use CoffeeScript for .coffee assets and views
gem 'coffee-rails', '~> 4.2'
# See https://github.com/rails/execjs#readme for more supported runtimes
# gem 'therubyracer', platforms: :ruby

# Use jquery as the JavaScript library
gem 'jquery-rails'
# Turbolinks makes navigating your web application faster.
# Read more: https://github.com/turbolinks/turbolinks
gem 'turbolinks', '~> 5'
# Build JSON APIs with ease. Read more: https://github.com/rails/jbuilder
gem 'jbuilder', '~> 2.5'
# Use Redis adapter to run Action Cable in production
# gem 'redis', '~> 3.0'
# Use ActiveModel has_secure_password
# gem 'bcrypt', '~> 3.1.7'

# Use Capistrano for deployment
# gem 'capistrano-rails', group: :development

group :development, :test do
  # Call 'byebug' anywhere in the code to stop execution and get a debugger
  # console
  gem 'byebug', '9.0.6', platform: :mri
end

group :development do
  # Access an IRB console on exception pages or by using <%= console %>
  # anywhere in the code.
  gem 'web-console', '>= 3.3.0'
  gem 'listen', '~> 3.0.5'
  # Spring speeds up development by keeping your application running in the
  # background. Read more: https://github.com/rails/spring
  gem 'spring'
  gem 'spring-watcher-listen', '~> 2.0.0'
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]

```

Many of these lines are commented out with the hash symbol `#` ([Section 4.2.1](https://www.railstutorial.org/book/rails_flavored_ruby#sec-comments)); they are there to show you some commonly needed gems and to give examples of the Bundler syntax. For now, we won’t need any gems other than the defaults.

Unless you specify a version number to the `gem` command, Bundler will automatically install the latest requested version of the gem. This is the case, for example, in the code

```
gem 'sqlite3'

```

There are also two common ways to specify a gem version range, which allows us to exert some control over the version used by Rails. The first looks like this:

```
gem 'uglifier', '>= 1.3.0'

```

This installs the latest version of the `uglifier` gem (which handles file compression for the asset pipeline) as long as it’s greater than or equal to version `1.3.0`—even if it’s, say, version `7.2`. The second method looks like this:

```
gem 'coffee-rails', '~> 4.0.0'

```

This installs the gem `coffee-rails` as long as it’s newer than version `4.0.0` and *not*newer than `4.1`. In other words, the `>=` notation always installs the latest gem, whereas the `~> 4.0.0` notation only installs updated gems where the last digit differs (e.g., from `4.0.0`to `4.0.1`), but the digits before that releases (e.g., from `4.0` to `4.1`).[12](https://www.railstutorial.org/book/beginning#cha-1_footnote-12) Unfortunately, experience shows that even minor point releases can break the application, so for the *Ruby on Rails Tutorial* we’ll err on the side of caution by including exact version numbers for all gems. You are welcome to use the most up-to-date version of any gem, including using the `~>` construction in the `Gemfile` (which I generally recommend for more advanced users), but be warned that this may cause the tutorial to act unpredictably.

Converting the `Gemfile` in [Listing 1.4](https://www.railstutorial.org/book/beginning#code-default_gemfile) to use exact gem versions results in the code shown in [Listing 1.5](https://www.railstutorial.org/book/beginning#code-gemfile_sqlite_version). (You can determine the exact version number for each gem by running `gem list <gem name>` at the command line, but [Listing 1.5](https://www.railstutorial.org/book/beginning#code-gemfile_sqlite_version) saves you the trouble.) Note that we’ve also taken this opportunity to arrange for the `sqlite3` gem to be included only in a development or test environment ([Section 7.1.1](https://www.railstutorial.org/book/sign_up#sec-rails_environments)), which prevents potential conflicts with the database used by Heroku ([Section 1.5](https://www.railstutorial.org/book/beginning#sec-deploying)). **Important note: For all the Gemfiles in this book, you should use the version numbers listed at gemfiles-4th-ed.railstutorial.org instead of the ones listed below (although they should be identical if you are reading this online).**

Listing 1.5: A `Gemfile` with an explicit version for each Ruby gem.

```
source 'https://rubygems.org'

gem 'rails',        '5.1.2'
gem 'sqlite3',      '1.3.13'
gem 'puma',         '3.9.1'
gem 'sass-rails',   '5.0.6'
gem 'uglifier',     '3.2.0'
gem 'coffee-rails', '4.2.2'
gem 'jquery-rails', '4.3.1'
gem 'turbolinks',   '5.0.1'
gem 'jbuilder',     '2.7.0'

group :development, :test do
  gem 'byebug', '9.0.6', platform: :mri
end

group :development do
  gem 'web-console',           '3.5.1'
  gem 'listen',                '3.0.8'
  gem 'spring',                '2.0.2'
  gem 'spring-watcher-listen', '2.0.1'
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]

```

Once you’ve placed the contents of [Listing 1.5](https://www.railstutorial.org/book/beginning#code-gemfile_sqlite_version) into the application’s `Gemfile`, install the gems using `bundle install`:[13](https://www.railstutorial.org/book/beginning#cha-1_footnote-13)

```
$ cd hello_app/
$ bundle install
Fetching source index for https://rubygems.org/
.
.
.

```

The `bundle install` command might take a few moments, but when it’s done our application will be ready to run.

By the way, when you run `bundle install` it’s possible that you’ll get a message saying you need to run `bundle update` first. In this case you should… run `bundle update` first.(Learning not to panic when things don’t go exactly as planned is a key part of technical sophistication, and you’ll be amazed at how often the “error” message contains the exact instructions you need to fix the problem at hand.)

### [1.3.2 `rails server`](https://www.railstutorial.org/book/beginning#sec-rails_server)

Thanks to running `rails new` in [Section 1.3](https://www.railstutorial.org/book/beginning#sec-the_hello_application) and `bundle install` in [Section 1.3.1](https://www.railstutorial.org/book/beginning#sec-bundler), we already have an application we can run—but how? Happily, Rails comes with a command-line program, or *script*, that runs a *local* webserver to assist us in developing our application. The exact command depends on the environment you’re using: on a local system, you just run `rails server` ([Listing 1.6](https://www.railstutorial.org/book/beginning#code-local_server)), whereas on Cloud9 you need to supply an additional *IP binding address* and *port number* to tell the Rails server the address it can use to make the application visible to the outside world ([Listing 1.7](https://www.railstutorial.org/book/beginning#code-cloud_server)).[14](https://www.railstutorial.org/book/beginning#cha-1_footnote-14) (Cloud9 uses the special *environment variables* `$IP` and `$PORT` to assign the IP address and port number dynamically. If you want to see the values of these variables, type `echo $IP` or `echo $PORT` at the command line.)

If your system complains about the lack of a JavaScript runtime, visit the [execjs page at GitHub](https://github.com/sstephenson/execjs) for a list of possibilities. I particularly recommend installing [Node.js](http://nodejs.org/).

Listing 1.6: Running the Rails server on a local machine.

```
$ cd ~/workspace/hello_app/
$ rails server
=> Booting Puma
=> Rails application starting on http://localhost:3000
=> Run `rails server -h` for more startup options
=> Ctrl-C to shutdown server

```

Listing 1.7: Running the Rails server on the cloud IDE.

```
$ cd ~/workspace/hello_app/
$ rails server -b $IP -p $PORT
=> Booting Puma
=> Rails application starting on http://localhost:8080
=> Run `rails server -h` for more startup options
=> Ctrl-C to shutdown server

```

Whichever option you choose, I recommend running the `rails server` command in a second terminal tab so that you can still issue commands in the first tab, as shown in [Figure 1.7](https://www.railstutorial.org/book/beginning#fig-new_terminal_tab) and [Figure 1.8](https://www.railstutorial.org/book/beginning#fig-rails_server_new_tab). (If you already started a server in your first tab, press Ctrl-C to shut it down.)[15](https://www.railstutorial.org/book/beginning#cha-1_footnote-15) On a local server, paste the URL [http://localhost:3000](http://localhost:3000/) into the address bar of your browser; on the cloud IDE, go to Share and click on the Application address to open it ([Figure 1.9](https://www.railstutorial.org/book/beginning#fig-share_workspace)). In either case, the result should look something like [Figure 1.10](https://www.railstutorial.org/book/beginning#fig-riding_rails).

![images/figures/new_terminal_tab](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/new_terminal_tab.png)

Figure 1.7: Opening a new terminal tab.

![images/figures/rails_server_new_tab](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/rails_server_new_tab.png)

Figure 1.8: Running the Rails server in a separate tab.

![images/figures/share_workspace](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/share_workspace.png)

Figure 1.9: Sharing the local server running on the cloud workspace.

![images/figures/riding_rails_4th_edition](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/riding_rails_4th_edition.png)

Figure 1.10: The default Rails page served by `rails server`.

#### [Exercises](https://www.railstutorial.org/book/beginning#sec-exercises_rails_server)

Solutions to exercises are available for free at [railstutorial.org/solutions](http://railstutorial.org/solutions) with any Rails Tutorial purchase. To see other people’s answers and to record your own, join the [Learn Enough Society](http://learnenough.com/society) at [learnenough.com/society](http://learnenough.com/society).

1. According to the default Rails page, what is the version of Ruby on your system?Confirm by running `ruby -v` at the command line.
2. What is the version of Rails? Confirm that it matches the version installed in [Listing 1.1](https://www.railstutorial.org/book/beginning#code-installing_rails).

### [1.3.3 Model-View-Controller (MVC)](https://www.railstutorial.org/book/beginning#sec-mvc)

Even at this early stage, it’s helpful to get a high-level overview of how Rails applications work, as illustrated in [Figure 1.11](https://www.railstutorial.org/book/beginning#fig-MVC). You might have noticed that the standard Rails application structure ([Figure 1.5](https://www.railstutorial.org/book/beginning#fig-directory_structure_rails)) has an application directory called `app/` containing three subdirectories: `models`, `views`, and `controllers`. This is a hint that Rails follows the [model-view-controller](http://en.wikipedia.org/wiki/Model-view-controller) (MVC) architectural pattern, which enforces a separation between the data in the application (such as user information) and the code used to display it, which is a common way of structuring a graphical user interface (GUI).

When interacting with a Rails application, a browser sends a *request*, which is received by a webserver and passed on to a Rails *controller*, which is in charge of what to do next. In some cases, the controller will immediately render a *view*, which is a template that gets converted to HTML and sent back to the browser. More commonly for dynamic sites, the controller interacts with a *model*, which is a Ruby object that represents an element of the site (such as a user) and is in charge of communicating with the database. After invoking the model, the controller then renders the view and returns the complete web page to the browser as HTML.

![mvc_schematic](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/mvc_schematic.png)

Figure 1.11: A schematic representation of the model-view-controller (MVC) architecture.

If this discussion seems a bit abstract right now, don’t worry; we’ll cover these ideas in more detail later in this book. In particular, [Section 1.3.4](https://www.railstutorial.org/book/beginning#sec-hello_world) shows a first tentative application of MVC, while [Section 2.2.2](https://www.railstutorial.org/book/toy_app#sec-mvc_in_action) includes a more detailed discussion of MVC in the context of the toy app. Finally, the full sample app will use all aspects of MVC: we’ll cover controllers and views starting in [Section 3.2](https://www.railstutorial.org/book/static_pages#sec-static_pages), models starting in [Section 6.1](https://www.railstutorial.org/book/modeling_users#sec-user_model), and we’ll see all three working together in [Section 7.1.2](https://www.railstutorial.org/book/sign_up#sec-a_users_resource).

### [1.3.4 Hello, world!](https://www.railstutorial.org/book/beginning#sec-hello_world)

As a first application of the MVC framework, we’ll make a [wafer-thin](http://en.wikipedia.org/wiki/Mr_Creosote) change to the first app by adding a *controller action* to render the string “hello, world!” to replace the default Rails page from [Figure 1.10](https://www.railstutorial.org/book/beginning#fig-riding_rails). (We’ll learn more about controller actions starting in [Section 2.2.2](https://www.railstutorial.org/book/toy_app#sec-mvc_in_action).)

As implied by their name, controller actions are defined inside controllers. We’ll call our action `hello` and place it in the Application controller. Indeed, at this point the Application controller is the only controller we have, which you can verify by running

```
$ ls app/controllers/*_controller.rb

```

to view the current controllers. (We’ll start creating our own controllers in [Chapter 2](https://www.railstutorial.org/book/toy_app#cha-a_toy_app).)[Listing 1.8](https://www.railstutorial.org/book/beginning#code-hello_action) shows the resulting definition of `hello`, which uses the `render` function to return the HTML text “hello, world!”. (Don’t worry about the Ruby syntax right now; it will be covered in more depth in [Chapter 4](https://www.railstutorial.org/book/rails_flavored_ruby#cha-rails_flavored_ruby).)

Listing 1.8: Adding a `hello` action to the Application controller.`app/controllers/application_controller.rb`

```
class ApplicationController < ActionController::Base
  protect_from_forgery with: :exception

  def hello
    render html: "hello, world!"
  end
end

```

Having defined an action that returns the desired string, we need to tell Rails to use that action instead of the default page in [Figure 1.10](https://www.railstutorial.org/book/beginning#fig-riding_rails). To do this, we’ll edit the Rails *router*, which sits in front of the controller in [Figure 1.11](https://www.railstutorial.org/book/beginning#fig-MVC) and determines where to send requests that come in from the browser. (I’ve omitted the router from [Figure 1.11](https://www.railstutorial.org/book/beginning#fig-MVC) for simplicity, but we’ll discuss it in more detail starting in [Section 2.2.2](https://www.railstutorial.org/book/toy_app#sec-mvc_in_action).) In particular, we want to change the default page, the *root route*, which determines the page that is served on the *root URL*.Because it’s the URL for an address like http://www.example.com/ (where nothing comes after the final forward slash), the root URL is often referred to as / (“slash”) for short.

As seen in [Listing 1.9](https://www.railstutorial.org/book/beginning#code-default_root_route), the Rails routes file (`config/routes.rb`) includes a comment directing us to the [Rails Guide on Routing](http://guides.rubyonrails.org/routing.html), which includes instructions on how to define the root route. The syntax looks like this:

```
root 'controller_name#action_name'

```

In the present case, the controller name is `application` and the action name is `hello`, which results in the code shown in [Listing 1.10](https://www.railstutorial.org/book/beginning#code-hello_root_route).

Listing 1.9: The default routing file (formatted to fit).`config/routes.rb`

```
Rails.application.routes.draw do
  # For details on the DSL available within this file,
  # see http://guides.rubyonrails.org/routing.html
end

```

Listing 1.10: Setting the root route.`config/routes.rb`

```
Rails.application.routes.draw do
  root 'application#hello'
end

```

With the code from [Listing 1.8](https://www.railstutorial.org/book/beginning#code-hello_action) and [Listing 1.10](https://www.railstutorial.org/book/beginning#code-hello_root_route), the root route returns “hello, world!” as required ([Figure 1.12](https://www.railstutorial.org/book/beginning#fig-hello_world_hello_app)).[16](https://www.railstutorial.org/book/beginning#cha-1_footnote-16) Hello, world!

![images/figures/hello_world_hello_app](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/hello_world_hello_app.png)

Figure 1.12: Viewing “hello, world!” in the browser.

#### [Exercises](https://www.railstutorial.org/book/beginning#sec-exercises_hello_world)

Solutions to exercises are available for free at [railstutorial.org/solutions](http://railstutorial.org/solutions) with any Rails Tutorial purchase. To see other people’s answers and to record your own, join the [Learn Enough Society](http://learnenough.com/society) at [learnenough.com/society](http://learnenough.com/society).

1. Change the content of the `hello` action in [Listing 1.8](https://www.railstutorial.org/book/beginning#code-hello_action) to read “hola, mundo!” instead of “hello, world!”.
2. Show that Rails supports non-[ASCII](http://en.wikipedia.org/wiki/ASCII) characters by including an inverted exclamation point, as in “¡Hola, mundo!” ([Figure 1.13](https://www.railstutorial.org/book/beginning#fig-hola_mundo)).[17](https://www.railstutorial.org/book/beginning#cha-1_footnote-17) To get a ¡ character on a Mac, you can use Option-1; otherwise, you can always copy-and-paste the character into your editor.
3. By following the example of the `hello` action in [Listing 1.8](https://www.railstutorial.org/book/beginning#code-hello_action), add a second action called `goodbye` that renders the text “goodbye, world!”. Edit the routes file from [Listing 1.10](https://www.railstutorial.org/book/beginning#code-hello_root_route)so that the root route goes to `goodbye` instead of to `hello` ([Figure 1.14](https://www.railstutorial.org/book/beginning#fig-goodbye_world)).

![images/figures/hola_mundo](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/hola_mundo.png)

Figure 1.13: Changing the root route to return “¡Hola, mundo!”.

![images/figures/goodbye_world](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/goodbye_world.png)

Figure 1.14: Changing the root route to return “goodbye, world!”.

## [1.4 Version control with Git](https://www.railstutorial.org/book/beginning#sec-version_control)

Now that we have a working “hello, world” application, we’ll take a moment for a step that, while technically optional, would be viewed by experienced software developers as practically essential: placing our application source code under *version control*. Version control systems allow us to track changes to our project’s code, collaborate more easily, and roll back any inadvertent errors (such as accidentally deleting files). Knowing how to use a version control system is a required skill for every professional-grade software developer.

There are many options for version control, but the Rails community has largely standardized on [Git](http://git-scm.com/), a distributed version control system originally developed by Linus Torvalds to host the Linux kernel. Git is a large subject, and we’ll only be scratching the surface in this book; for a more thorough introduction, see [*Learn Enough Git to Be Dangerous*](http://learnenough.com/git-tutorial).[18](https://www.railstutorial.org/book/beginning#cha-1_footnote-18)

Putting your source code under version control with Git is *strongly* recommended, not only because it’s nearly a universal practice in the Rails world, but also because it will allow you to back up and share your code more easily ([Section 1.4.3](https://www.railstutorial.org/book/beginning#sec-bitbucket)) and deploy your application right here in the first chapter ([Section 1.5](https://www.railstutorial.org/book/beginning#sec-deploying)).

### [1.4.1 Installation and setup](https://www.railstutorial.org/book/beginning#sec-git_setup)

The cloud IDE recommended in [Section 1.2.1](https://www.railstutorial.org/book/beginning#sec-development_environment) includes Git by default, so no installation is necessary in this case. Otherwise, [*Learn Enough Git to Be Dangerous*](http://learnenough.com/git-tutorial) includes [instructions](https://www.learnenough.com/git-tutorial#sec-installation_and_setup)for installing Git on your system.

#### [First-time system setup](https://www.railstutorial.org/book/beginning#uid99)

Before using Git, you should perform a couple of one-time setup steps. These are *system*setups, meaning you only have to do them once per computer:

```
$ git config --global user.name "Your Name"
$ git config --global user.email your.email@example.com

```

Note that the name and email address you use in your Git configuration will be available in any repositories you make public.

#### [First-time repository setup](https://www.railstutorial.org/book/beginning#sec-first_time_setup)

Now we come to some steps that are necessary each time you create a new *repository*(sometimes called a *repo* for short). The first step is to navigate to the root directory of the first app and initialize a new repository:

```
$ git init
Initialized empty Git repository in /home/ubuntu/workspace/hello_app/.git/

```

The next step is to add all the project files to the repository using `git add -A`:

```
$ git add -A

```

This command adds all the files in the current directory apart from those that match the patterns in a special file called `.gitignore`. The `rails new` command automatically generates a `.gitignore` file appropriate to a Rails project, but you can add additional patterns as well.[19](https://www.railstutorial.org/book/beginning#cha-1_footnote-19)

The added files are initially placed in a *staging area*, which contains pending changes to our project. We can see which files are in the staging area using the `status` command:

```
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

  new file:   .gitignore
  new file:   Gemfile
  new file:   Gemfile.lock
  new file:   README.md
  new file:   Rakefile
  .
  .
  .

```

To tell Git we want to keep the changes, we use the `commit` command:

```
$ git commit -m "Initialize repository"
[master (root-commit) df0a62f] Initialize repository
.
.
.

```

The `-m` flag lets us add a message for the commit; if we omit `-m`, Git will open the system’s default editor and have us enter the message there. (All the examples in this book will use the `-m` flag.)

It is important to note that Git commits are *local*, recorded only on the machine on which the commits occur. We’ll see how to push the changes up to a remote repository (using `git push`) in [Section 1.4.4](https://www.railstutorial.org/book/beginning#sec-git_commands).

By the way, we can see a list of the commit messages using the `log` command:

```
commit af72946fbebc15903b2770f92fae9081243dd1a1
Author: Michael Hartl <michael@michaelhartl.com>
Date:   Thu May 12 19:25:07 2016 +0000

    Initialize repository

```

Depending on the length of the repository’s log history, you may have to type `q` to quit. (As explained in [*Learn Enough Git to Be Dangerous*](http://learnenough.com/git-tutorial), `git log` uses the `less` interface [covered](https://www.learnenough.com/command-line-tutorial#sec-less_is_more)in [*Learn Enough Command Line to Be Dangerous*](http://learnenough.com/command-line-tutorial).)

### [1.4.2 What good does Git do you?](https://www.railstutorial.org/book/beginning#sec-what_good_does_git_do_you)

If you’ve never used version control before, it may not be entirely clear at this point what good it does you, so let me give just one example. Suppose you’ve made some accidental changes, such as (D’oh!) deleting the critical `app/controllers/` directory.

```
$ ls app/controllers/
application_controller.rb  concerns/
$ rm -rf app/controllers/
$ ls app/controllers/
ls: app/controllers/: No such file or directory

```

Here we’re using the Unix `ls` command to list the contents of the `app/controllers/`directory and the `rm` command to remove it ([Table 1.1](https://www.railstutorial.org/book/beginning#table-unix_commands)). As [noted](https://www.learnenough.com/command-line-tutorial#sec-removing_directories) in [*Learn Enough Command Line to Be Dangerous*](http://learnenough.com/command-line-tutorial), the `-rf` flag means “recursive force”, which recursively removes all files, directories, subdirectories, and so on, without asking for explicit confirmation of each deletion.

Let’s check the status to see what changed:

```
$ git status
On branch master
Changed but not updated:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

      deleted:    app/controllers/application_controller.rb

no changes added to commit (use "git add" and/or "git commit -a")

```

We see here that a file has been deleted, but the changes are only on the “working tree”; they haven’t been committed yet. This means we can still undo the changes using the `checkout` command with the `-f` flag to force overwriting the current changes:

```
$ git checkout -f
$ git status
# On branch master
nothing to commit (working directory clean)
$ ls app/controllers/
application_controller.rb  concerns/

```

The missing files and directories are back. That’s a relief!

### [1.4.3 Bitbucket](https://www.railstutorial.org/book/beginning#sec-bitbucket)

Now that we’ve put our project under version control with Git, it’s time to push our code up to [Bitbucket](http://www.bitbucket.com/), a site optimized for hosting and sharing Git repositories. ([*Learn Enough Git to Be Dangerous*](http://learnenough.com/git-tutorial) uses [GitHub](http://www.github.com/), but see [Box 1.4](https://www.railstutorial.org/book/beginning#aside-github_bitbucket) to learn the reasons why this tutorial uses Bitbucket instead.) Putting a copy of your Git repository at Bitbucket serves two purposes: it’s a full backup of your code (including the full history of commits), and it makes any future collaboration much easier.

Box 1.4. GitHub and Bitbucket

By far the two most popular sites for hosting Git repositories are GitHub and Bitbucket.The two services share many similarities: both sites allow for Git repository hosting and collaboration, as well as offering convenient ways to browse and search repositories. The important differences (from the perspective of this tutorial) are that GitHub offers unlimited free repositories (with collaboration) for open-source repositories while charging for private repos, whereas Bitbucket allows unlimited free private repos while charging for more than a certain number of collaborators. Which service you use for a particular repo thus depends on your specific needs.

[*Learn Enough Git to Be Dangerous*](http://learnenough.com/git-tutorial) (and some previous editions of this tutorial) use GitHub because of its emphasis on supporting open-source code, but growing concerns about security have led me to recommend that *all* web application repositories be private by default. The issue is that such repositories might contain potentially sensitive information such as cryptographic keys or passwords, which could be used to compromise the security of a site running the code. It is possible, of course, to arrange for this information to be handled securely (by having Git ignore it, for example), but this is error-prone and requires significant expertise.

As it happens, the sample application created in this tutorial is safe for exposure on the web, but it is dangerous to rely on this fact in general. Thus, to be as secure as possible, we will err on the side of caution and use private repositories by default. Since GitHub charges for private repositories while Bitbucket offers an unlimited number for free, for our present purposes Bitbucket is a better fit than GitHub.

(By the way, recently a third major Git hosting company has emerged, called [GitLab](http://gitlab.com/).Originally designed principally as an open-source Git tool you hosted yourself, GitLab now offers a hosted version as well, and in fact allows for unlimited public *and* private repositories. This makes GitLab an excellent alternative to GitHub or Bitbucket for future projects.)

Getting started with Bitbucket is straightforward, though it may take a little technical sophistication ([Box 1.1](https://www.railstutorial.org/book/beginning#aside-technical_sophistication)) to get everything to work just right:

1. [Sign up for a Bitbucket account](https://bitbucket.org/account/signup/) if you don’t already have one.
2. Copy your [*public key*](https://en.wikipedia.org/wiki/Public-key_cryptography) to your clipboard. As indicated in [Listing 1.11](https://www.railstutorial.org/book/beginning#code-cat_public_key), users of the cloud IDE can view their public key using the `cat` command, which can then be selected and copied. If you’re using your own system and see no output when running the command in [Listing 1.11](https://www.railstutorial.org/book/beginning#code-cat_public_key), follow the instructions on [how to install a public key on your Bitbucket account](https://confluence.atlassian.com/x/YwV9E).
3. Add your public key to Bitbucket by clicking on the avatar image in the upper right and selecting “Bitbucket settings” and then “SSH keys” ([Figure 1.15](https://www.railstutorial.org/book/beginning#fig-add_public_key)).

Listing 1.11: Printing the public key using `cat`.

```
$ cat ~/.ssh/id_rsa.pub

```

![images/figures/add_public_key](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/add_public_key.png)

Figure 1.15: Adding the SSH public key.

Once you’ve added your public key, click on “Create” to [create a new repository](https://bitbucket.org/repo/create), as shown in [Figure 1.16](https://www.railstutorial.org/book/beginning#fig-create_first_repository). When filling in the information for the project, take care to leave the box next to “This is a private repository.” checked. After clicking “Create repository”, follow the instructions under “Command line > I have an existing project”, which should look something like [Listing 1.12](https://www.railstutorial.org/book/beginning#code-bitbucket_add_push). (If it doesn’t look like [Listing 1.12](https://www.railstutorial.org/book/beginning#code-bitbucket_add_push), it might be because the public key didn’t get added correctly, in which case I suggest trying that step again.) When pushing up the repository, answer yes if you see the question “Are you sure you want to continue connecting (yes/no)?”

![images/figures/create_first_repository_bitbucket_4th_ed](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/create_first_repository_bitbucket_4th_ed.png)

Figure 1.16: Creating the first app repository at Bitbucket.

Listing 1.12: Adding Bitbucket and pushing up the repository.

```
$ git remote add origin git@bitbucket.org:<username>/hello_app.git
$ git push -u origin --all

```

The commands in [Listing 1.12](https://www.railstutorial.org/book/beginning#code-bitbucket_add_push) first tell Git that you want to add Bitbucket as the *origin* for your repository, and then push your repository up to the remote origin. (Don’t worry about what the `-u` flag does; if you’re curious, do a web search for “git set upstream”.) Of course, you should replace `<username>` with your actual username. For example, the command I ran was

```
$ git remote add origin git@bitbucket.org:railstutorial/hello_app.git

```

The result is a page at Bitbucket for the hello_app repository, with file browsing, full commit history, and lots of other goodies ([Figure 1.17](https://www.railstutorial.org/book/beginning#fig-bitbucket_repository_page)).[20](https://www.railstutorial.org/book/beginning#cha-1_footnote-20)

![images/figures/bitbucket_repository_page_4th_ed](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/bitbucket_repository_page_4th_ed.png)

Figure 1.17: A Bitbucket repository page.

### [1.4.4 Branch, edit, commit, merge](https://www.railstutorial.org/book/beginning#sec-git_commands)

If you’ve followed the steps in [Section 1.4.3](https://www.railstutorial.org/book/beginning#sec-bitbucket), you might notice that Bitbucket automatically rendered the repository’s README file, as shown in [Figure 1.17](https://www.railstutorial.org/book/beginning#fig-bitbucket_repository_page). This file, called `README.md`, was generated automatically by the command in [Listing 1.3](https://www.railstutorial.org/book/beginning#code-rails_command). As indicated by the filename extension `.md`, it is written in *Markdown*,[21](https://www.railstutorial.org/book/beginning#cha-1_footnote-21) a human-readable markup language designed to be easy to convert to HTML—which is exactly what Bitbucket has done.

This automatic rendering of the README is convenient, but of course it would be better if we tailored the contents of the file to the project at hand. In this section, we’ll customize the README by adding some Rails Tutorial–specific content. In the process, we’ll see a first example of the branch, edit, commit, merge workflow that I recommend using with Git.[22](https://www.railstutorial.org/book/beginning#cha-1_footnote-22)

![images/figures/bitbucket_default_readme](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/bitbucket_default_readme.png)

Figure 1.18: Bitbucket’s rendering of the default Rails README.

#### [Branch](https://www.railstutorial.org/book/beginning#sec-git_branch)

Git is incredibly good at making *branches*, which are effectively copies of a repository where we can make (possibly experimental) changes without modifying the parent files. In most cases, the parent repository is the *master* branch, and we can create a new topic branch by using `checkout` with the `-b` flag:

```
$ git checkout -b modify-README
Switched to a new branch 'modify-README'
$ git branch
  master
* modify-README

```

Here the second command, `git branch`, just lists all the local branches, and the asterisk `*`identifies which branch we’re currently on. Note that `git checkout -b modify-README`both creates a new branch and switches to it, as indicated by the asterisk in front of the `modify-README` branch.

The full value of branching only becomes clear when working on a project with multiple developers,[23](https://www.railstutorial.org/book/beginning#cha-1_footnote-23) but branches are helpful even for a single-developer tutorial such as this one. In particular, because the master branch is insulated from any changes we make to the topic branch, even if we *really* mess things up we can always abandon the changes by checking out the master branch and deleting the topic branch. We’ll see how to do this at the end of the section.

By the way, for a change as small as this one I wouldn’t normally bother with a new branch (opting instead to work directly on the master branch), but in the present context it’s a prime opportunity to start practicing good habits.

#### [Edit](https://www.railstutorial.org/book/beginning#sec-git_edit)

After creating the topic branch, we’ll edit the README to add custom content, as shown in [Listing 1.13](https://www.railstutorial.org/book/beginning#code-new_readme).

Listing 1.13: The new `README` file.`README.md`

```
# Ruby on Rails Tutorial

## "hello, world!"

This is the first application for the
[*Ruby on Rails Tutorial*](http://www.railstutorial.org/)
by [Michael Hartl](http://www.michaelhartl.com/). Hello, world!

```

#### [Commit](https://www.railstutorial.org/book/beginning#sec-git_commit)

With the changes made, we can take a look at the status of our branch:

```
$ git status
On branch modify-README
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

```

At this point, we could use `git add -A` as in [Section 1.4.1.2](https://www.railstutorial.org/book/beginning#sec-first_time_setup), but `git commit` provides the `-a` flag as a shortcut for the (very common) case of committing all modifications to existing files:

```
$ git commit -a -m "Improve the README file"
[modify-README 9dc4f64] Improve the README file
 1 file changed, 5 insertions(+), 22 deletions(-)

```

Be careful about using the `-a` flag improperly; if you have added any new files to the project since the last commit, you still have to tell Git about them using `git add -A` first.

Note that we write the commit message in the *present* tense (and, technically speaking, the [imperative mood](http://en.wikipedia.org/wiki/Imperative_mood)). Git models commits as a series of patches, and in this context it makes sense to describe what each commit *does*, rather than what it did. Moreover, this usage matches up with the commit messages generated by Git commands themselves. See [Committing to Git](https://www.learnenough.com/git-tutorial#aside-commit_messages) from [*Learn Enough Git to Be Dangerous*](http://learnenough.com/git-tutorial) for more information.

#### [Merge](https://www.railstutorial.org/book/beginning#sec-git_merge)

Now that we’ve finished making our changes, we’re ready to *merge* the results back into our master branch:

```
$ git checkout master
Switched to branch 'master'
$ git merge modify-README
Updating af72946..9dc4f64
Fast-forward
 README.md | 27 +++++----------------------
 1 file changed, 5 insertions(+), 22 deletions(-)

```

Note that the Git output frequently includes things like `34f06b7`, which are related to Git’s internal representation of repositories. Your exact results will differ in these details, but otherwise should essentially match the output shown above.

After you’ve merged in the changes, you can tidy up your branches by deleting the topic branch using `git branch -d` if you’re done with it:

```
$ git branch -d modify-README
Deleted branch modify-README (was 9dc4f64).

```

This step is optional, and in fact it’s quite common to leave the topic branch intact. This way you can switch back and forth between the topic and master branches, merging in changes every time you reach a natural stopping point.

As mentioned above, it’s also possible to abandon your topic branch changes, in this case with `git branch -D`:

```
# For illustration only; don't do this unless you mess up a branch
$ git checkout -b topic-branch
$ <really mess up the branch>
$ git add -A
$ git commit -a -m "Make major mistake"
$ git checkout master
$ git branch -D topic-branch

```

Unlike the `-d` flag, the `-D` flag will delete the branch even though we haven’t merged in the changes.

#### [Push](https://www.railstutorial.org/book/beginning#sec-git_push)

Now that we’ve updated the `README`, we can push the changes up to Bitbucket to see the result. Since we have already done one push ([Section 1.4.3](https://www.railstutorial.org/book/beginning#sec-bitbucket)), on most systems we can omit `origin master`, and simply run `git push`:

```
$ git push

```

As with the default README, Bitbucket nicely converts the Markdown in our updated README to HTML ([Figure 1.19](https://www.railstutorial.org/book/beginning#fig-new_readme)).

![images/figures/new_readme_bitbucket_4th_ed](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/new_readme_bitbucket_4th_ed.png)

Figure 1.19: The improved `README` file at Bitbucket.

## [1.5 Deploying](https://www.railstutorial.org/book/beginning#sec-deploying)

Even though this is only the first chapter, we’re already going to deploy our (nearly empty) Rails application to production. This step is optional, but deploying early and often allows us to catch any deployment problems early in our development cycle. The alternative—deploying only after laborious effort sealed away in a development environment—often leads to terrible integration headaches when launch time comes.[24](https://www.railstutorial.org/book/beginning#cha-1_footnote-24)

Deploying Rails applications used to be a pain, but the Rails deployment ecosystem has matured rapidly in the past few years, and now there are several great options. These include shared hosts or virtual private servers running [Phusion Passenger](http://www.modrails.com/) (a module for the Apache and Nginx[25](https://www.railstutorial.org/book/beginning#cha-1_footnote-25) webservers), full-service deployment companies such as [Engine Yard](http://engineyard.com/)and [Rails Machine](http://railsmachine.com/), and cloud deployment services such as [Engine Yard Cloud](http://cloud.engineyard.com/) and [Heroku](http://heroku.com/).

My favorite Rails deployment option is Heroku, which is a hosted platform built specifically for deploying Rails and other web applications. Heroku makes deploying Rails applications ridiculously easy—as long as your source code is under version control with Git. (This is yet another reason to follow the Git setup steps in [Section 1.4](https://www.railstutorial.org/book/beginning#sec-version_control) if you haven’t already.) In addition, for many purposes, including for this tutorial, Heroku’s free tier is more than sufficient.

The rest of this section is dedicated to deploying our first application to Heroku. Some of the ideas are fairly advanced, so don’t worry about understanding all the details; what’s important is that by the end of the process we’ll have deployed our application to the live web.

### [1.5.1 Heroku setup](https://www.railstutorial.org/book/beginning#sec-heroku_setup)

Heroku uses the [PostgreSQL](http://www.postgresql.org/) database (pronounced “post-gres-cue-ell”, and often called “Postgres” for short), which means that we need to add the `pg` gem in the production environment to allow Rails to talk to Postgres:[26](https://www.railstutorial.org/book/beginning#cha-1_footnote-26)

```
group :production do
  gem 'pg', '0.20.0'
end

```

Also be sure to incorporate the changes made in [Listing 1.5](https://www.railstutorial.org/book/beginning#code-gemfile_sqlite_version) preventing the `sqlite3` gem from being included in a production environment, since SQLite isn’t supported at Heroku:

```
group :development, :test do
  gem 'sqlite3', '1.3.13'
  gem 'byebug',  '9.0.0', platform: :mri
end

```

The resulting `Gemfile` appears as in [Listing 1.14](https://www.railstutorial.org/book/beginning#code-gemfile_pg_gem).

Listing 1.14: A `Gemfile` with added and rearranged gems.

```
source 'https://rubygems.org'

gem 'rails',        '5.1.2'
gem 'puma',         '3.9.1'
gem 'sass-rails',   '5.0.6'
gem 'uglifier',     '3.2.0'
gem 'coffee-rails', '4.2.2'
gem 'jquery-rails', '4.3.1'
gem 'turbolinks',   '5.0.1'
gem 'jbuilder',     '2.7.0'

group :development, :test do
  gem 'sqlite3', '1.3.13'
  gem 'byebug',  '9.0.6', platform: :mri
end

group :development do
  gem 'web-console',           '3.5.1'
  gem 'listen',                '3.0.8'
  gem 'spring',                '2.0.2'
  gem 'spring-watcher-listen', '2.0.1'
end

group :production do
  gem 'pg', '0.20.0'
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]

```

To prepare the system for deployment to production, we run `bundle install` with a special flag to prevent the local installation of any production gems (which in this case consists of the `pg` gem):

```
$ bundle install --without production

```

Because the only gem added in [Listing 1.14](https://www.railstutorial.org/book/beginning#code-gemfile_pg_gem) is restricted to a production environment, right now this command doesn’t actually install any additional local gems, but it’s needed to update `Gemfile.lock` with the `pg` gem. We can commit the resulting change as follows:

```
$ git commit -a -m "Update Gemfile for Heroku"

```

Next we have to create and configure a new Heroku account. The first step is to [sign up for Heroku](http://signup.heroku.com/). Then check to see if your system already has the Heroku command-line client installed:

```
$ heroku version

```

Those using the cloud IDE should see the Heroku version number, indicating that the `heroku` CLI is available, but on other systems it may be necessary to install it using the [Heroku Toolbelt](https://toolbelt.heroku.com/).[27](https://www.railstutorial.org/book/beginning#cha-1_footnote-27)

Once you’ve verified that the Heroku command-line interface is installed, use the `heroku`command to log in and add your SSH key:

```
$ heroku login
$ heroku keys:add

```

Finally, use the `heroku create` command to create a place on the Heroku servers for the sample app to live ([Listing 1.15](https://www.railstutorial.org/book/beginning#code-heroku_create)).

Listing 1.15: Creating a new application at Heroku.

```
$ heroku create
Creating app... done, fathomless-beyond-39164
https://damp-fortress-5769.herokuapp.com/ |
https://git.heroku.com/damp-fortress-5769.git

```

The `heroku` command creates a new subdomain just for our application, available for immediate viewing. There’s nothing there yet, though, so let’s get busy deploying.

### [1.5.2 Heroku deployment, step one](https://www.railstutorial.org/book/beginning#sec-heroku_step_one)

To deploy the application, the first step is to use Git to push the master branch up to Heroku:

```
$ git push heroku master

```

(You may see some warning messages, which you should ignore for now. We’ll discuss them further in [Section 7.5](https://www.railstutorial.org/book/sign_up#sec-professional_grade_deployment).)

### [1.5.3 Heroku deployment, step two](https://www.railstutorial.org/book/beginning#sec-heroku_step_two)

There is no step two! We’re already done. To see your newly deployed application, visit the address that you saw when you ran `heroku create` (i.e., [Listing 1.15](https://www.railstutorial.org/book/beginning#code-heroku_create)). (If you’re working on your local machine instead of the cloud IDE, you can also use `heroku open`.) The result appears in [Figure 1.20](https://www.railstutorial.org/book/beginning#fig-heroku_app). The page is identical to [Figure 1.12](https://www.railstutorial.org/book/beginning#fig-hello_world_hello_app), but now it’s running in a production environment on the live web.

![images/figures/heroku_app_hello_world](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_4th_edition/images/figures/heroku_app_hello_world.png)

Figure 1.20: The first Rails Tutorial application running on Heroku.

#### [Exercises](https://www.railstutorial.org/book/beginning#sec-exercises_heroku_step_two)

Solutions to exercises are available for free at [railstutorial.org/solutions](http://railstutorial.org/solutions) with any Rails Tutorial purchase. To see other people’s answers and to record your own, join the [Learn Enough Society](http://learnenough.com/society) at [learnenough.com/society](http://learnenough.com/society).

1. By making the same change as in [Section 1.3.4.1](https://www.railstutorial.org/book/beginning#sec-exercises_hello_world), arrange for your production app to display “hola, mundo!”.
2. As in [Section 1.3.4.1](https://www.railstutorial.org/book/beginning#sec-exercises_hello_world), arrange for the root route to display the result of the `goodbye`action. When deploying, confirm that you can omit `master` in the Git push, as in `git push heroku`.

### [1.5.4 Heroku commands](https://www.railstutorial.org/book/beginning#sec-heroku_commands)

There are many [Heroku commands](http://devcenter.heroku.com/heroku-command), and we’ll barely scratch the surface in this book. Let’s take a minute to show just one of them by renaming the application as follows:

```
$ heroku rename rails-tutorial-hello

```

Don’t use this name yourself; it’s already taken by me! In fact, you probably shouldn’t bother with this step right now; using the default address supplied by Heroku is fine. But if you do want to rename your application, you can arrange for it to be reasonably secure by using a random or obscure subdomain, such as the following:

```
hwpcbmze.herokuapp.com
seyjhflo.herokuapp.com
jhyicevg.herokuapp.com
```

With a random subdomain like this, someone could visit your site only if you gave them the address.[28](https://www.railstutorial.org/book/beginning#cha-1_footnote-28) (By the way, as a preview of Ruby’s compact awesomeness, here’s the code I used to generate the random subdomains:

```
('a'..'z').to_a.shuffle[0..7].join

```

Pretty sweet.)

In addition to supporting subdomains, Heroku also supports custom domains. (In fact, the [Ruby on Rails Tutorial site](http://www.railstutorial.org/) lives at Heroku; if you’re reading this book online, you’re looking at a Heroku-hosted site right now!) See the [Heroku documentation](http://devcenter.heroku.com/) for more information about custom domains and other Heroku topics.

#### [Exercises](https://www.railstutorial.org/book/beginning#sec-exercises_heroku_commands)

Solutions to exercises are available for free at [railstutorial.org/solutions](http://railstutorial.org/solutions) with any Rails Tutorial purchase. To see other people’s answers and to record your own, join the [Learn Enough Society](http://learnenough.com/society) at [learnenough.com/society](http://learnenough.com/society).

1. Run `heroku help` to see a list of Heroku commands. What is the command to display logs for an app?
2. Use the command identified in the previous exercise to inspect the activity on your application. What was the most recent event? (This command is often useful when debugging production apps.)

## [1.6 Conclusion](https://www.railstutorial.org/book/beginning#sec-beginning_conclusion)

We’ve come a long way in this chapter: installation, development environment setup, version control, and deployment. In the next chapter, we’ll build on the foundation from [Chapter 1](https://www.railstutorial.org/book/beginning#cha-beginning) to make a database-backed *toy app*, which will give us our first real taste of what Rails can do.

If you’d like to share your progress at this point, feel free to send a tweet or Facebook status update with something like this:

[I’m learning Ruby on Rails with the @railstutorial! http://www.railstutorial.org/](http://twitter.com/?status=I%27m%20learning%20Ruby%20on%20Rails%20with%20the%20@railstutorial!%20http://www.railstutorial.org/)

I also recommend signing up for the [Rails Tutorial email list](http://www.railstutorial.org/#email)[29](https://www.railstutorial.org/book/beginning#cha-1_footnote-29), which will ensure that you receive priority updates (and exclusive coupon codes) regarding the *Ruby on Rails Tutorial*.

### [1.6.1 What we learned in this chapter](https://www.railstutorial.org/book/beginning#sec-beginning_what_we_learned_in_this_chapter)

- Ruby on Rails is a web development framework written in the Ruby programming language.
- Installing Rails, generating an application, and editing the resulting files is easy using a pre-configured cloud environment.
- Rails comes with a command-line command called `rails` that can generate new applications (`rails new`) and run local servers (`rails server`).
- We added a controller action and modified the root route to create a “hello, world” application.
- We protected against data loss while enabling collaboration by placing our application source code under version control with Git and pushing the resulting code to a private repository at Bitbucket.
- We deployed our application to a production environment using Heroku.

1. Copyright © Randall Munroe and used unaltered under the terms of the [Creative Commons Attribution-NonCommercial 2.5 Generic](https://creativecommons.org/licenses/by-nc/2.5/) license.. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-1)
2. learnenough.com/story [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-2)
3. learnenough.com/command-line [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-3)
4. The most up-to-date version of the *Ruby on Rails Tutorial* can be found on the book’s website at <http://www.railstutorial.org/>. If you are reading this book offline, be sure to check the [online version of the Rails Tutorial book](http://www.railstutorial.org/book) at <http://www.railstutorial.org/book> for the latest updates. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-4)
5. *URI* stands for Uniform Resource Identifier, while the slightly less general *URL* stands for Uniform Resource Locator. In practice, the URL is usually equivalent to “the thing you see in the address bar of your browser”. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-5)
6. As of this writing, the command line, text editor, and Git tutorials are complete, and the other tutorials are in development. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-6)
7. railstutorial.org/help [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-7)
8. For example, to find the definition of a function called `foo`, you can do a global search for “def foo”. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-8)
9. c9.io/signup [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-9)
10. learnenough.com/command-line [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-10)
11. This is a typical example of technical sophistication ([Box 1.1](https://www.railstutorial.org/book/beginning#aside-technical_sophistication)). [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-11)
12. Similarly, `~> 4.0` would install version `4.9` of a gem but not `5.0`. This is especially useful if the project in question uses [*semantic versioning*](http://semver.org/) (also called “semver”), which is a convention for numbering releases designed to minimize the chances of breaking software dependencies. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-12)
13. As noted in [Table 3.1](https://www.railstutorial.org/book/static_pages#table-shortcuts), you can even leave off `install`, as the `bundle` command by itself is an alias for `bundle install`. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-13)
14. Normally, websites run on port 80, but this usually requires special privileges, so it’s conventional to use a less restricted higher-numbered port for the development server. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-14)
15. Here “C” refers to the character on the keyboard, not the capital letter, so there’s no need to hold down the Shift key to get a capital “C”. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-15)
16. The base URL for the Rails Tutorial Cloud9 shared URLs has changed from rails-tutorial-c9-mhartl.c9.io to rails-tutorial-mhartl.c9users.io, but in many cases the screenshots are identical, so the browser address bar will show old-style URLs in some figures (such as [Figure 1.12](https://www.railstutorial.org/book/beginning#fig-hello_world_hello_app)). This is the sort of minor discrepancy you can resolve using your technical sophistication ([Box 1.1](https://www.railstutorial.org/book/beginning#aside-technical_sophistication)). [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-16)
17. Your editor may display a message like “invalid multibyte character”, but this is not a cause for concern. You can [Google the error message](http://lmgtfy.com/?q=invalid+multibyte+character) if you want to learn how to make it go away. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-17)
18. learnenough.com/git [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-18)
19. Although we’ll never need to edit it in the main tutorial, an example of adding a rule to the `.gitignore` file appears in [Section 3.6.2](https://www.railstutorial.org/book/static_pages#sec-guard), which is part of the optional advanced testing setup in [Section 3.6](https://www.railstutorial.org/book/static_pages#sec-advanced_testing_setup). [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-19)
20. Because of how my public keys are set up on Cloud9, I created the repository as railstutorial and then added my main account, mhartl, as a collaborator. As a result, I can make commits under either account name. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-20)
21. See [*Learn Enough Text Editor to Be Dangerous*](http://learnenough.com/text-editor-tutorial) and [*Learn Enough Git to Be Dangerous*](http://learnenough.com/git-tutorial) for more information about Markdown. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-21)
22. For a convenient way to visualize Git repositories, take a look at [Atlassian’s SourceTree app](http://www.sourcetreeapp.com/). [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-22)
23. See, for example, the section on [Collaborating](https://www.learnenough.com/git-tutorial#sec-collaborating) in [*Learn Enough Git to Be Dangerous*](http://learnenough.com/git-tutorial). [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-23)
24. Though it shouldn’t matter for the example applications in the *Rails Tutorial*, if you’re worried about accidentally making your app public too soon there are several options; see [Section 1.5.4](https://www.railstutorial.org/book/beginning#sec-heroku_commands)for one. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-24)
25. Pronounced “Engine X”. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-25)
26. Generally speaking, it’s a good idea for the development and production environments to match as closely as possible, which includes using the same database, but for the purposes of this tutorial we’ll always use SQLite locally and PostgreSQL in production. See [Section 3.1](https://www.railstutorial.org/book/static_pages#sec-sample_app_setup) for more information. [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-26)
27. toolbelt.heroku.com [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-27)
28. This solution, known as “security through obscurity”, is fine for hobby projects, but for sites that require greater initial security I recommend using [Rails HTTP basic authentication](http://lmgtfy.com/?q=HTTP+basic+authentication). This is a much more advanced technique, though, and requires significantly more technical sophistication ([Box 1.1](https://www.railstutorial.org/book/beginning#aside-technical_sophistication)) to implement. (Thanks to Alfie Pates for raising this issue.) [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-28)
29. railstutorial.org/email [↑](https://www.railstutorial.org/book/beginning#cha-1_footnote-ref-29)
