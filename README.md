# EXP-4-Home Automation System with IOT

# Aim:
To make a Lamp at home (230 V AC) On / Off using ESP8266, IFTT Google Assistance and Blynk IoT mobile application. 
# Hardware / Software Tools required :
* PC with Internet connection
* Micro USB cable
* Wifi connection for ESP8266 (Use any mobile hotspot or Router)
* ESP8266 Board
* Mobile Phone with Blynk App installed
* IFTT for Google Voice Assistance
* 9 W Bulb and Relay control
* Arduino software 
* Jumper Wires

# Circuit Diagram:
<img width="1295" height="727" alt="image" src="https://github.com/user-attachments/assets/a3e68af3-4caa-413d-9ffe-fb49a49c84b0" />



# Theory: 


Blynk is an IoT platform for iOS or Android smartphones that is used to control Arduino, Raspberry Pi and NodeMCU via the Internet. This application is used to create a graphical interface or human machine interface (HMI) by compiling and providing the appropriate address on the available widgets.In this experiment we use ESP8266 to control a 220-volt lamp from a web server. But you can also use the same procedure to control fans, lights, AC, or other electrical devices that you want to control remotely.
Relay is an electromechanical device that is used as a switch between high current and low current devices. When the coil in the relay gets fully energized, the contact shifts from the normally open position to the normally closed position. Light bulbs usually operate on 120V or 220V AC power supply. We cannot interface these AC loads directly with the ESP8266 development board, or it will damage the board. We have to use a relay between the ESP8266 and the lamp. 
Google Assistant and IFTTT work together to let you control services with voice commands. When you say a set phrase, Google Assistant processes it and sends it to IFTTT as a trigger. If the phrase matches an applet you've created, IFTTT performs the linked action—like turning on a light or sending a message. Everything runs in the cloud, making it easy to automate tasks with just your voice, as long as the command is correctly matched and all services are online.
When we apply an active high signal to the signal pin of the relay module from any microcontroller like ESP8266, the relay contact moves from the normally open to the normally closed position. It makes the circuit complete, and the output load turns on.


# Program:
~~~
#include <Servo.h>
#include <LiquidCrystal.h>

LiquidCrystal lcd(A1,10,9,6,5,3);
float value;
int tmp = A0;
const int pingPin = 7;
int servoPin = 8;

Servo servo1;

void setup() {
  Serial.begin(9600);
