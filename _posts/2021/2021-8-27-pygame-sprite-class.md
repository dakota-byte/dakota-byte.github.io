---
title: Pygame RPG Prototype
date: 2021-08-27 12:00:00 -0400
categories: [Project]
tags:  [python, pygame, game]
---

watch me refuse to use a game engine

You can download this project on the projects tab under "Pygame: Spritesheets & Tilemaps"

### Creating a way to draw tilemaps in Pygame

Last week I decided to create something new in Pygame, and this time get far more complicated than a simple flappy bird game. I wanted to create some sort of RPG, with a world that I could create myself.

The hardest struggle I had was drawing sprites to the screen to actually visualize a real life world. I didn't want to just copy and paste some code that could do it for me, but everything online looked overly complicated. I decided to create my own way of doing it, and while it's definitely not the most efficient or intuitive way, I understand it completely.

I wanted to make it really easy to take a .csv file and a .png spritesheet and draw tiles onto the world.

At first it was extremely laggy, because of how much I was rendering to the screen and how many collisions I was trying to handle. After realizing that collisions only need to be detected for objects the player will actually touch, I improved the code. And this is what I had.

collisions:

https://user-images.githubusercontent.com/50030363/131174306-dc3c638e-3385-4753-9b34-5a70c0d6c194.mp4

The world moves, the player moves, and collisions are handled perfectly (perfectly enough).

After that, it wasn't hard to create tiles that had interaction involved. So I created a dialogue class and a way to change tilemaps, and here we have a pretty functional rpg.

dialouge and doors:

https://user-images.githubusercontent.com/50030363/131174352-a07ee0bb-2e9a-4c89-81bb-aeaca57c8b63.mp4

At this point though, I was realizing how inefficient and tedious all my code was. I kept finding new bugs that would cause me to have to rewrite parts of my sprite handler.

And although it was fun figuring out how to do stuff, eventually it becomes a hassle and unenjoyable. And I didn't even get started on creating actual gameplay...

### Pygame vs Game Engines

Theres a youtuber who goes by the username DaFluffyPotato, who's created games using Pygame for over 7 years. His most popular video, "Why I'm Glad I Didn't Use a Game Engine" discusses just that. The benefits he feels that he recieves from using a graphics library over a traditional engine like Unity.

Essentially, he feels that the skills you learns by creating games from the ground up are more transferable to industry level jobs. Unless you specifically plan to pursue a career in game dev, using a game engine limits what you learn.

When using a game engine, you're learning to use the abstractions of the engine. When using a graphics library, you're learning to turn ideas into code, designing things on your own.

He later released a followup video clarifying that game engines are not fundamentally bad, as many viewers misunderstood. You can still gain problem solving skills through a game engine. But game engines rely heavily on knowing its specific abstractions and functionality.

In the end, it comes down to personal preference and goals. Although game engines handle a lot of stuff like rendering for you, and make collisions easier to implement, there is still a lot you need to create yourself. You still have to code the functionality of a game.

Creating a boss, for example, may be the same in Unity and Pygame. The behavior of the boss, the player mechanics, etc., would have similar logic. However, in pygame you have the extra step of having to render everything. 

### My opinions

Using a game engine is definetly easier than starting from scratch with Pygame. You can still learn a lot in Unity, especially since you can create much more complex games with much less effort. After writing my own, awful, sprite and tilemap handler in python, I've come to appreciate games made using basic graphic libraries. Using Unity makes it easier to get your functionality into a game, without having to worry about reimplementing basic physical constraints. I enjoy being able to focus on the design and software principles needed to implement features and systems, without having to worry about the systems / libraries I'm using to get the result.
