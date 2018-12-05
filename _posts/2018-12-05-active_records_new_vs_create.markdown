---
layout: post
title:      "Active Record's New vs. Create"
date:       2018-12-05 11:34:06 -0500
permalink:  active_records_new_vs_create
---


While coding my Rails final project, I encountered a pesky problem. I was trying to create an activity entry that associates to a user as part of a fitness app. Like you would expect, when a user creates a new activity entry, a user expects to see their activity in a show page. The issue was that calling Activity.new did not save the activity instance with an auto-incremented ID. I could not figure out why.

While searching for an answer on Google, I came across a StackOverflow answer that detailed my mistake. ActiveRecord’s new method creates a local object but does not validate it or save it to the DB, which explains why Activity.id was nil. By using the create method, I was able to instantiate a new object, validate it, and save it to the database.

