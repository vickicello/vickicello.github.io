---
layout: post
title:      "Understanding Routes in MVC Applications"
date:       2018-09-05 17:34:23 +0000
permalink:  understanding_routes_in_mvc_applications
---


As I make my way through the Sinatra portion of the Learn.co curriculum, I find myself having to stop and think about control flow while setting up routes between the View and Controller portion of MVC applications.

On top of navigating the HTML for creating forms, selecting the correct GET or POST route can be tricky.  

It's helpful to think of the flow of execution:

User views the index page by making a GET request to our controller (app.rb):

![](https://i.imgur.com/otn5upG.png)

The user is prompted to complete a form (index.erb):

![](https://i.imgur.com/16VVOOe.png)

Notice how we create a POST request in the form tag.  This will also direct us to a new page,  /info, where our information will be displayed.

In our app.rb file, we create a POST request :

![](https://i.imgur.com/ZPrwXoI.png)

And finally, in our info.erb code, we incorporate the information gathered from the new instance of Person that was created when the user filled out the form.  This will display on our /info page:

![](https://i.imgur.com/aj9fgUh.png)

As our programs become more and more complicated, it's important to be able to follow the flow of execution to understand how our routes connect.


