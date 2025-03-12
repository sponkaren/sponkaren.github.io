---
title: "JoltPhysics Library Integration"
summary: "Integrating JoltPhysics in our group Game Engine -->"
tags: ["physics", "engine"]
ShowToc: false
TocOpen: true
Weight: 2
---

As second year students at TGA we have the option of building our own game engine.<br/>
The game engine is developed and simultaneously used in a total of 4 projects.<br/>
There is a requirement for a physics library from in the third project, but I reasoned that having a physics library integrated already from the start would make sense. 
The main reason was that we could use the library as a general collision system as well. 
<br/><br/>I wanted to work with [JoltPhysics](https://github.com/jrouwe/JoltPhysics) in particular because I believed it would give great insight and flexibility to work with an open source solution.<br/><br/>I took on responsibility for implementation. Here's how it went. 

## Project 1, Pre Production - Make it work

The goal of the first project was to get our game engine development ready for project 2 where we'de actually make a game.<br/><br/>
The requirements that I identified were:<br/>
1. Integrate the JoltPhysics library in our engine<br/> 
2. Create system that bridges the JoltPhysics<br/> 
3. Create a simple interface for other programmers<br/>
4. Render colliders<br/> 
5. Enable tying custom logic to collision events<br/> 
 
<br/>...

![Make it work](../../gifs/joltMIW.gif)


## Project 2, Top Down ARPG - Make it right & Destructables

For the second project I saw two major focus areas for the physics- & collision system:<br/>
1. A more systematic way of creating and updating entities with colliders and rigid bodies
2. Some kind of destructables in the game – I wanted to simulate with physics

### Make it right


### Destructables
![Destructables in second project of year 2](../../gifs/destructables.gif)


## Project 3, FPS - Impact & Ragdolls
For project 3 we were heavily inspired by [Anger Foot](https://store.steampowered.com/app/1978590/Anger_Foot/) and used it as a reference game.
<br/>This put two implementation requirement on the physics- & collision system.
1. Collisions impacts need to be measured to determine if they deal damage 
2. Enemies should to ragdoll when they die

## Ragdolls
![Ragdoll import wip](../../gifs/ragdollWIP.gif)
![Ragdoll import wip 2](../../gifs/ragdoll_Import.gif)

### Credits/ inspiration
[Physics and Collision Library](https://github.com/jrouwe/JoltPhysics)