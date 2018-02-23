---
layout: post
title:  "My Basic Jekyll Workflow"
date:   2018-02-22 19:07:16 -0500
categories: dev-docs
---

These are my basic workflows right now (as best I understand them) for working with Jekyll + Heroku on a variety of common tasks.

### Create a Post

Using my text-editor [Atom](http://atom.io), I create a post, name it with the date and title, add the YAML front-matter (layout, title, date, and categories ) and save it into the project's `/_posts` directory. Changes can be previewed on the development server by running `bundle exec jekyll serve` in the terminal and visiting /localhost:4000, or, if the server is already running, simply by refreshing the page.

Next, I commit the changes (with comments) and push them up to GitHub.

Finally, I deploy to Heroku with `git push heroku master`.

### Make a Theme Change

All the .scss partials have already been imported into the project directory, so editing them directly is enough to override them. If I want to change variables, for example, I'd just open `_variables.scss` in the text-editor, write the changes, and save the file. The preview should take effect when a page is reloaded on the dev server.

**Note:** If changes are made to `_config.yml`, they will not update automatically on the preview server. Instead, in the terminal window that contains the running server process, press <kbd>control+c</kbd>. This will kill the server process. Then, I can run `bundle exec jekyll serve` to rebuild the site and relaunch the dev server.

When the last change has been made in a given commit, and it's time to deploy, the main.css needs to be recompiled. This must be done in this order:
```
$ bundle exec jekyll server
$ git commit -m meaningful_comment_text
$ git push master
$ git push heroku master
```
