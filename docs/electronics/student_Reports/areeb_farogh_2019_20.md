---
title: Report for the tasks completed and engaged with during the Summer Internship at AUV club, ZHCET
authors: Mohammad Areeb Akhter, Farogh Alam
email-id: m.areebakhter401@gmail.com , faroghalam99@gmail.com 
---

## Objective

Understanding and learning the different Software and Hardware that could prove or are necessary for the vehicle.

## Introduction

A slight introduction of some of the major aspects of the tasks performed in the Internship.

- Arduino: Arduino proved to be one of the most inexpensive hardware and easy to learn as well as has a compatibility with wide range of sensors. Though its processing speed is slow, but due to its open source software, it’s one of the top microcontrollers in the world of Internet of Things, with a number of boards available to perform a number of different tasks, like Nodemcu, etc.
- Raspberry Pi: It’s a series of a small single-board computers developed for the sake of developers only to provide faster computing power and greater functions as compared to the other microcontrollers available in the market.
- Proteus: Proteus is a simulation software for the electric circuits, and due to its large developing community, a lot of new libraries for a number of sensors as well as a number of microcontrollers and other electrical components keep on coming, to make the software always up to date and ready for the task of performing and testing nearly any circuitry possible.
- Electronic Sensors: An electronic sensor is a device designed to indicate or measure something about the environment which it is operating in. This data is created mechanically or electrically with a digital command usually and is transmitted to the required source then, The data can be of many types, for example temperature, soil quality, air quality or detection of sound or readings obtained from Ultrasonic and Infrasonic waves, and many more.

## Equipment & Software used

|S. No.:| Software and Equipment | Version               |
|:-----:|:----------------------:|:---------------------:|
| 1     | Arduino                | UNO                   |
| 2     | Raspberry Pi           | 4 -(2 Gb)             |
| 3     | Arduino IDE            | 1.8.13                |
| 4     | Raspbian               | Kernel version (4.19) |
| 5     | Python                 | 3.6.2                 |
| 6     | OpenCV                 | 4.3.0                 |
| 7     | Jupyter Notebook       | 6.0.3                 |
| 8     | Nodemcu                | ESP8266               |
| 9     | Proteus                | 8.9                   |

And some sensors too like IMU, MLX2900, Ultrasonic, IR, etc.

## Procedure

- Interfacing of Arduino with sensors:
    1. Install Proteus and Arduino IDE on the system.  
    2. Install libraries of the different sensors in the Proteus from this [link](https://www.theengineeringprojects.com/2015/02/ultrasonic-sensor-library-proteus.html#:~:text=Ultrasonic%20sensor%20normally%20used%20is%20HC-SR04%2C%20which%20is,pin%20on%20ultrasonic%20sensor%2C%20which%20is%20analog%20pin)
    3. Compile the code of different sensors one by one on the Arduino IDE.
    4. Design the correct circuitry in the Proteus by bringing all the devices to the window from the ‘Devices’ section and do the proper wiring to the appropriate pins as mentioned in the code.
    5. Click on the Arduino Board in the Proteus and in the ‘Program File’ column, paste your location of the code and instead of the ‘.ino’ extension, change it to ‘.hex’ .
    6. Location of the code can be copied from the Arduino IDE after compiling the code without any errors, and dragging the bar of the error window upward to increase the area of the ‘dark side’ and then look for the location tag which would be between (“ ”)  and would be resembling something like “C/Documents/…………”.
    7. Run the simulation and rejoice if the code runs or open the error window and then check the connection of the wires with the pins provided in the code.

- Interfacing of Raspberry Pi with sensors:

    1. Download NOOBs from this [link](https://www.raspberrypi.org/downloads/noobs/)
    2. Extract the file from the `.zip` download into a folder.
    3. Download and install SD card Formatter and have an empty SD card (min. 16 Gb) at your hand. Format it with SD card Formatter.
    4. Copy the previously extracted files into the SD card without making any folder and right on the home screen.
    5. Plug in your SD card in the Pi, power it up and connect a HDMI chord to it to use a monitor as a screen. Boot it up.
    6. Plug in a mouse and choose the Raspbian option as it’s the most recommended operating system for Raspberry Pi and has a good Graphical User Interface. Give it some time to get installed.
    7. After installing and successfully booting up, it would ask for a password, set up a password and remember it and your default username would be Pi.
    8. Open the terminal and type `sudo apt-get update` for updating the drivers.
    9. To configure GPIO pins (general output and input), you would have to install one more thing. Type the command `sudo apt-get install rpi.gpio`.
    10. Make your own directory to save your codes in it by `mkdir <dir-name>`.
    11. To go from home directory to the new directory, type `cd <dir-name>`
    12. Now make a python file by running `touch distance.py`. Open this file in the vim editor by `vim distance.py` or in nano editor by `nano distance.py`.
    13. Copy your python code which in the vim editor after pressing 'i' and paste the code and check the pin numbers that you have wired your sensor with.
    14. Press “Esc” and then while pressing the SHIFT key type ' : ' and then followed by “wq” while in nano editor just press Ctrl + X and hit 'y' for yes.
    15. Then run the command `sudo python distance.py`.
    16. Voila! You would be seeing Distance of the objects you would want to see on the terminal.

!!! Note
    Due to the absence of many sensors at hand and library of Pi in Proteus, the procedure is just for ultrasonic sensor.

- Working on the Corona related theme project of the club:

    1. Researched for the different sensors that could be used for the thermal screening for the objects.
    2. Prepared the list of the different products available in the market.
    3. Worked on trying to simulate different sensors and checked their accuracy by studying their datasheet that were provided online.
    4. Finalised on the sensor **MLX2900**  because of its accuracy and distance to measurement ratio.
    5. Then started working on to study to how increase the accuracy with distance as its accuracy was 0.02`C which was great but the distance over which it was accurate was less than 2cm, which was not feasible as there was a computer vision branch of the project too and that required the person to be at least 1 feet away from the camera.
    6. Found a way of increasing the distance to accuracy ratio via an Infrared lens to diverge more and more infrared rays towards the sensor.

- Launching of a webserver and creating a webpage on Raspberry Pi:

This is Raspberry Pi project of displaying the sensor data over a webpage via **NGINX** and **UWSGI** server.

1. Install Flask, NGINX and UWSGI on Pi by `sudo-apt get install` command.
2. Sign in with root user as it would give much greater access by typing `sudo su` and set up a password for root user and remember it.
3. The corresponding file for UWSGI server that is, the ini file is also uploaded alongside.
4. The project is based on Python3 so you would have to install it.
5. The additional directories that need to be created are: /var/www/lab_app (to run the code more easily as the location and extensions are already settled inside the different file uploaded on my GitHub).
6. Install sqlite3 then at the command line type :

    1. `sqlite3 lab_app.db`
    2. `sqlite> begin;`
    3. `sqlite> create table temperatures (rDatetime datetime, sensorID text, temp numeric);`
    4. `sqlite> insert into temperatures values (datetime(CURRENT_TIMESTAMP), "1", 25);`
    5. `sqlite> commit;`
    6. To see the values stored in the database, type the following command:

        - `sqlite> select * from temperatures` then `sqlite>.exit`. Repeat the same process for the humidities table.

7. For automatically adding values to the database, we can use crontab.

    1. Open the command line and type `crontab -e` then from there choose nano then at the last of the page paste the below code for taking values every 10 minutes.
    2. `*/10 * * * * /var/www/lab_app/python  /var/www/lab_app/bin/env_log.py`
    3. For choosing the recurring time format i.e., `*/10 * * * *`, Go to: `crontab.guru`

!!! Note
    Currently the project is still under progress, as I’m trying to add Google charts to display the data precisely and pictorially.

- Interfacing and working of IMU was also studied from the Instructables website. Hands on is left for the future work as there was no IMU present at home.

If we go through the power specifications of AUV vehicle then apart from the thrusters everything can be powered by the power bank that we use to power Raspberry pi as camera, IMU, pressure transducer, everything is connected to Pi therefore the power ban could run it for one hour or so.

Then it comes to the thrusters, thrusters used are T200 that basically have power requirements of:
645 Watts for maximum thrust at 20 Volts and current supply of 32 Amperes
450 Watts for normal thrust at 18 Volts and current supply of 25 Amperes (voltage is taken more than normal, for calculation purposes)

Blue robotics has strictly instructed not to use the maximum throttle for a longer period of time and also not more than 22 Volts should be used in power supply as they could damage the Blue ESCs as the thrusters would be drawing a large amount of current and the power consumption would be fairly high, so I used 45 minutes as the ideal time for the vehicle to be working in normal range.
So, if we used a LiPo battery of 2100 Mah and voltage of 9.9 Volts than the battery pack would comprise of:
**{(x\25\*1000)\* 60} = 45**, x= the Mah required by us and that comes out to be x = 18750
Therefore, the number of LiPos we would require of 2100 Mah would be ~9 connected in parallel for being a good current source
For the voltage purposes, we would require 2 LiPos to be connected in series and that would provide the voltage of ~20 Volts.

## Results

- Interfacing of IMU as well as its working was understood.
- Successfully performed simulations of a number of sensors in Proteus with Arduino (as Pi was unavailable there) even some which could be used in the vehicle for water detection like the Rain sensor.
- Successfully wrote and run codes on Raspberry Pi with the sensors available at disposal via SSH protocol.
- Learnt the basics of computer vision via OpenCV and plan to learn more in the near future to understand and work in better coordination with the Computer Team.
- Worked and studied on the hardware technicalities of a project with other Club members related to Corona.
- Learnt the basic web development for managing the club Website, if needed.
- Learnt to launch a web server on Nodemcu, so as to control the devices over a local network.
- Learnt to create a web-server to display sensor data in tabular format which is stored in SQLite database and can be displayed pictorially also if needed.

## Future work

1. More time would be invested to gain more hands-on experience with Raspberry Pi environment and different tasks that could be done with it.
2. Work with different sensors as well as equipment to understand the working of the devices with the I2C pins.
3. Investing time and energy to learn Object identification with OpenCV python to use it with Raspberry Pi in the future.
4. Testing the knowledge gained of IMU and Rain sensor by using them on the vehicle in the future.
5. To go through of journals of other teams to study their devices and devise ways to make both the vehicles of the club work more efficiently, like the thruster orientation, using YAW, etc.
