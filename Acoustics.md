---
title: Initial Acoustics Implementation
author: Syed Jawad Akhtar
email: syedjawadakhtar@gmail.com
---

## Acoustics Implementation - Survey, procurement & implementation

#### Introduction about acoustics and competitions using it
[Acoustics](https://en.wikipedia.org/wiki/Acoustics) is the branch of physics related to the study of mechanical waves in gases, liquids, and solids. [Underwater Acoustics](https://en.wikipedia.org/wiki/Acoustics#Underwater_acoustics) is the scientific study of natural and man-made sounds underwater. Applications include sonar to locate submarines, underwater communication by whales, et cetra. To make our AUVs of industrial level standards and perform properly among the different sounds produced underwater, various competitions all around the world oncorporate acoustic localisation tasks in there arena. For example in [Singapore AUV Challenge](https://sauvc.org/), [acoustic pingers](https://ocean-innovations.net/companies/rje-international/acoustic-pingers-and-transponders/) located at different props are used for [target acquisitions](https://sauvc.org/rulebook/#2.-target-acquisition) and [localization](https://sauvc.org/rulebook/#4.-localization)). Similarly the [Robosub competition](https://robosub.org/) conducted by AUVSI also plants diffrent frequency pingers to guide the vehicle around the arena. Check out [Resources - RoboSub](https://robosub.org/resources/) link for their configurations as they change the theme every year.

An acoustic localization system detects a frequency emitting source at a distance, using Time Difference of Arrival (TDOA) of the sound wave.

#### Our Goal
We chose this task to be ocmpleted as it's very tedious to make this system incorporate with the movements of vehicle as well as the equipments used is comparitively costly and complicated. And because of these downsides for student teams the points to accomplish has been increased by a large amount as compared to performing other tasks. Thus helping the teams win with large margins. Check [SAUVC Rulebook](https://sauvc.org/rulebook/) and [mission and scoring](https://robosub.org/resources/) of Robosub competitions.

#### Objective
Our first objective is to use the optimum number of hydrophones to detect two pingers emitting 37.5 KHz and 40 KHz frequencies, respectively. The placement of these two pingers are at two differnt locations in the SAUVC arena:
1. Yellow Flare
2. Red Drums
**[Figure of Red Drums and Yellow Flare]**


#### The survey
For this we picked up Robosub Journals of previous years of different teams([Past Programs - RoboSub](https://robosub.org/past-programs/)). 
The survey of hydrophones used by 2019 Robosub teams is [here](https://github.com/auvzhcet/AUV2k19/blob/master/hydrophones_study.md)
 
Check References for the survey for types of hydrophones, the number, company & placement with implementation.

#### Model we chose
We chose the [H2C hydrophones](https://www.aquarianaudio.com/h2c-hydrophone.html) from [Aquarian Audio](https://www.aquarianaudio.com/) with 3.5 mm TRS output connection. (Contact faculty advisor for prices and shipping details).
Prime importance of this model: Groves for easy mouting, 3.5mm conector & range of detection (10 KHz - 100 KHz)

For the microcontroller we chose [NI MyRIO](https://www.ni.com/en-in/shop/select/myrio-student-embedded-device)
Prime imporatnace of this model:
1. Inbuilt [FPGA](https://www.xilinx.com/products/silicon-devices/fpga/what-is-an-fpga.html) for audio processing
2. 3.5mm as well as 3 analog inputs for audio signals [Fig. NIMyRIO i/p ports]
3. In built IMU that can be used further for movement of the vehicle
4. WiFi connectivity


#### The placement of hydrophones  
They are placed at specific distances in an equilateral shape for accurate results.
Reference: Assistant professor Wajid Sir

The aproximated distance of the placement of the arrays was calcaulted to be ~ 3 in apart

#### The process:
1. Time Delay Of Arrival(TDOA):
Figure for 2-D plane detection using 3 hydrophones
The analog signals from the frequency emitter are detected by the hydrophones placed on our vehicle, which is then passed through a signal processing board (For that we're using National Instruments MyRIO microcontroller board.)
Then the signal is passed through Fast Fourier transform algorithms, for detecting the exact frequency.
The value thus obtained is then passed to the AUVs computer, which commands the thrusters to move towards the detected source. 

#### Future Work:
The assemble of all the components at one place and it's optimzation is required:
1. Connecting all 3 hydrophones to a microcontroller to recveive input without wire/connection interference
2. Processing of audio signals for higher frequencies (50 KHz)
3. Attaching to vehicle at a certain angle
4. Testing to eradicate reflections of signals form props and side walls of swimming pool

#### References
We looked in the 2012 paper **(insert document link)** of Istanbul Technical University
3 hydrophones - 2012 paper **(insert document link)** of FEFU University and DARYABIRD **(insert document link)** IIT Bombay Matsya 2.0, 2013 FEFU
Malardalen 2012 - H2C aquarian 2016 REDEFIANCE, 2016 Leviathan 3 H1C
2016 DORY 4 Teledyne
2013 ZYRA - used GCCPHAT (Generalized Cross Co relation PHase Transform) for finding [Delay of Arrival (DOA)](https://in.mathworks.com/help/phased/direction-of-arrival-doa-estimation-1.html) implementation 
Graphical Programming for Field Programmable Gate Arrays: Applications in Control and Mechatronics (PDF link)
