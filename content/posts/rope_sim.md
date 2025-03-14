---
title: "Rope Simulation in C++"
summary: "Personal project implemented in the 4th Group Game at TGA -->"
tags: ["gameplay","physics"]
ShowToc: false
TocOpen: true
Weight: 5
background: "../../images/ropeCover2.png"
# text_color: "#692d09"
---
| |  |
|----------------------------|------------|
| **Type:**     |Personal Project|
| **Engine:**   |The Game Engine – The Game Assembly's in house C++ engine|
| **Intent:**   |I was interested in learning more about game physics and decided to implement rope simulation from scratch.| 

This is a personal project that I ended up adding to the 4th game project at The Game Assembly.<br/>
Here's a quick summary of how it works. 

## The Simulation
The simulation uses **nodes** and **springs**.<br/>
The **nodes** are dynamic physics objects, meaning that they have a mass and are affected by forces added to them.<br/>
**Springs** connect the nodes and apply force to them based on a relationship between the spring's natural- and current length.
![Rope Test](../../gifs/rope2D.gif)
##### *Showcasing the functionality of changing spring length and adding/removing nodes in run time*
<br/>

```c
// Looping over the nodes, calculating force added by springs
// index1, index2 - Indices of the nodes connected to the spring

spring.vector = myNodes[index1].position - myNodes[index2].position;
spring.direction = spring.vector.GetNormalized();

float tooLongBy = spring.vector.Length() - MAX_LENGTH;
if (tooLongBy > 0.f)
{
    myNodes[index1].posistion -= spring.direction * tooLongBy;
    spring.vector = myNodes[index1].position - myNodes[index2].position;
}

float spring.Length = spring.vector.Length() - SPRING_LENGTH;

Vector3 springForce = SPRING_STIFFNESS * spring.length * spring.direction;
myNodes[index1].AddVelocity(springForce);
myNodes[index2].AddVelocity(-springForce);
```
<br/>


## The Visualization
The rope is an animated model that I created in Blender.<br/> 
Based on the simulation data I update the pose of the skeletal mesh.<br/>
This is how it turned out.

![Rope In Game](../../gifs/ropeInGame.gif)

```c
// Looping over the the skeleton of the rope mesh,
// calculating the joint transforms based on the simulation

Vector3 forward = springs[springIndex].dir;
Vector3 up = { 0.f, 1.f, 0.f };
Vector3 right = (up.Cross(forward)).GetNormalized();
up = forward.cross(right);
Quaternion quat = CreateFromOrthonormalBasisVectors(right, up, forward);

Matrix4x4 jointRotation = CreateRotation(quat.GetEulerAnglesDegrees());
Matrix4x4 jointPosition = CreateTranslationMatrix(myNodes[nodeIndex].position);
modelPose.JointTransforms[joinIndex] = jointRotation * jointPosition;
```

## Credits & inspiration
[Video](https://youtu.be/0WaDxYuD9S8?si=kiFzpYAY5c4veVde) going over basic rope simulation