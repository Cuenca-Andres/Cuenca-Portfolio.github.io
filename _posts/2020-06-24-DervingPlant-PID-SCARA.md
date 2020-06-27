---
layout: post
title: "Using MATLAB to Create a PID Simulator for SCARA Robot"
date: 2020-06-24
tags: [Arduino, DC Motors, PID, MATLAB, Robotics]
excerpt: "DC Motors, Quadrature Encoder, Arduino"
---

## Written by: Andres Cuenca

### Introduction

This post will introduce on how to build a PID (proportional, integral, derivative) simulator using MATLAB to generate
step response graphs. This post requires to have a solid background in mechanical and electrical systems.

<img src="{{ site.url }}{{ site.baseurl }}/images/industry-logos/matlab-logo.jpg" alt="">

Suppose a robotic linkage is driven by a DC motor, a timing belt, and gears. The goal is for the
DC motor to generate enough torque to rotate the robotic linkage to a desirable
angular position of the robot. Using a DC motor integrated with a quadrature encoder and connected to an Arduino,
it's achievable to set up a PID controller code to program the shaft of the motor to rotate the robotic linkage to a
specific position. However its require to tune the proportional, integral and derivative coefficients of the PID to achieve
a smooth motion path for a robot that is driven by each DC motor. To understand how to achieve this goal,
this MATLAB simulation program will properly tune each coefficient until the design criteria is met.

### Design Criteria




### Deriving Plant System for Joint of Robot

For this simulation program the first joint and linkage of the SCARA robot are driven by a timing belt, gears and DC motor.

Below is a diagram that illustrates a CAD model of the robot.
