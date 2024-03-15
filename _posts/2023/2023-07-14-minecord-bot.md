---
title: Minecord Discord Bot
date: 2023-07-14 12:00:00 -0400
categories: [Project]
tags:  [discord, python]
---

turning 3D minecraft into a 1D text game

## Minecord (Kody Bot 2.0)

This project is not the first discord bot that I've worked on. I created a bot over quaratine to be used as utility amongst my highschool friends and I. Back then, I used MongoDB for user data and heroku to host the bot 24/7. Unfortunately, Heroku no longer has a free tier. So hosting is done locally on my PC, as other free hosting services are extremely slow and unreliable.

I'm also using Google Firebase now, just to try something new. I'm utilizing their Realtime Database which offers a very generous free plan. 

This bot is a game, unlike the last one, which was used for practicality. You can play the game by joining it's dedicated [Discord Server](https://discord.gg/eWZQWFwmpp), and if it's offline, don't be shy to ping me and I'll boot it up if I'm available :)

## Gameplay & How it works

The user runs commands, such as "/gather" and "/hunt" to get resources. Some commands, like "/mine", require that the user owns a pickaxe. They also need to "/eat" to refill hunger. Overtime, they'll be able to "/craft" stronger armor and tools which unlock new items that they can find. Once they've crafted an Enchanting Table, they can use the levels they earn from using all of these commands to "/enchant" their gear.

All user data is stored in a JSON. An updated JSON file is uploaded to the database anytime a command is run that alters the state of the users variables. I've organized my data in such a way to use the minimal amount of data for storing information. In essence, player data is a string that gets parsed by methods I've created. Good for memory, and a little more intensive on the CPU, which I deemed was a good tradeoff given my limited cloud storage.

Something I'm very proud of is using a little bit of photoshop and Pillow (Python Imaging Library) to create a very beautiful image of an inventory, similar to that of Minecraft.

## Screenshots of the game & Backend

<img src="assets/img/image1.png"/>

<img src="assets/img/image2.png"/>

<img src="assets/img/image3.png"/>

<img src="assets/img/image4.png"/>

<img src="assets/img/image5.png"/>

<img src="assets/img/image6.png"/>

<img src="assets/img/image7.png"/>

<img src="assets/img/image8.png"/>

<img src="assets/img/image9.png"/>

<img src="assets/img/image10.png"/>

<img src="assets/img/image11.png"/>
