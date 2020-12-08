---
title: Level up your Projects
description: A blog post on suggestions for taking your projects to the next level when preparing to showcase them while hunting for a job as a web developer. 
date: 2020-12-07
layout: layouts/post.njk
image: ../img/projects.jpg
alt: a laptop with code on the screen
---

Build, build, build. That's what I hear a lot of folks on the internet saying. The more you build the more experience you get with coding and the more you learn. This is true, I fully support this idea. However at some point we need to focus on more than just learning and showcase our skills in a way that can wow our potential employers. 

So maybe you've got some projects with some cool CRUD functionality, maybe you're having a hard time actually figuring out what to make that could be really useful. My philosophy is always build products instead of projects. Thats why I'm currently writing my book [Build a Product Become a Developer](https://www.buildaproduct.dev/).

Let's see how we can take some common projects and turn them into a product. 

## The most Important think to take away
Don't do these projects alone. Unless you're a private contracter/freelancer you're always going to be working with others. Even if you're a private contracter you will be at least communicating with someone regarding the work you're doing. Are you a bootcamp grad? Go through your fellow Alumni channels or people you went to bootcamp with and see if they would be down to work on a project together. Join online tech communities on Twitter or LinkedIn as well as different Slack Channels and Discord Channels. There are so many people out there trying to learn to code. Make something together, when you're out there doing the job you are going to be working with others and reading other peoples code. Make sure you do meaningful code reviews between each other. Reach out beyond just devs! There are folks trying to go into product, design, etc. Seek out communites where folks can get together and work on something even if its small.

### The ToDo App

I know I know but hear me out on this one. You've got your regular ToDo basic CRUD app that almost everyone has probably done some iteration of at some point while learning how to code. Let's take some stuff that transforms it into a full on Product. 

Create a backend:

Create a backend but don't deploy it as a monolith, deploy the backend on its own. What I mean by monlith is don't ship one big app that has both frontend and backend in one and fully deployed on something like Heroku. Instead of that let's deploy a seperate app for both the frontend and the backend and work out learning how to properly secure your backend. Let's add some authentication so folks can create usernames and passwords and acces their todo's anywhere they go.

Additional Features:

- Integrate your ToDo App with the Google Calendar API so people can add their ToDo's to their schedule. 
- Add Unit and Integration Tests with testing frameworks like Jest, Mocha, Chai, Cypress for end to end testing.
- Create a mobile app that hits the same API so users can have their todo's available on mobile devices as well as on the computer. 

Add all of these features in there and you have a full fledged ToDo list product. Will anyone buy it? I'm not sure but you can certainly put it out there and see. If you manage to get a few people using it though thats another nice story you can add to your interview about the fact that you have a deployed app people are actually using. 


### The Weather Application

Another common project I see is a weather application. You might integrate some type of weather API to get the users local weather based on their geolocation. This is a pretty dope exercise on its own, working with geolocation is quite interesting. How can we turn this into a product?

Let's go beyond just having a web app. Let's take a look at other API's that we can integrate for more services. Twilio is an awesome service that does many things but we'll focus on the thing they are known for the most. Giving us phone numbers to use for marketing and events. Grab yourself a Twilio number and create a service that sends a text message to your user letting them know what they should wear in the current weather. Alternatively this could be done as a mobile app and take advantage of the Notification system of your users phone. Now you've turned what was initially a weather app into something that can add value to someone who always forgets to take an umbrella when its raining. (like me...)

Here is something I want you to think about regarding this Weather App. We took a simple problem (like forgetting an umbrella) and created a solution for it. You don't need to solve a groundbreaking problem, you just need a solution to something. That's what I'm aiming at really showing you to bring your projects to the next level. 

### The Notes/Writing App

This is a todo app plus if we're being honest here. How do we turn this into a cool product? When I was in bootcamp, my team and I actually created an mvp of a service that is essentially a notes app but can become a product. 

We called it Litlab - cuz our writing is super lit...I'm sorry I won't do that again. It was all about writing and collaborating with others on works like short stories, poems, song lyrics etc. We created a google docs style document page that multiple people can write on at once along with a little chatbox to collaborate ideas on. We didn't quite get all the CRUD functionality going but if you want to fork it and complete it be my guest:

[Litlab Github Repository](https://github.com/Rahat-ch/LitLab)

The concept behind this evolved from the personal experience of myself and another one of our group members. We were both musicians and writers and thought it would be cool to have a place to easily collaborate with others on different works of writing. In this case we didn't neccasarily solve a problem per say. We thought about something nice to have and decided to try and build it. Whats a nice to have that you would like? Can it be turned into an app?

These are just a few examples of turning projects into products. In my view products are simply something that can truly add value to someone other than yourself. A project is just for your to learn something. We can take them to the next level by building things with a userbase in mind and learn even more not just about code but about collaboration and empathy. Something missing in a lot of bootcamp curriculums. 

Here are a couple challenges for you:

- Think of a problem you're facing and see if you can build an app that solves it. Don't worry about things that are already out there and exist, solve the problem you are having specifically. Remember it doesn't have to be groundbreaking, it can be as simple as forgetting your umbrella. Hit me up on [Twitter](https://twitter.com/rahatcodes) or [LinkedIn](https://www.linkedin.com/in/rahatc/) if you need help thinking through it.

- Create an Open source repo with these product suggestions and add some of your own and let others make PR's to add to it. I'll update this article with a link to the repo of the first person who does this and direct people to make PR's to it. 

