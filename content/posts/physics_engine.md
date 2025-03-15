---
title: "JoltPhysics Library Integration"
summary: "Integrating JoltPhysics in our group Game Engine -->"
tags: ["physics", "engine"]
ShowToc: false
TocOpen: true
Weight: 2
---
| |  |
|----------------------------|------------|
| **Type:**     |Group projects at The Game Assembly|
| **Engine:**   |Tonic Engine – Our group's C++ engine built from scratch|
| **Intent:**   |Enable the group easily develop games that use collision logic and rigid body physics simulation| 

## Table of Contents
- [Introduction](#introduction)
- [Project 5, Pre Production](#project-5-pre-production)
    - [Make it work](#make-it-work)
- [Project 6, Top Down ARPG](#project-6-top-down-arpg)
    - [Make it right](#make-it-right)
    - [Destructibles](#destructibles)
- [Project 7, First Person Shooter](#project-7-first-person-shooter)
    - [Ragdolls](#ragdolls)
    - [Impact](#impact)
- [Credits & inspiration](#credits--inspiration)

## Introduction
As second year students at The Game Assembly, we have the option of building our own game engine in which we develop the 5th, 6th, 7th and 8th group projects.<br/>
There is a requirement for a physics library in project 7, but I reasoned that having a physics library integrated already from the start would make sense. 
The main reason was that we could use the library as a general collision system as well. 
<br/><br/>I wanted to work with [JoltPhysics](https://github.com/jrouwe/JoltPhysics) in particular because I believed it would give great insight and flexibility to work with an open source solution.<br/><br/>I took on responsibility for implementation. Here's how it went. 

## Project 5, Pre Production

The goal of the first project was to get our game engine development ready for project 2 where we'de actually make a game.<br/><br/>
The requirements that I identified were:<br/>
1. Integrate the JoltPhysics library in our engine<br/> 
2. Create system that bridges the JoltPhysics<br/> 
3. Create a simple interface for other programmers<br/>
4. Render colliders<br/> 
5. Enable tying custom logic to collision events<br/> 
 
<br/>...

### Make it work
![Make it work](../../gifs/joltMIW.gif)


## Project 6, Top Down ARPG

For the second project I saw two major focus areas for the physics- & collision system:<br/>
1. A more systematic way of creating and updating entities with colliders and rigid bodies
2. Some kind of destructables in the game – I wanted to simulate with physics

### Make it right


### Destructibles
![Destructibles in second project of year 2](../../gifs/destructables.gif)

## Project 7, First Person Shooter
For project 3 we were heavily inspired by [Anger Foot](https://store.steampowered.com/app/1978590/Anger_Foot/) and used it as a reference game.
<br/>This put two implementation requirement on the physics- & collision system.
1. Enemies should to ragdoll when they die. This is crucial feedback in Anger Foot.
2. Collisions impacts need to be measured to determine if they deal damage.

## Ragdolls
![Ragdoll import wip](../../gifs/ragdollWIP.gif)
![Ragdoll import wip 2](../../gifs/ragdoll_Import.gif)

## Impact

## Credits & inspiration
[Physics and Collision Library](https://github.com/jrouwe/JoltPhysics)