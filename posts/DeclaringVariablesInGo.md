---
title: Declaring Variables in Go
description: My foray into the language with the best mascot. This is all about declaring variables in GO.
date: 2020-02-11
layout: layouts/post.njk
image: /../img/gopher.png
alt: Blue Golang Gopher with mohawk and beard
---

I've recently taken up learning Go on the side to broaden my knowledge as a developer and dive into some backend a little more. Since I'm learning this language from scratch there are lots of things I'm going to be sharing. This post starts off a little small with declaring variables in Go. 

Declaring variables is probably one of the first things you learn in any language after a Hello World! (We're skipping that here). Let's look at one way of doing a variable declaration:

```go
var name string = "Rahat"
```

Ok so...yay var looks like there isn't a let and const war in this language...that was a JavaScript joke. Go is a statically typed language so if you're like me and used to dynamic languages like JavaScript, Python, or Ruby you might say at first, oh this is different. In Go we keep the type of the variable consistent, so if name is a string I can't later replace it with some numbers, it's always got to be a string! 

That's great and all but Go gives us a nicer way of making a declaration:

```go
name := "Rahat"
```

Looked a little weird to me at first but this is great, Go will infer that you want the variable name to be a string and you won't have to declare the type every time. One thing to note is that this syntax would only be used when declaring. If I want to change my name, later on, I would do something like this:

```go
name := "Rahat"
name = "Goku"
```
Once I change my name to Goku I can just use an equal sign since I'm re-assigning the value of the name variable.

I hope you enjoyed the post, it would be great to see if others are learning Go as well, always looking for accountability partners! Feel free to send over a tweet or dm @rahatcodes.  