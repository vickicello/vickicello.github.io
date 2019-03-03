---
layout: post
title:      "Garden Planner: Final Portfolio Project"
date:       2019-03-03 01:04:20 +0000
permalink:  garden_planner_final_portfolio_project
---


I can't believe I'm finally here!  As I'm finishing up the final touches on my fifth and final portfolio project, I'm reflecting on everything I've learned about React and Redux, and using a Rails API, through this project.

Here are a few snaffoos I've run into along the way:

Setting up the Rails backend was actually quite simple.  I was able to get everything working quickly for the most part.  One thing I learned was how to add seed data for a Date object:

```
sow_by: Date.parse('2019-04-01')
```

Since my project was creating a garden planning app, I wanted users to be able to add a sow by date for each crop.  This is important to stay on top of, because some crops have to be seeded long before harvest.  To create the crops table, I just needed to add a column with the Date datatype.

I also ran into a CORS issue along the way.  I was stuck on this one for a while, because I was sure that I added the rack-cors gem to my gemfile, ran bundle install, and uncommented out the code in ```config/initializers/cors.rb```.  *But*, what I neglected to realize that I was entering the wrong 'origins' URL in the file - I was putting in the URL for my Rails server (localhost:3001) instead of the URL that would actually be requesting the resource (localhost:3000, where my React app was running).  So I quickly realized that 'origins' was referring to the URL that would be *requesting* resources from the Rails API, not the origin of the resources.  I'm glad that was a simple error to solve!

Setting up the client side was a little trickier.  While I was able to successfully create my fetch function and map over my Crop objects in my App.js, I quickly realized that I wasn't exactly following standard separation of concerns.  I also needed to incorporate Redux and Thunk to allow async requests, and establish a store.

The store basically allows the app to store data, such as form data, the current Crop at hand, and  a list of Crops, without making a fetch request to the API over and over again.  It also allows every component easy access to the state, and creates 'a single source of truth' for the state, making the app less prone to bugs and decreasing load time.  

So to incorporate Redux and Thunk, I wrapped my App component with a Provider component, so everything inside App has access to the store.  I then created Reducers and Actions to handle any actions that were required (submitting form data, creating a Crop, etc).  

One problem I ran into here was inside my ```createStore()``` function.  The Redux Devtools Extension was giving me an error.  I googled around and tried a few different solutions before realizing that I simply needed to wrap ```applyMiddleware``` and the devtools with ```compose()```.  This got rid of the error and allowed me to continue hacking away.

Another problem I came across was trying to figure out how to go back to my Crops index page after submitting a new Crop form.  I started out with simply clearing the form after submitting:

```
export const createCrop = crop => {
  return dispatch => {
    return fetch(`${API_URL}/crops`, {
      method: "POST",
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({ crop: crop })
    })
      .then(response => response.json())
      .then(crop => {
        dispatch(addCrop(crop))
        dispatch(resetCropForm())
      })
      .catch(error => console.log(error))
  }
}
```

I tried a few things here; I tried putting ```dispatch(push('/crops')``` at the end of my ```createCrop()``` function, but for whatever reason, this didn' work.  I then realized that I could simply add a line of code to the end of my ```handleOnSubmit()``` function in my CropForm component:

```
  handleOnSubmit = event => {
      event.preventDefault()
      this.props.createCrop(this.props.cropFormData).then(() =>
      this.props.history.push('/crops')
     )
    }
```

Using ```this.props.history.push('/desired-url')``` basically pushes a new entry onto the history stack, thereby redirecting the user to a different route.

Other than that, once I knew where all of my code should go, creating the client side was pretty easy.  I just had to remember to ```import``` any functions or Components that I needed, and everything worked very well.

I'm so excited to have completed such a huge milestone, and looking forward to graduation!
