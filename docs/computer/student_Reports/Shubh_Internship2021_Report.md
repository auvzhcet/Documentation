---
title: Report for Internship at AUVZHCET
author: Shubh Singhal
email: shubhsinghal02@gmail.com
Duration: 1 July - 7 August 2021
---

## Table of Contents

- [Robot Operating System (ROS)](#ROS)
- [Computer Vision](#Computer-Vision)
- [Deep Learning](#Deep-Leaning)

## ROS

**Objective**: Complete ROS revision, Creating a basic talker & listener node.

**Resources**:
 - [ROS tutorials](http://wiki.ros.org/ROS/Tutorials)
 - [_towardsdatascience_  Blog](https://towardsdatascience.com/what-why-and-how-of-ros-b2f5ea8be0f3)
 - [ Overview Video on ROS](https://www.youtube.com/watch?v=vrFFnupcRL4)
 
 **Tech/Software used**: Ubuntu 20.04/ ROS Noetic
 
 **Summary**:
 ROS or Robot Operating System is a middleware, more of a low-level framework responsible for handling the communication between programs in a distributed system. The idea behind using ROS is creation of unique sub-programs (_nodes_) for each particular task. There are various parts of ROS such as topics, messages, nodes, services etc. In Robotics one has to deal with plenty of senosrs & actuators. Instead of creating a single large code-base to run the entire robot, ROS helps us in creating a distributed system for all these components.
 
 **Result**: Completed an overview of ROS from various resources. Created a talker/listener setup which detects `keyboard` inputs
 
 **Future Work**: Shift current code to ROS
 
 ## Computer-Vision (Open-CV)
 
 **Objective**: Understand the use of Open-CV for various image processing tasks 
 
 **Resources**: 
  - [OpenCV with Python- _pythonprogramming_](https://pythonprogramming.net/loading-images-python-opencv-tutorial/)
  
 **Used Libraries**: OpenCV, Numpy, Matplotlib
 
 **Summary**: OpenCV is a library mainly used for image/video processing tasks. Many complicated tasks such as facial-recognition, robot-vision, character-recognition, object-detection can be achieved by processing image/video data using this library. Specifically the image processing includes- edge detection, thresholding, blurring/smoothing, foreground/background extraction, corner detection, feature mapping etc. OpenCV is very convenient to use even while dealing with image data in deep learning models.
 
 **Result**: Created a OpenCV based script which basically tells the distance between camera and a particular object.
 
 ## Deep Learning for Computer Vision
 
 **Resources**:
   - [3Blue1Brown playlist on Neural Networks](https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi)
   - [Basics of Deep Learning (Udacity course)]
   - [Pyimagesearch Blogs](https://www.pyimagesearch.com/start-here/)
  
  **Tech/Software used**: Tensorflow/Google Colab
  
  **Summary**:
  Deep Learning assists in various computer vision tasks such as object/digit detection, classification, segmentation etc. Deep Learning models give very high accuracy in these areas. 3Blue1Brown's playlist on neural networks gives a very considerable introduction to the building blocks of deep learning. A significant fact is there are numerous pre-trained models available on tensorflow hub. Once familiar with the basics of DL one can jump onto state-of-the-art models like YOLO or Faster-RCNN which are used for majort computer vision tasks such as object detection.
  
  **Result**: Created a multi-class dog breed classifier using a pretained model from tensorflow hub
