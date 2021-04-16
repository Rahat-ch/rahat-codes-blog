---
title: Ramadan Side Project Part 1
description: Building a side project for Ramadan
date: 2021-04-15
layout: layouts/post.njk
image: /../img/ramadanpart1.jpeg
tags:
  - ramadan-project-series
alt: Holy Quran and a bowl of dates
---

So on the Islamic calendar, we are currently in the month of Ramadan. This is when Muslims like myself spend a lunar month fasting from dawn till dusk and reflecting and dedicated more time to our faith. One thing I wanted to do this year was to use my skills in tech to make it easier for fellow Muslims to stay in tune with their faith. From that desire, Salat Scheduler was born. 

Salat means prayer, we pray five times a day and during Ramadan perform additional nighttime prayers as well. As someone whose professional life can often get in the way and make it difficult to pray I knew other Muslims shared a similar issue. We book meetings, lunch, and sometimes heads-down work time on our calendars and make sure we adhere to that schedule. Our professional lives often consume a lot of our time and it can be very easy to let our prayers fall through the cracks. 

The solution I came up with was an app that combed through your calendar and found empty slots within the time frames for each prayer and booked ten minutes for you to go and pray. I tweeted about this and that tweet can be found here:

https://twitter.com/Rahatcodes/status/1381814424059658240

It was wild to see how many people really loved the idea and I immediately understood this would be an incredibly useful app for Muslims in the workforce.

I received a lot of messages asking to be a part of this but ended up taking on two other devs and a designer to help me bring this to life. The hope is to open source this so it will be open for contributions from anyone once it is in a manageable state. 

Here are my current plans for this:

- Initially, I wanted to do a mobile application however it made more sense to stick to this being a web app/PWA since the target audience will likely be at a desk working on their computers while using this. 
- The app will be using the Nylas Calendar API in order to read and book time on people’s calendars.
- The app will be using a prayer times API which will give us time frames for praying based on the person’s city.
- The app will keep track of the number of hours of Salat that has been booked as a cool fun little metric.

I have ideas for future roadmap items but I think this is manageable to do during Ramadan and have something out hopefully before the month is over.

Some more technical stuff:

- NextJS for the Frontend
- Utilizing NextJS API routes serverless functions for backend logic
- Tailwind for styling 
- Luxon because no one wants to deal with dates in JavaScript
- Vercel for all things deployment


 I’m planning on sharing my progress on this as I go and share the process for how I build this. Give me a follow to keep up with the progress and be notified when this goes live!
