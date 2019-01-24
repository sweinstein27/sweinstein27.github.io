---
layout: post
title:      "Why Active Record Delete and Destroy are Not Interchangeable"
date:       2019-01-24 15:57:24 +0000
permalink:  why_active_record_delete_and_destroy_are_not_interchangeable
---


While working on my Rails with JS portfolio project for the FlatIron School I encountered a pesky problem, the destroy method was failing to destroy an instance called challenge. Challenge has dependenicies to a user class as well as a join table users_challenge. Destroy was unable to destroy the record in the join table, but I struggled to figure out why.

While researching, I found other methods to delete an ActiveRecord Object, perhaps I was just using the wrong one. I ran challenge.delete and the object was succesfully deleted, or so I thought. When I checked the join table the challenge_id was still there. 

ActiveRecord destroy and delete have key differences and are not interchangeable. When you invoke destroy or destroy_all on an ActiveRecord object, the ActiveRecord destruction process is initiated, it analyzes the class you're deleting, it determines what it should do for dependencies and runs through validations. When you invoke delete or delete_all on an object, ActiveRecord merely tries to run the DELETE FROM tablename WHERE conditions query against the db, performing no other ActiveRecord-level tasks. This led me to believe that destroy was not working do to an issue with dependencies. After a bit more searching, I found that by adding "dependent: :destroy" to the has_many relationships of the challenge class the associated records will be removed along with the parent. 
