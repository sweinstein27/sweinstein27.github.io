---
layout: post
title:      "Sweat the Small Stuff"
date:       2018-10-05 15:11:37 +0000
permalink:  sweat_the_small_stuff
---


The Sinatra portfolio project was by far the most challenging and rewarding project thus far. While I had very little trouble building out the logic of my fitness app, getting the app to redirect and retain the propper parameters was a bit challenging.

The majority of issues I had were small errors that had major consequences. The first major issue was that I could not get to my users or workouts controller. After checking to see if they both inherrited from the app controller properly, I found on stackoverflow that I should make sure "run ApplicationController" was after the "use."  

The next problem I had to overcome was that redirects were not properly interpolating. For example i wanted to redirect to "users/:id" but the browser was showing :id as a string not as the id of the user. I eventually discovered that Sinatra requires double quotations to interpolate. 

What I learned from all of this is how important it is to master the basics. I spent hours debugging an application and the fix was fairly simple. But without the pain, the reward of a finished app doesn't feel as rewarding!
