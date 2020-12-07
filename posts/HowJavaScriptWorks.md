---
title: How JavaScript Executes
description: A brief overview of how JavaScript works. Lets get a better understanding of JavaScript by talking about the Execution context.
date: 2020-12-07
layout: layouts/post.njk
image: ../img/javascript.jpg
alt: a laptop with code on the screen
---

Oh JavaScript, you can be infuriating at best and completely unreasonable at your worst. Ever felt this why and wondered why JavaScript works the way it does? I definetely have, but diving a little deeper and understanding how JavaScript runs helped me get a better understanding of it. 

Let's start at the engine. If we're running JavaScript in the browser there is some type of engine that does the execution of the code for you. I use chrome so let's stick to that. In chrome the JavaScript engine that runs everything is called the V8 engine. A nifty little thing written in C++ that lets us not have to think about the low level stuff that goes on in the browsers and focus on the JavaScript code that makes dope things happen on the web. 

Now how does our little engine that could run all the JavaScript? Let's take a look at the code below:

```javascript

const me = "Rahat"

function sayHi(person){
console.log(`Hi ${person}`)
};

sayHi(me)

```

JavaScript is what we call a single threaded language, this is just a fancy way of saying it runs all of our code line by line. So let's break this down in terms of how the JavaScript engine might read this:

- We first declare a variable called me and set the value to be a string with my name.
- We declare a function called sayHi that takes an argument of a person

## Important note

There is a console log inside of the function. We need to consider how Javascript actually reads this. Let's say I wrote the code like this:

```javascript
  const me = "Rahat"

  function sayHi(person){
  console.log(`Hi ${person}`)
  };
```

I've done the two steps I've mentioned already of declaring a variable and a function. At this point however the JavaScript Engine does not care about what you wrote inside of the sayHi function. It's there, you wrote it but that code isn't being run. We need to actually call a function in order to execute the code inside of it. So coming back to the original code:

```javascript

const me = "Rahat"

function sayHi(person){
console.log(`Hi ${person}`)
};

sayHi(me)

```
We call the sayHi function by adding parentheses (you won't believe how long it took me to spell that correctly). Inside of the parentheses we pass it the me variable which is my name. We did that because when we wrote the function we specified that it needs a person to say hi to. Unless you call a function using parenthesis the code insde of it will never be read by the JavaScript Engine. 

With me so far? If you aren't don't worry you can always reach out to me with questions. Let's take a deeper dive. Consider an updated version of the code:

```javascript
const me = "Rahat"
const favoritePowerRanger = "Tommy Oliver"

function greenRanger(){
  console.log("OMG you're the green power ranger!")
}

function sayHi(person){
greenRanger()
console.log(`Hi ${person}`)
};

sayHi(me)
```

Not too different then before. I'm now declaring a variable for me and my favorite power ranger. (I tried watching an episode of Mighty Morphin Power Rangers a few weeks ago, super cringy). I've also got two functions declared. Now lets take a look at how this code is interpreted by the JavaScript Engine. Remember I said that the code inside of a function is not read until its called? You'll see that in the sayHi function I added a new line to call the greenRanger function. This means that the GreenRanger function won't run unless the sayHi function is running. 

So just like last time we call the sayHi function with parentheses and giving it an argument for a person. This time once we go into the sayHi function we call another function. Here is a nice little explanation of the execution context and call stack!

We call the sayHi function - we are now inside the execution context of sayHi, however, when we call the greenRanger function we now get shifted into the execution context of the greenRanger.

Lets take a look at this diagram to see how the execution context and call stack works. 

![call stack diagram of sayHi function](https://i.imgur.com/3itRLR4.png)

So we start by calling the sayHi function and fall into its execution context but then we immediately call the greenRanger function taking us into that execution function illustrated below:


![call stack diagram of greenRanger function](https://i.imgur.com/RoT5pFj.png)

You'll notice I placed the greenRanger function above the sayHi function. That's becuase this call stack obeys the rule of First in, Last Out. Meaning the first function we go into we cannot exit its execution context until everything inside of it is resolved. In this case we need to resolve the greenRanger function before finishing the rest of it. 

To summarize here is the order of events:

- JavaScript sees all variables and functions initialized
- It then sees that we called the sayHi function at the bottom of the page
- When it starts going through the code  in sayHi it sees a call to the greenRanger function
- It exuctes the greenRanger function the comes back into the sayHi function
- It finishes the remaining console log inside the sayHi function. 

That's the call stack and execution context. It is the steps the JavaScript engine will go through to enterpret and run the beautiful code you've written. Like I said earlier in this post if anything doesn't make sense feel free to reach out to me on the Twitter or LinkedIn handles below!
