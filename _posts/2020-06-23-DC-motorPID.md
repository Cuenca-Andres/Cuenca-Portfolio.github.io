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

Often times when a DC motor is purchase a manufacture specifications sheet will have
the proper coefficients for the Kp, Ki and Kd. However, when this information is not available or if a PID controller is
integrated to a plant system that is derive from a electro-mechanical equations of the load and inertia acting on the DC motor,
 then proper tuning is required.  

In this example, a SCARA robot was designed and dimension from scratched. Below are
some drawings to illustrate how the DC motors were mounted to the robot model.


<img src="{{ site.url }}{{ site.baseurl }}/images/scaradrawing1.jpg" alt="">

The first motor drives the first and second rotating linkage. The second motor is directly
coupled to the second rotating linkage.


<img src="{{ site.url }}{{ site.baseurl }}/images/scaradrawing3.jpg" alt="">

Part of process of integrating the PID controller to the plant system equation is to
analyze the mass and load inertia of the entire model and apply this process to find
the proper tuning variables that can meet the design specifications such as achieving
zero steady-state error, low rising time and low overshoot.



Tuning these variable is crucial to achieve a smooth and desire angular velocity and angular position for
the DC motor. It would take hours of making assumptions for properly tuning these variables.
However I complied a MATLAB script that can save time and analyze step response graphs
that fluctuate given the electro-mechanical equations of the DC motor and robotic arm. Analyzing
the step response graphs can determine the overshoot, settling-time, and achieve a steady-state error equal to zero.
Below is a MATLAB script was complied to represent the linkages of a SCARA robot.


* post matlab script here

### Arduino Code
[Arduino PID Code for DC Motor](https://github.com/Cuenca-Andres/RoboticsControlsSystem/blob/master/Arduino_PID_Controller_DC-Motor)
