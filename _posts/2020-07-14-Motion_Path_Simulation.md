---
layout: post
title: "Generating a Motion Path for SCARA Robot on MATLAB"
date: 2020-07-14
tags: [SCARA Robot, MATLAB, Forward Kinematics, Inverse Kinematics, Motion Path, Robotics]
excerpt: "Robotics, Motion Planning, Motion Path, MATLAB "
---

## Written by: Andres Cuenca

<img src="{{ site.url }}{{ site.baseurl }}/images/robotMotionPlant/scara_robot_model3.jpg" alt="">

## Introduction

This post introduces how to set up a motion path for a SCARA (Selective Compliance Robotic Arm) robot.
This custom made SCARA model was design on SolidWorks 2020. An urdf file that consist of the model's
dimensions, mass, inertia for each linkages, and stl files was generated on SolidWorks and can be imported to any
program such as ROS (Robotics Operating System) or MATLAB to view and control the linkages of the robot.

To generate a motion path of the robot the Inverse Kinematics was used for obtaining a limited and possible points that the end-effector
of a robot can travel. Generating a MATLAB code, optimizes this procedure and provides the user a map of possible px and py points.

Below is a graph generated on MATLAB showing possible px and py points of the end-effector of SCARA robot.
<img src="{{ site.url }}{{ site.baseurl }}/images/robotMotionPlant/PointsRRPR_robot.jpg" alt="">


## Required Programs and Background
* MATLAB (preferably version 2020a)
* MATLAB Robotics Control Toolbox
* Some Knowledge in Linear Algebra (matrices) would help
* Understanding of Forward and Inverse Kinematics


## Background

This post assumes that the user has an understanding on how to set up the Forward and Inverse Kinematic algorithms for a robot.  

## Demo Video


## GitHub Code
The MATLAB code is available on my Github page so any one can download and run the code on MATLAB.

[SCARA Robot Motion Path Simulation](https://github.com/Cuenca-Andres/RoboticsControlsSystem/blob/master/SCARA_Motion_Path_Simulation)
