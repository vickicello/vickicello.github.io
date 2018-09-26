---
layout: post
title:      "The Sinatra Portfolio Project: A Practice in Humility"
date:       2018-09-26 16:39:55 +0000
permalink:  the_sinatra_portfolio_project_a_practice_in_humility
---


It seems that each time I work my way through the rigors of a portfolio project, a central theme or lesson presents itself to me.  For the CLI project, the lesson was patience - understanding that programming is about a lot of small mistakes, and a lot of small fixes.  But by being patient and working your way through errors, you will eventually arrive at a working, functional application or project.

For my Sinatra Porject, the lesson was humility.  Having worked my way through the Sinatra section rather quickly, I thought I knew exactly what I wanted to do, and how to execute every step in my portfolio project.  Unfortunately, as I began work on the structure, I realized that my understanding of some of the foundations of the MVC model were shaky.

My original plan was to create a reading list app, where users could post a book or article they'd like to read, could search their list by topic, and could also click on links to view these books or articles online, in addition to being able to leave comments about the book.  This is an app that I personally would find very handy, because I never seem to have the time to read every article and/or book that I'd like to read, so having them all in one place with notes about why I want to read them would be very useful.

Seeing as we already have similar apps (Goodreads, for one), I thought that I could create one, no problem!  But as soon as Join Tables and has_many: through relationships came into the fold, I realized that I was way over my head.  If I wanted to work my way through all of the additional functionality, I would be working on this project for a month (instead of the two-week timeframe I gave myself).

So, I scaled way back.  Now, My ReadingList only has models for Users and Books (no articles, topics, or URLs, sadly).  But it was important for me to scale back so that I was left with a simple, yet functional app.  Even after reducing components down, I still struggled with coordinating my views with my routes.  However, if I hadn't pared the program down, the code would have been much messier, and the program less functional.

After completing My ReadingList, I feel more confident in my understanding of MVC applications, Sinatra, and ActiveRecord.  Hopefully, after honing my skills throughout the rest of the curriculum, I'll be able to return to My ReadingApp and add in more complexity and functionality - the right way.
