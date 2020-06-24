---
layout: post
title: "Creating a PID Controller for DC Motor using Arduino"
date: 2020-06-23
tags: [Arduino, DC Motors, Quadrature Encoders, PID Controller, Robotics]
excerpt: "DC Motors, Quadrature Encoder, Arduino"
---

## Written by: Andres Cuenca

<img src="{{ site.url }}{{ site.baseurl }}/images/arduino-PID.jpg" alt="">

### Introduction
This DIY post covers on how to set up a DC motor with quadrature encoder, and
compile an Arduino PID controller code, to turn the shaft of the motor to any desire
setpoint value.

It's recommended to complete the project below before jumping into the Arduino PID controller.

[Reading Data from Quadrature Encoder of DC motor](https://cuenca-andres.github.io/Cuenca-Portfolio.github.io/DC_motor_quad/)


### Background on PID Controller

 For the DC motor shaft to turn at the desire angular position, the steady-state error of the angular position should equal to zero, without experiencing any excessive overshoot, and a low settling time within a range of 15-20 seconds. To reach this goal, a PID (proportional, integral and derivative) controller code was complied on an Arduino. There are three coefficients Kp, Ki and Kd that must be properly tuned to get an correct response for the DC motor. For this task, a quadrature encoder is applied to get feedback for the closed-control loop. Once the angular position is computed on the Arduino, the proportional, integral and derivative response are computed and the sum of all three coefficients will generate the output that must match to the desire setpoint.



### Flowchart of PID Controller

<img src="{{ site.url }}{{ site.baseurl }}/images/PID-flowChart.jpg" alt="">


### Tuning Kp, Ki and Kd variables

Often times a DC motor will have a specification sheet of proper coefficients for the
Kp, Ki and Kd. However, assuming that a motor was properly selected and size for a project,
for instance a robot linkage, then the mass and inertia of the rigid body must be analyzed.
Tuning these variable is crucial to achieve a smooth and desire angular velocity and angular position for
the DC motor. It would take hours of making assumptions for properly tuning these variables.
However I complied a MATLAB script that can save time and analyze step response graphs
that fluctuate given the electro-mechanical equations of the DC motor and robotic arm. Analyzing
the step response graphs can determine the overshoot, settling-time, and achieve a steady-state error equal to zero.
Below is a MATLAB script was complied to represent the linkages of a SCARA robot.

* post picture of scara There
* post matlab script here

### Arduino Code
[Arduino PID Code for DC Motor](https://github.com/Cuenca-Andres/RoboticsControlsSystem/blob/master/Arduino_PID_Controller_DC-Motor)
