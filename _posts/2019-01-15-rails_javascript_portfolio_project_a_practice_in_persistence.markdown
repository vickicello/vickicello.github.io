---
layout: post
title:      "Rails + JavaScript Portfolio Project: A Practice in Persistence "
date:       2019-01-16 01:06:46 +0000
permalink:  rails_javascript_portfolio_project_a_practice_in_persistence
---


For my fourth portfolio project, I spent more time planning out exactly how I would implement the features required to pass my review.  This proved to be highly beneficial, and made working on the project a lot more straightforward.

Hanging on a wall in my workspace, I have written down some advice from a Medium article I read over the summer for programming newcomers (unfortunately at the moment I seem to be forgetting the author and title).  Basically, the article says that while learning a new concept or working on a project, one should: 1) Understand; 2) Plan; 3) Divide; and 4) if you're stuck, breathe - reassess - go through step by step - and/or Google it!

This time around, I spent a lot of time making sure I understood the JavaScript syntax and concepts before jumping in.  I definitely needed a refresher on scope, hoisting, ES6 classes, constructors, and prototypes.  It turns out that ES6 classes and prototypes became very useful in this project: 

```
$(document).ready(function(){
	class Hike {
		constructor(hikeData){
			this.name = hikeData.name
			this.description = hikeData.description
			this.state = hikeData.state
			this.completed = hikeData.completed
			this.id = hikeData.id
			this.userId = hikeData.user_id
		}
	}

//HTML prototype for formatting and listing user's hikes
	Hike.prototype.formatHike = function() {
		return `<li><h4><a class='show_hike_details' href="/hikes/${this.id}">${this.name}</a></h4></li>`
	}

//prototype for displaying Hike details
	Hike.prototype.showHikeDetails = function() {
		return `<li>${this.description} - ${this.state}<br></li>`
  	}
	}
```

Above, you can see my Hike class, which allowed me to recreate instances of @hike (in the Rails stack) to JSON objects (in the JavaScript stack).  My prototype functions allowed me to easily format the hike information as HTML using AJAX functions. 

I already mentioned planning.  This made the third step, dividing, much easier.  I divided up each of the project requirements into steps, then broke down how I would build and meet those requirements in my Notes.md file.  Dividing the project up like this made the work easier, less stressful, and more organized.  I could feel good taking a break after one section was finished, then write down notes for how I should proceed during the next sprint.

I definitely did get stuck a few times, so a combination of Googling around, watching review videos, checking out other student's code on Github, and attending office hours helped me through.  One problem in particular snagged my progress for a few days: how to create a click event on the child of an already-fired click event.  

My goal was to list a user's hike on their show page using AJAX.  In the list, the hikes would render as an anchor tag.  I wanted to be able to click on that anchor tag and show more information on the hike using another AJAX click event.

After not being able to grab the anchor tag, and changing up the code a few different times, I finally realized that I would need to include a second function, which I labeled ```listenForShowDetailsClick();``` inside the first function in order to be able to click on the link.  Here's how the code ended up playing out:

```
//render 'list of things' using function on the prototype 
//show a list of a user's hikes on the user show page
	$('a.show_user_hikes').on('click', function(event){
		$.ajax({
			url: this.href,
			method: "GET",
			dataType: "json",
			success: function(response){
				response.forEach(item =>{
					let newHike = new Hike(item)
					$('div.list_user_hikes ol').append(newHike.formatHike())
				})
				listenForShowDetailsClick();
			}
		});
		event.preventDefault();
	});

//render show page/'one thing'
//show more hike details on user show page
function listenForShowDetailsClick(){
	$('li h4 a').on('click', function(event){
		event.preventDefault();
		$.ajax({
			url: this.href,
			method: "GET",
			dataType: "json",
			success: function(response){
				let hike = new Hike(response);
				let html = hike.showHikeDetails();
				$('div.hike_details ul').html(html)
			}
		});	
	});
}
```

Notice how the second function listens for a click on ```li h4 a```, which appears because of the ```formatHike()``` prototype method on the Hike class after the first link is clicked.  It was a great feeling after finally getting this to work!

Once again, the portfolio project process was truly a challenge, but the lessons I learned and the amount that I grew from the experience made it all worth it.




