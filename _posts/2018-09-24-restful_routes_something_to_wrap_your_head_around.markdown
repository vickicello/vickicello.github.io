---
layout: post
title:      "RESTful Routes: Something to Wrap Your Head Around"
date:       2018-09-24 23:15:32 +0000
permalink:  restful_routes_something_to_wrap_your_head_around
---


This past week, I've been focused on two big projects: the Fwitter group project, and my own Sinatra portfolio project.  With both projects, I've run into some issues with setting up my routes correctly.  While I thought I understood the concept of RESTful routes, once my applications got more complicated and more controllers came into the fold, I found that I needed to go back to the basics to make sure I really understood how the routes were working in my projects.

One problem I ran into was confusing the URL with the directory in my project.  For example, a GET request for my books index page is simply `/books,` it shouldn't be `GET '/books/index`   

So the URL might look like www.myreadinglist.com/books ,  but the erb file would be `erb :'/books/index` .   
In my controller, I would express the GET action like so:

![](https://i.imgur.com/of8SzPU.png)

While I felt a little defeated that I needed to go back to basics in order to really wrap my head around this concepts, I figured it would be better to take the time to really understand the flow of execution before moving on with my project!
