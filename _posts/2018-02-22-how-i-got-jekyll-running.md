---
layout: post
title:  "How I Got Jekyll Running on Heroku"
date:   2018-02-22 16:31:16 -0500
categories: dev-docs
---

I got it working basically by following the [instructions here](https://www.jamesward.com/2014/09/24/jekyll-on-heroku). Mostly this is just to document for myself how it was accomplished.

### Pre-Reqs

Ok, there are some things I needed first:
+ Heroku account
+ Github account
+ Jekyll and dependencies all installed.

As well as,
+ A generated jekyll site with some basic content.


### Install Gems

I included the following gems in my project's Gemfile.
+ `gem "rack-jekyll"`
+ `gem "rake"`
+ `gem "puma"`

Then I ran `bundle install` from within project `root` to build in the new gems and install dependencies.

### Create Necessary Files and Rules

Next, I needed to create some files for the new gems to work with. Both of these files were created in `root`.
+ `$ touch Procfile`
+ `$ touch config.ru`

Inside `Procfile` (btw, no extension of that file), I added the following lines:

`web: bundle exec puma -t 8:32 -w 3 -p $PORT`

And inside `config.ru`, I added these lines:

`web: bundle exec puma -t 8:32 -w 3 -p $PORT`

### Stage, Comment, Commit and Push Changes

Then, I staged, commented, and committed these changes in git (using a client or the CLI) and pushed these changes to the master branch of the project on GitHub. I'll gloss over instructions on this because it could be done multiple ways depending on individual workflow.

### Deploy Site Build to Heroku

Finally, just run `git push heroku master` from within the project `root`.
