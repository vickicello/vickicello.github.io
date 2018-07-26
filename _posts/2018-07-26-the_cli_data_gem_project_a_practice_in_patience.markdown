---
layout: post
title:      "The CLI Data Gem Project: A Practice in Patience"
date:       2018-07-26 14:57:16 -0400
permalink:  the_cli_data_gem_project_a_practice_in_patience
---


Nothing can quite describe the rush of euphoria I experienced after I ran ./bin/scene-cli for the millionth time - *and the program actually worked!*  But it took a lot of work to make it to that point.

I had difficulty setting my project and directories up in the beginning.  After watching Avi's CLI walkthrough, and after rereading the lessons about Github on learn.co, I thought I would be set to create my new project.  I made a new repo on Github, cloned it into the Learn IDE, and began to work.  However, I could not for the life of me get files to run or save.  Thankfully, with the help of other Learn.co students, I was directed to an extremely handy blogpost by Richard Austin Melchior: 

https://sillhouette.github.io/crowder_news_data_gem

and learned how to use bundler to create a ruby gem.  Thanks to the technical coaches at Flatiron, I was able to figure out  my environment file, require_relatives, how to sort out errors in my gemspec file, and why I wasn't able to run my cli.rb file (I should have been trying to run ./bin/scene-cli since that file had all of the requires and require_relatives set up to inable the program to run).

Once I hopped over the hurdle of simply setting up the file and learning how to get out of the temporary directory in the Learn IDE, the coding aspect was relatively straightforward.  I followed Avi's advice and wrote out 'the code I wish I had' first, and stated my goals for my CLI in pseudocode.  Over the course of a week and a half, I was able to build out my CLI gem: a program that scrapes concert information from the Cleveland Scene website (our city's free weekly magazine) and displays daily concert information, including event name, time, price, venue, address, and phone number to call for more information.

Although this project was definitely a challenge, both for my brain and my patience, I can't believe how much more I know now compared to last Monday!  I'm looking forward to the great leaps in ability I will make with each new portfolio project.




