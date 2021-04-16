---
title: This in JavaScript 
description: What is "this" in JavaScript? 
date: 2021-01-05
layout: layouts/post.njk
image: /../img/2021.jpg
alt: the word this with a grassy backdrop
---

The word "this" is a word that has caused many JavaScript developers nightmares and caused many of us to utter profanities. Understanding "this" can be difficult because it can mean something else depending on when you are actually using it. Let's take a look at some code below to see if we can get a better understanding. If you want to try this out yourself create a js file in some folder of your choice and run it with node. 

```javascript
function whatIsThis() {
    console.log(this)
}

whatIsThis()
```

So if we use node to run a file with the above code in it then it seems like "this" is referring to the global object. Essentially all the built in nice javascript stuff that the global object has built in inside of node. If we ran this in the browser we would get the window object. That's the global object of the browser. 

Now let's take a look at "this" inside of a method:

```javascript
const me = {
    name: "rahat",
    sayHi() {
        console.log(`Hi! I'm ${this.name}`)
    }
}

me.sayHi()
```

So I've got a "me" object that has my name and a sayHi function. If I run this code then I will see the terminal output "Hi! I'm rahat". This is referring to the object that it's inside of. So in the first example we were just inside the global object. Now we're inside of this new me object I've defined. Another quick and dirty way of knowing what this is referring to when dealing with objects -> look to what is to the left of the dot. 

```javascript
me.sayHi()
```

The sayHi function is what has "this" inside of it so let's take a look at what is to the left of the dot that comes before it. It's me! So "this" is referring to me so this.name is rahat. 

What if we changed this to an arrow function?

```javascript
const me = {
    name: "rahat",
    sayHi: () => {
        console.log(`Hi! I'm ${this.name}`)
    }
}

me.sayHi()
```

If you run this function now it looks like...huh undefined. That's becuase with an arrow function the scope of "this" is inherited from its parent. This is called lexical scoping. The parent of this object is the global object. So we inherit "this" from the global object and the global object does not have a method called name. We can change this by explcitly using the .bind() method to make the arrow function recognize me as "this" but a general rule of thumb -> don't use arrow functions if you're using "this".