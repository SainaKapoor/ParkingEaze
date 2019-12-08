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
 -PCF8574 LCD module (effector)
- The Serial LCD  backpack built on PCF8574 IC uses the I2C bus to convert the parallel interface to a serial one.
- The LCD needs only 2 wires SDA & SCL , apart from the power connections and ground.
- There is a blue model which adjusts the contrast of the LCD.
- The I2C device has a HEX address by which a microcontroller can communicate with it.
 
 -HC-SR04 distance sensor  (sensor)
- This sensor uses sonar to determine distance to an object.
- It has both transmitter and receiver modules.
- It has some features like measuring Angle: 30 degree, Ranging Distance : 2cm – 400 cm/1″ – 13ft, Power Supply :+5V DC, Working Current: 15mA


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
This project can be done in 1-2 weeks. It will take about 4 days to recieve the parts. The breadboarding and testing the connection might take 1-2 hour. Soldering headers, resitors just take 15 minutes. After this, importing the necessary libraries for the lcd and running the python code can take 1 more extra hour which includes troubleshooting step.

## Setting up Raspberry Pi
First step after getting your raspberry pi is to set it up.
 Following things you need:
1. Hdmi to VGA cable.
2. Power supply.
3. SD card.
4. Computer or any other screen.
5. Side devices such as mouse and keyboard.

 Follow the steps below:
1. Download [Raspbian](https://www.raspberrypi.org/downloads/) to be installed on your raspberry pi.
2. Use [SDCardFormatter](https://www.sdcard.org/downloads/formatter_4/) to format your SD card.
3. Insert SD card in raspberry pi and connect the side devices.
4. Switch on the power and finish the further setup such as settings, internet connection etc.

## Hardware Testing

After software installation, I connected the jumper wires from sensor and LCD to breadboard and breadboard to raspberry pi.

Wiring:
---
 - For HC-SR04 sensor
- Sensor VCC to 5V on Raspberry Pi.
- Sensor GND to GND on Raspberry Pi.
- Sensor TRIG to Pin 16 GPIO23.
- Sensor ECHO to 1k resistor, other leg of 1k resistor to Pin 18 GPIO24.

 - For PCF-8574 LCD module
- LCD VCC to 5V on Raspberry Pi.
- LCD GND to GND on Raspberry Pi.
- LCD SDA to Pin 3 GPIO2 / SDA
- LCD SCL to Pin 5 GPIO3 / SCL


If the connections are correct then you should be able to get address from your sensor.
![whatsapp image 2018-10-23 at 1 44 14 pm 1](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/display.jpg)

### Breadboard and Raspberry Pi schematic
This wiring diagram could be helpful to make the connections on breadboard
![fritz_bb](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/new_breadboard.jpg)

### i2c Detection (0x27)
Type the following command in terminal

````
i2cdetect -y 1
````

![whatsapp image 2018-10-23 at 1 44 14 pm](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/output.jpg)
