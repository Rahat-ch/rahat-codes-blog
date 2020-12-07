---
title: Chocolate Chip Cookies and Recursion
description: Recursion for the rest of us. Check out this difficult Computer science concept broken down into simplet terms with examples in JavaScript.
date: 2020-02-03
layout: layouts/post.njk
image: ../img/cookies.jpg
alt: chocolate chip cookies and milk
---

Here is a 30 second video explaning the below concept! 
[![Recursion in 30 seconds](http://img.youtube.com/vi/LVkomHIbKR0/0.jpg)](http://www.youtube.com/watch?v=LVkomHIbKR0 "Recursion in 30 seconds")

Alright, let’s talk about Recursion! For a real world example of recursion, <a href = /posts/ChocolateChipCookiesandRecursion/ >click here.</a>

Did you click it? How many times did you have to click it? Did it frustrate you? Every time you click that link, this page just reopens, right? Well, that’s recursion for you. Recursion is when a function calls itself. You might be saying, “But wait Rahat, you can’t just infinitely loop through one function!” Well yeah, of course not. There are strategic ways that you can use recursion so that it can simplify your code without trapping your program in an infinite loop. I’m going to walk you through a simplified version of recursion, and then we’ll also try one that has math in it.

Let’s say you’re in the mood to have some chocolate chip cookies. You sit down and you’ve got yourself a jar of five cookies. With that in mind. let’s start creating a recursive function instructing us how to eat our delicious cookies. If you are not a fan of chocolate chip (but why though?), you can replace this example with any cookie of your desire or any food item of your choice. If you don’t like food, I’m not sure what to tell you...food is life.

```javascript
const eatCookie = cookie => {
  //enter some code here
}
```

Great, so I have a function now for eating cookies set up. I also have a cookie variable I’m passing through the function, this will be the number of cookies available for me to eat. Cool, so we have our cookies in a cookie jar all set up let’s get to eating!

```javascript
const eatCookie = cookie => {
    cookie = cookie - 1;
    console.log(“I ate a cookie there are “ + cookie + “ left.”)
}
```

Now our function is telling us we can eat a cookie and when we do there will be one less cookie. If we call the function now we will eat exactly one cookie. At this point, my wife would say “ok that’s it no more cookies”, but my wife isn’t here so we’re going to eat all the cookies.

```javascript
const eatCookie = cookie => {
    cookie = cookie - 1;
    console.log(“I ate a cookie there are “ + cookie + “ left.”)
    eatCookie(cookie)
}
```

Incredible right? If we call our function now and execute it, the function will then call itself and repeat the process so we can keep eating more cookies! The function will take in the remaining number of cookies as a parameter when executing itself again. Now there is still something wrong with this...see as much as I’d love to keep eating cookies I have to stop at some point. I’m sure as much as you all love the recursive functions you write...they all have to stop at some point. As it’s written now we’re just going to keep infinitely trying to eat cookies. Let’s make a slight adjustment.

```javascript
const eatCookie = cookie => {
    if (cookie === 0) return;
    cookie = cookie - 1;
    console.log(“I ate a cookie there are “ + cookie + “ left.”)
    eatCookie(cookie)
}
```

The final addition just lets us know that if the value of cookie is 0, meaning there are no cookies left, we return and the function will stop running. We don’t need to keep trying to eat cookies that do not exist! Let’s call our function with 5 cookies:

```javascript
eatCookie(5)
```

In your console your result should be:

```javascript
I ate a cookie there are 4 left.
I ate a cookie there are 3 left.
I ate a cookie there are 2 left.
I ate a cookie there are 1 left.
I ate a cookie there are 0 left.
```

Amazing we eat all of our cookies and stop once there are no more cookies in the cookie jar! So that was hopefully a super simple way of looking at recursion. Let’s take a look at a slightly more complex one.

Say you are given a number, n, and you are tasked with finding the value of n!.

What this means:

If n = 3
3!(read as three factorial)
3 x 2 x 1 = 6

We start with three and keep going down by 1 and multiply each number. Yay math.

So how can we write a function in JavaScript that will help us solve this? Did you say recursion? Why yes you’re correct!

Let’s break it down and write this function in parts:

```javascript
const factorial = n => {
  if (n < 0) return
  if (n === 0) return 1
}
```

So just like with the cookies, we’re going to start off by passing in a variable “n” which will be whatever number we’re trying to get the factorial of. We also already know that we need to stop our function at some point so I wrote in the logic this time that we need to stop if n is less than 0. The reason I say less than is that math is super weird and the factorial of 0 is 1. I won’t get into the details of that but just know that it’s just a thing in math. Now let’s write in the logic for getting our factorial:

```javascript
const factorial = n => {
  if (n < 0) return
  if (n === 0) return 1
  return n * factorial(n - 1)
}
```

So here we’re going to return the value of n being multiplied by the factorial of one number less than n. So like in the example about if we want 3! We should get 3 x 2 x 1, which is 6. Let’s pass 3 in as a parameter and see if we get 6.

```javascript
console.log(factorial(3))
```

You should be getting 6 for that if you followed along with what I’ve been showing you. Feel free to test it out with more cases! 