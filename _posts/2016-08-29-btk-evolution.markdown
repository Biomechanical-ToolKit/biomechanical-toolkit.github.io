---
layout: post
title:  "BTK is evolving to become a bigger project!"
date:   2016-08-29 11:05
categories: btk openma
---

Dear users, 

Since 2009, the project BTK helped lots of people to simplify data management and accelerate their development. In 2015, during the [33rd ISBS congress](https://isbs2015.sciencesconf.org), I announced the future of BTK with the integration of biomechanical models (e.g. computation of joint kinetics and kinematics using conventional models like Plug-in Gait or Helen Hayes). 

One year later, this comes true! 

I would like to introduce a new open-source project called OpenMA (Open-source Movement Analysis library) and available on the website http://www.openma.org. This is a large evolution of BTK. Due to new internal concepts, the rewriting of the whole code, and eventually the usage of the acronym BTK in the USA, it was decided to rename the project to better fit with the new goals. 

The project is in heavy development, but it is already possible to: 

 - read the content of C3D files 
 - compute force platform wrench expressed at COP or PWA 
 - create a model using the Plug-in Gait (Vicon) markers set 
 - calibrate model parameters (validated against original Vicon results) 
 - reconstruct segment poses (validated against original Vicon results) 
 - compute joint kinematics (validated against original Vicon results) 
 - compute joint kinetics. 
 - write data to C3D files 
 - write calculuses with automatic data occlusion management (i.e. no need of a loop to test data validity on each sample!) 
  
The core is still in C++ and bindings will be available (e.g Matlab, Python 2 & 3). The code was successfully tested by different teams. 

The project wants to provide simple but powerful tools to accelerate development and simplify collaboration between teams. 

The goal is to create a large community with contributions coming from universities and compagnies as it already started. It is important to know that OpenMA is managed by a company as explained on the [website](http://openma.org/about/#history). The company will offer higher quality services and support than a single developer can offer in his spare time. 

If you are interested to use OpenMA or contribute to it (documentation, bug reports, feature requests, etc.), let us know. The more, the merrier! 
 