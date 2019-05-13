---
layout: post
title:      "Why Doesn’t My Search Query Work with Spaces?"
date:       2019-05-13 12:51:51 -0400
permalink:  why_doesn_t_my_search_query_work_with_spaces
---


Working with querying data from an API with user submitted queries, requires the knowledge of how queries are sent over the internet. This blog intends to help. 

A browser is not able to read certain character so they are encoded into a character your browser can read.  As you can see in the image below “special characters” are given an individual code that the browser can read.

 ![](https://i.imgur.com/rHWC1r1.png)
 
I was working on an application that allowed a user to search and play a song utilizing the Spotify API. The search results were only coming up for single word searches, while multiple words came back empty. The query looked normal in the debugger, but the response from the API was a 400 error, so something was wrong with the fetch request. In the Spotify API documentation multiple word queries were separated by *%20*. JavaScript has a handy function to achieve this called *encodeUri()*. The function automatically takes your URL and changes it to a browser readable state. 
I hope this blog will help you next time you need to deal with special characters in your search queries.





 



