---
title: Report for Internship at AUV ZHCET
author: Shahab Ahmad Khan
email: shahabahmadkhan555@gmail.com
Duration: 1 July - 7 August 2021
---
## ROS (Robot Operating System)

**Objective**: ROS revision, Creating a basic talker & listener node
**Resources**:
 - [ROS tutorials](http://wiki.ros.org/ROS/Tutorials)
 - [ROS tutorials for beginners](https://www.youtube.com/playlist?list=PLk51HrKSBQ8-jTgD0qgRp1vmQeVSJ5SQC)
 - [ROS tutorials python - Beginners](https://www.youtube.com/playlist?list=PLAjUtIp46jDcQb-MgFLpGqskm9iB5xfoP)
 
 ### Summary:
Robot Operating System (ROS) is an open-source robotics middleware suite. Although ROS is not an operating system but a collection of software frameworks for robot software development. It is responsible for handling the communication between programs in a distributed system.There are various parts of ROS such as topics, nodes, services etc.

**ROS Master:**
The ROS Master provides naming and registration services to the rest of the nodes in the ROS system. It tracks publishers and subscribers to topics as well as services. The role of the Master is to enable individual ROS nodes to locate one another.
 
 **Topics:**
Topics are named buses over which nodes send and receive messages. Topic names must be unique within their namespace as well. To send messages to a topic, a node must publish to said topic, while to receive messages it must subscribe.

**Nodes:**
Nodes are at the center of ROS programming, as most ROS client code is in the form of a ROS node which takes actions based on information received from other nodes, sends information to other nodes, or sends and receives requests for actions to and from other nodes.

**Services:**
A service represents an action that a node can take which will have a single result. Nodes advertise services and call services from one another. 
