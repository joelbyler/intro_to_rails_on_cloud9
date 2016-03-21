# Intro To Rails

## Goal

To teach you Ruby on Rails we are going to use a "Real World" example. You've decided to create a voting system for you and your friends to play with. You've decided at a minimum, you'd like to allow users to:

* view the topics sorted by number of votes
* vote on topics
* create, edit, and destroy topics

You've sketched up an initial screenshot of what you want it to look like:

  ![Browser window with topic titles that can be voted on, ordered by number of votes](images/finished_app.png)

## Meta-Goal

When you have completed today's goal of getting the basic application online you should understand:

* Basic Ruby syntax
* How to try your Ruby code (IRB)
* How to go from requirements to a new working Rails application
* How to get your application online
* The basic tools a RoR (Ruby on Rails) developer uses (source control, editor, console, local server)

## Schedule

* 1-ish hour of Ruby
* 4-ish hours of Rails, broken up in 1-ish hour steps

This is just a rough guideline, not a mandate. Some steps you'll go over and some you'll go under. It'll all work out by the end of the day. Probably.

## Requirements

We're going to be working with:

* Ruby 2.1 or 2.2 installed via RVM (Mac or Linux) or RailsInstaller (Windows)
* Rails 4.2.x
* Bundler
* SQLite
* The text editor of your choice

Everything should be set up the night before during our install-fest. Please ensure you have everything working before you show up for RailsBridge on Saturday.

You can verify that you have everything working by trying this out in your terminal:

```ruby
$ irb
>> 1 + 2
=> 3
>> require "active_support"
=> true
>> exit
$
```

If you can do that, you are probably good to go.

## Working Effectively and Efficiently
We highly recommend you do the following:

* Open your browser fresh or hide any windows you already have open.
  * Bring up one window with three tabs
  * One for this content
  * One for interacting with your app
  * One for the cloud9 browser based IDE
* Bring up your terminal and open 2 tabs:
  * One is for regular terminal stuff
  * One will be for IRB (a.k.a. Rails console). We'll explain later.
  * __NOTE__: in cloud9, this may be labelled `bash`. If you don't see any tabs with the title of `bash` on them, you can open a new tab under the cloud9 `Window` menu and choose `New Terminal`
* Hide all extra applications. Turn off Twitter, Facebook, IM, and all other distractions.

By minimizing the number of things you interact with, you reduce the amount of time spent switching between them and the context lost as you work through the lessons. Having 50 tabs open in your web browser gets confusing.

## Format

Each lesson will look like this:

---
# Step Title

## Goal:
Description of the current step.

## Steps:
`steps to take.`
```ruby
def code_to_write
  1 + 1
end
```
These are steps that we're going to take, but we're not sure why, that comes next.

## Explanation
Details of what the steps actually did, explaining the cause and effect.

---

## Next Step:
Go on to [Getting started](getting_started.md)
