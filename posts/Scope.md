---
title: Scope 
description: Lets talk about scope in JavaScript and how some code is only available in closure.  
date: 2020-12-08
layout: layouts/post.njk
image: ../img/scope.jpg
alt: a cool kid with a bucket on his head scoping out some danger with his binoculars
---

This word scope has probably come up a lot if you've been studying up on JavaScript. What exactly does it mean? If you've read my article on [closures](https://www.rahatcodes.com/posts/javascriptclosuresandpokemon/) then you might have a decent starting idea but lets do a bit more of a dive into this. 

Let's talk about the code below:

```javascript
  let count = 0;

  function incriment (){
    count ++
    console.log(count)
  }
  
  increment()
  increment()
  increment()
```

Not the most complex example but lets go through this code just a little bit. We have a count variable initialized with the value 0 and a function incriment which is declared. We then call increment causing the count to go up by 1. Notice that I did not pass the count value as an argument into incriment, our handy dandy JavaScript engine already knew what we were referring to. 

Let's think about it this way:

You've got a brand new red sports car with tinted windows. This obscures everyones line of vision to you but you can see everyone else quite clearly. Even though you are in your own closure inside the car the rest of the work is known to you. Anyone walking down the street however has no idea how many people are in the red sports car with tinted windows. This code behaves the same way. 

Outside of the function we just have a count and a call to increment. We do not have access to anything inside of the function and have no idea whats going on in there. When we enter the function itself we know everything that exists on the outside. We can see through our tinted windows and we know that there is a count variable declared that we can increase. Since we're updating the count each time we call increment we should see the numbers 1-3 come up in the counsel. 

Let's take a look at some more code: 

```javascript

  function incriment (){
    const count = 0
    count ++
  }

  console.log(count)
  
  increment()

```
Pretty similar to before except this time we declare the the count variable inside of the function and console log it outside the function. This won't work! You might get an error saying something along the lines of the fact that count is never defined. Yet we did identify it we can see it inside the function...oh inside the function. The console log outside of the function in the global scope has no idea what's inside of the increment function. Therefore it has no idea of knowing that count is a variable that was declared causing it to throw an error. 

So scope is what each of our functions and lines of code actually has access to. It is an important core part of JavaScript that can save you a lot of headaches if you understand it and are careful about it when writing your code. You always need to make sure you can use whatever variable you're trying to access.

