# ParkingEaze
# PCF8574 LCD with HC-SR04 ultrasonic distance sensor. 
 
<img src="https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/case1.jpg" width="500" height="500">

## Table of Contents
1. [Introduction](#introduction-to-the-sensor-and-effector)
2. [Purpose](#purpose)
3. [System Diagram](#system-Diagram)
4. [Materials](#materials-required-to-build-this-project)
5. [Budget](#budget)
6. [Time Commitment](#time-Commitment)
7. [Setting up Raspberry Pi](#setting-Up-Raspberry-Pi)
8. [Hardware Testing](#hardware-Testing)
9. [Mechanical Assembly](#mechanical-Assembly)
10. [PCB Soldering](#pcb-Soldering)
11. [Unit Testing](#unit-Testing)
12. [Production Testing](#production-Testing)
13. [Resources](#resources)

## Introduction to the sensor and effector
 •PCF8574 LCD module (effector)
 -The Serial LCD  backpack built on PCF8574 IC uses the I2C bus to convert the parallel interface to a serial one.
 -The LCD needs only 2 wires SDA & SCL , apart from the power connections and ground.
 -There is a blue model which adjusts the contrast of the LCD.
 -The I2C device has a HEX address by which a microcontroller can communicate with it.
 
 •HC-SR04 distance sensor  (sensor)
 -This sensor uses sonar to determine distance to an object.
 -It has both transmitter and receiver modules.
 -It has some features like measuring Angle: 30 degree, Ranging Distance : 2cm – 400 cm/1″ – 13ft, Power Supply :+5V DC, Working Current: 15mA


## Purpose
The main goal of my project is to measure the distance of the car and display it on the lcd screen. The LCD screen will display the available parkig spots and will give indication and direction to the customers.

## System Diagram 
 This diagram shows the sensor and effector communication with each other using raspberry pi. 

![systemdiagram](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/diagram.png)

## Materials required to build this project
- Raspberry Pi
- HC-SR04 distance sensor
- PCF8574 LCD module
- 1k resistor and 2.2k resitor used as a voltage divider.
- Breadboard and jumper wires to test the connection.
- Socket Header to attach sensor and effector to the pcb and pcb to the raspberry pi.
- Acrylic case to enclose the whole circuit.

## Budget
![capture](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/budget.png)

## Time Commitment
This project can be done in one weekend. It will take about 2 to 4 days to recieve the parts. If you want to skip breadboarding then you can get started with the soldering which would take about 10 minutes but testing can take about 2 hours. After getting address, it should take one more hour to run the python script and get the readings.

## Setting up Raspberry Pi
First step after getting your raspberry pi is to set it up. Follow the steps below:
1. Download [Raspbian](https://www.raspberrypi.org/downloads/) to be installed on your raspberry pi.
2. Use [SDCardFormatter](https://www.sdcard.org/downloads/formatter_4/) to format your SD card and flash downloaded OS on your SD card.
3. Insert SD card in raspberry pi and connect the side devices like keyboard and mouse.
4. Switch on the power and finish the further setup.
