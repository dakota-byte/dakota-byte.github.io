---
title: Creating a Discord Bot
date: 2020-09-30 12:00:00 -0400
categories: [Project]
tags:  [discord, python]
---

a discord bot with a database

### What is Discord?

"Discord is a free voice, video, and text chat app that's used by tens of millions of people ages 13+ to talk and hang out with their communities and friends. People use Discord daily to talk about many things, ranging from art projects and family trips to homework and mental health support. It's a home for communities of any size, but it's most widely used by small and active groups of people who talk regularly."

### What is a Discord Bot?

You can create bots on Discord that automate tedious tasks, or supply entertainment. They have been used to moderate and regulate users, play music, play games, and there are many other creative uses.

### What I created

Giving that I use discord daily, I decided to use it to make school easier for me and my friends, during a time where no one could go outside and everything had to be done online. Originally, this was its only purpose, but it was fun to code so I added more to it.

#### Bell Functionality

Kody Bot (Its name) notified us when each period would start. For example, it would send a message saying "Period 8 is starting now". This was its only intended use at first.

#### Database implementation

Discord allows you to create "tags" that you can place on users, that describe and label them. For example, the "School" tag was used for everyone who wanted to utilize the bell sheducle Kody Bot had. However, a trusted user has to manually apply these to everyone. Instead, I created a way for users to automatically give themselves the tag. Using MongoDB with the Discord.py API, I could manage which tags existed anywhere, given I was logged in online. It was also really fun to integrate a database into the bot.

![database](https://user-images.githubusercontent.com/50030363/129261101-db16cf56-5c38-4ecc-97eb-faeca62e59ab.png)

#### BrainF###

BrainF is surprisingly easy to code, so I coded a compiler for it right into the bot.

![brainf](https://user-images.githubusercontent.com/50030363/129262333-f72bbf02-8ad3-42de-99d7-9fef27799fe6.png)

And thats about it. Twas fun :)
