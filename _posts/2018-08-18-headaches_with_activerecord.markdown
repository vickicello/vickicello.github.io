---
layout: post
title:      "Headaches with ActiveRecord"
date:       2018-08-18 18:09:17 +0000
permalink:  headaches_with_activerecord
---


ActiveRecord is an amazing Ruby gem that maps database tables to Ruby classes, saving the programmer time by utilizing powerful built-in functionality.  Instead of writing out long lines of SQL, we are able to rely on ActiveRecord's vast library of code, as long as we follow conventions (and remember to migrate our databases!)

I ran into some trouble in a few of the ActiveRecord labs, because I forgot to run rake db:migrate (using Rake, another wonderful Ruby gem) to migrate each change to the databases I was creating.  For that reason, whenever I ran rake db:migrate or even rake -T to see a list of rake tasks I could use to solve my problem, I was presented with a laundry list of errors.  

After hours of trying to alter my Rakefile and Gemfile (bad idea), editing my ActiveRecord version and other tweaking, I finally decided to do the unthinkable and delete my Github repository so I could start fresh.  It was a painful moment, but also a teachable moment - make sure to follow instructions and steps in sequence, and don't try to fly through labs!  Although I felt that I was saving time by going through the lab quickly, in the end it led to hours of headaches and diving around Stack Overflow to see if I could find a solution to the error messages I was seeing. 

I'll have to remember this moment in the future when I am a professional web developer - take time to get things right the first time, instead of trying to cut corners.

Side note: In the end, I was able to fix the error by actually following the suggestions that the error message gave me - to place bundle exec before my commands, and run ' bundle exec rake -T ', for example.  Another lesson is in there: take the time to really understand error messages before trying to fix things willy-nilly!
