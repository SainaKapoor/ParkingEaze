# ParkingEaze
# PCF8574 LCD with HC-SR04 ultrasonic distance sensor. 
 
<img src="https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/case1.jpg" width="500" height="500">

### Purpose
The main goal of my project is to measure the distance of the car and display it on the lcd screen. The LCD screen will display the available parkig spots and will give indication and direction to the customers.
## Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction-to-the-sensor-and-effector)
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
13. [References](#references)

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




## System Diagram 
 This diagram shows the sensor and effector communication with each other using raspberry pi. 

![systemdiagram](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/diagram.png)

## Materials required to build this project
--Folloing materials are listed with the link to the website where you can acquire from:
- Raspberry Pi [Raspberrypi-Amazon](https://www.amazon.ca/CanaKit-Raspberry-Starter-Premium-Black/dp/B07BD56DW5/ref=sr_1_6?crid=3EARREJYHEXFP&keywords=raspberry+pi+3&qid=1576002058&sprefix=raspber%2Caps%2C249&sr=8-6)
- HC-SR04 distance sensor [Sensor-Amazon](https://www.amazon.ca/HC-SR04-Ultrasonic-Distance-Arduino-MEGA2560/dp/B01COSN7O6/ref=sr_1_3?crid=3FEU10TPSGD93&keywords=hc-sr04&qid=1576002253&sprefix=HC-Sr%2Caps%2C260&sr=8-3)
- PCF8574 LCD module [LCD-Amazon](https://www.amazon.ca/Module-Yellow-Green-PCF8574-Arduino-mega2560/dp/B07Z45V1N7/ref=sr_1_3?keywords=pcf8574+lcd+module&qid=1576002295&sr=8-3)
- 1k resistor and 2.2k resitor used as a voltage divider.
- Breadboard and jumper wires to test the connection.
- Socket Header to attach sensor and effector to the pcb and pcb to the raspberry pi.
- Acrylic case to enclose the whole circuit. [Thingiverse website](https://www.thingiverse.com/search?q=raspberry+pi+3b%2B+laser&dwh=735defe387e7a28)

## Budget
![capture](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/budget.png)

## Time Commitment
- This project can be done in 1-2 weeks. It will take about 4-5 days to recieve the parts. The breadboarding and testing the connection might take 1-2 hour. Soldering headers, resitors just take 15 minutes. After this, importing the necessary libraries for the lcd and running the python code can take 1 more extra hour which includes troubleshooting step.
- You can also refer to my schedule provided [here](https://github.com/SainaKapoor/ParkingEaze/blob/master/documentation/Schedule.mpp)

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


If the connections are correct then you should be able to see the readings on the LCD.
![whatsapp image 2018-10-23 at 1 44 14 pm 1](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/display.jpg)

### Breadboard and Raspberry Pi schematic
This wiring diagram could be helpful to make the connections on breadboard
![fritz_bb](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/new_breadboard.jpg)

### I2c Detection (0x27)
Type the following command on terminal

````
i2cdetect -y 1
````

![whatsapp image 2018-10-23 at 1 44 14 pm](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/output.jpg)

## Mechanical Assembly
I made the connections on the breadboard to check if all the elements are working using jumper wires and the python script described in the further steps.
After testing, PCB design is made so that the sensor and effector can be directly connected to the pcb without the use of any wires.

| HC-SR04 | Raspberry Pi |
| --- | --- |
| VCC | 5V |
| GND | GND |
| TRIG | PIN16 |
| ECHO |  1K |  

| PCF8574 LCD | Raspberry Pi |
| --- | --- |
| VCC | 5V |
| GND | GND |
| SDA | SDA |
| SCL | SCL |



## PCB
Here is my PCB Design and I got the PCB by exporting it to the gerber files and printed in the humber's prototype lab.
You can get the fritzing file of my pcb my clicking on this link. [PCB file](https://github.com/SainaKapoor/ParkingEaze/blob/master/Electronics/PCBfile.fzz)

### Soldering
- Follow these [instruction](https://www.instructables.com/id/How-to-solder/) on how to solder the pcb. 
I soldered my pcb with necessary headers and resistors.
- Make sure the connections on PCB are not short. vias and other point should have enough solder on it for accurate connection.
![99a0e5b6-66c7-4494-9c4c-d72fc71df572](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/new_pcb2.jpg)
![99a0e5b6-66c7-4494-9c4c-d72fc71df572](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/new_pcb1.jpg)

- To avoid short, make sure your pcb is soldered properly, I connected the VCC and ground with the multimeter. It shows Overload which means connection is open. Try connecting it with sensor and effector on it, it will show some value which depicts that connections are accurate.
![99a0e5b6-66c7-4494-9c4c-d72fc71df572](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/test.jpg)

### Power Up
After all the components are connected, your setup should look like this and should show the readings of the distance on the LCD when any object moves infront of the sensor.
![whatsapp image 2018-11-13 at 10 50 46 pm](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/measure_distance1.jpg) 

## Unit Testing
To run the LCD we need some lcd driver libraries which is available at [Libraries](https://www.recantha.co.uk/blog/?p=4849)
- Note that the i2c address in the library should match with your lcd i2c address otherwise it will give some errors.


### Python Script
I used the this code to run both my sensor and lcd.
```
import lcddriver
import RPi.GPIO as GPIO
import time
GPIO.setmode(GPIO.BCM)

display = lcddriver.lcd()

TRIG = 23 
ECHO = 24

print ("Distance Measurement In Progress")
display.lcd_display_string("Distance :", 1)
GPIO.setup(TRIG,GPIO.OUT)
GPIO.setup(ECHO,GPIO.IN)
try:
    while True:

        GPIO.output(TRIG, False)
        print ("Waiting For Sensor To Settle")
        
        time.sleep(2)

        GPIO.output(TRIG, True)
        time.sleep(0.00001)
        GPIO.output(TRIG, False)

        while GPIO.input(ECHO)==0:
          pulse_start = time.time()

        while GPIO.input(ECHO)==1:
          pulse_end = time.time()

        pulse_duration = pulse_end - pulse_start

        distance = pulse_duration * 17150

        distance = round(distance, 2)

        result = str(distance)+" cm"
        display.lcd_display_string(result,2);

except KeyboardInterrupt: # If there is a KeyboardInterrupt (when you press ctrl+c), exit the program and cleanup
    print("Cleaning up!")
    GPIO.cleanup()
```

### Final Testing
I got this output on the terminal window of the Raspberry Pi after running the python script and the distance will be displayed on the lcd screen.
![reading](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/result.jpg)

### Enclosure
I made an acrylic case to enclode my raspberry pi, pcb, sensor and lcd 
You can use Corel Draw to make a case. Click here to get the files for this case. [Design](https://github.com/SainaKapoor/ParkingEaze/blob/master/Mechanical/Enclosure.cdr)

If you are successful in making your case, it should look like this.
![design](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/case1.jpg)

![usbports](https://raw.githubusercontent.com/SainaKapoor/ParkingEaze/master/Images/case2.jpg)

## Production Testing
It is important that the sensor and effector should work properly to give accurate results for that frequent troubleshooting is required. The key point is i2c address should be correct and the wires are connected properly for initial testing. Rest, this project contributes in making the parking scenarios easy for humans.

## References
For detailed information and demo, I refered to [Youtube video](https://www.youtube.com/watch?v=i-7Hv90Rz58)



