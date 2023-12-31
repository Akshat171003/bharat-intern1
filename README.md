# bharat-intern1
 In this , we will be creating code for smart parking system, air pollution monitoring system , health monitoring system.
BHARAT-Intern_Projects
1. Smart Parking System using Arduino Uno :-
There are two parking slots in our project. If you want to increase the number of paring slots then add a few more IR sensors and modify the code accordingly.
The system automatically detects whether the parking slot is empty or not. If the slot is empty in the automated car parking the new vehicles are allowed to enter else the entrance is blocked by the servo barrier in case the parking is full.
The visitors can see the status for the availability of the free space outside the parking on a 16×2 LCD. They can also see on the LCD how many parking slots are free. The data keeps updating as the vehicles move in and out of the parking.

Components Required
Arduino UNO
Two IR sensors
Servo motor
16×2 LCD
USB cable for uploading the code  

automatic car parking Circuit Diagram is below  
automatic car parkingBefore starting please check the address of the I2C module that you are using and modify the code accordingly.

Then connect the 5 volts pin of the Arduino with the VCC pin of the I2C module, the red wire of the servo motor, and the VCC pin of both the IR sensors.
Join the SDA pin of the I2C module with the analog-4 pin of the Arduino and the SCL pin of the I2C module with the analog-5 pin of the Arduino in this automatic car parking system project.Connect the GND pin of the Arduino with the GND pin of the I2C module, the brown wire of the servo motor, and the GND pin of both the IR sensors. Attach the orange(signal) wire of the servo motor to the digital-9 pin of the Arduino.

Now connect the pins of the I2C module with the pins of 16×2 LCD.
You can check here the interfacing of 16×2 LCD with the I2C module. At last, connect the OUT pin of the first IR sensor with the digital-4 pin of the Arduino and the OUT pin of the second IR sensor with the digital-7 pin of the Arduino.


2. Air pollution monitoring system -
In this project we are going to make an IoT Based Air Pollution Monitoring System in which we will monitor the Air Quality over a webserver using internet and will trigger a alarm when the air quality goes down beyond a certain level, means when there are sufficient amount of harmful gases are present in the air like CO2, smoke, alcohol, benzene and NH3. It will show the air quality in PPM on the LCD and as well as on webpage so that we can monitor it very easily.

Previously we have built the LPG detector using MQ6 sensor, Smoke detector using MQ2 sensor, and Air Quality Analyser but this time we have used MQ135 sensor as the air quality sensor which is the best choice for monitoring Air Quality as it can detects most harmful gases and can measure their amount accurately. In this IOT project, you can monitor the pollution level from anywhere using your computer or mobile. We can install this system anywhere and can also trigger some device when pollution goes beyond some level, like we can switch on the Exhaust fan or can send alert SMS/mail to the user.

Required Components:
MQ135 Gas sensor
Arduino Uno
Wi-Fi module ESP8266
16X2 LCD
Breadboard
10K potentiometer
1K ohm resistors
220 ohm resistor
Buzzer
 
Circuit Diagram and Explanation:
Circuit Diagram 
First of all we will connect the ESP8266 with the Arduino. ESP8266 runs on 3.3V and if you will give it 5V from the Arduino then it won’t work properly and it may get damage. Connect the VCC and the CH_PD to the 3.3V pin of Arduino. The RX pin of ESP8266 works on 3.3V and it will not communicate with the Arduino when we will connect it directly to the Arduino. So, we will have to make a voltage divider for it which will convert the 5V into 3.3V. This can be done by connecting three resistors in series like we did in the circuit. Connect the TX pin of the ESP8266 to the pin 10 of the Arduino and the RX pin of the esp8266 to the pin 9 of Arduino through the resistors.
ESP8266 Wi-Fi module gives your projects access to Wi-Fi or internet. It is a very cheap device and make your projects very powerful. It can communicate with any microcontroller and it is the most leading devices in the IOT platform. Learn more about using ESP8266 with Arduino here.Then we will connect the MQ135 sensor with the Arduino. Connect the VCC and the ground pin of the sensor to the 5V and ground of the Arduino and the Analog pin of sensor to the A0 of the Arduino.

Connect a buzzer to the pin 8 of the Arduino which will start to beep when the condition becomes true.
In last, we will connect LCD with the Arduino. The connections of the LCD are as follows

Connect pin 1 (VEE) to the ground.
Connect pin 2 (VDD or VCC) to the 5V.
Connect pin 3 (V0) to the middle pin of the 10K potentiometer and connect the other two ends of the potentiometer to the VCC and the GND. The potentiometer is used to control the screen contrast of the LCD. Potentiometer of values other than 10K will work too.
Connect pin 4 (RS) to the pin 12 of the Arduino.
Connect pin 5 (Read/Write) to the ground of Arduino. This pin is not often used so we will connect it to the ground.
Connect pin 6 (E) to the pin 11 of the Arduino. The RS and E pin are the control pins which are used to send data and characters.
The following four pins are data pins which are used to communicate with the Arduino.
Connect pin 11 (D4) to pin 5 of Arduino.
Connect pin 12 (D5) to pin 4 of Arduino.
Connect pin 13 (D6) to pin 3 of Arduino.
Connect pin 14 (D7) to pin 2 of Arduino.
Connect pin 15 to the VCC through the 220 ohm resistor. The resistor will be used to set the back light brightness. Larger values will make the back light much more darker.
Connect pin 16 to the Ground.
Iot-air-quality-monitoring-system-using-arduino-circuit

Working Explanation:
The MQ135 sensor can sense NH3, NOx, alcohol, Benzene, smoke, CO2 and some other gases, so it is perfect gas sensor for our Air Quality Monitoring Project. When we will connect it to Arduino then it will sense the gases, and we will get the Pollution level in PPM (parts per million). MQ135 gas sensor gives the output in form of voltage levels and we need to convert it into PPM. So for converting the output in PPM, here we have used a library for MQ135 sensor, it is explained in detail in “Code Explanation” section below.

Sensor was giving us value of 90 when there was no gas near it and the safe level of air quality is 350 PPM and it should not exceed 1000 PPM. When it exceeds the limit of 1000 PPM, then it starts cause Headaches, sleepiness and stagnant, stale, stuffy air and if exceeds beyond 2000 PPM then it can cause increased heart rate and many other diseases.When the value will be less than 1000 PPM, then the LCD and webpage will display “Fresh Air”.  Whenever the value will increase 1000 PPM, then the buzzer will start beeping and the LCD and webpage will display “Poor Air, Open Windows”. If it will increase 2000 then the buzzer will keep beeping and the LCD and webpage will display “Danger! Move to fresh Air”.

3.Health monitoring system- 
IoT based patient health monitoring system is a generic term given to any medical equipment that has internet capability and can measure one or more health data of a patient who is connected to the device such as heartbeat, body temperature, blood pressure, ECG, steps etc. The equipment can record, transmit and alert if there is any abrupt change in the patient’s health.

By this definition, it includes devices such as smart-watches, fitness trackers, smart-phones to expensive hospital equipment which can connect to internet.

IoT based health monitoring system is used where the patient and heath expert(s) are at different locations. For example, a patient can stay at home and continue his/her routine life and a doctor can monitor patient’s heath. Based on the received data the heath expert can prescribe a best treatment or take an immediate action in case of an emergency.
Circuit Diagram - 
An IoT based health monitoring system using ThingSpeak is a project that involves integrating various sensors and devices to gather and analyze health data of an individual. ThingSpeak is an open-source IoT platform that provides an easy-to-use interface to collect, analyze, and visualize data from IoT devices.

The system can be designed to monitor various health parameters such as heart rate, blood pressure, body temperature, oxygen level, and many others. The data collected from the sensors can be transmitted to a ThingSpeak channel using a Wi-Fi module such as ESP8266 or ESP32. The data can be then analyzed using MATLAB or other programming languages supported by ThingSpeak.
The system can be designed to send alerts or notifications to the individual or caregiver in case of abnormal readings or health issues. For instance, if the blood pressure reading goes beyond a certain threshold level, the system can send a notification to the individual and also to the healthcare provider for immediate attention.

Moreover, the system can also be integrated with wearable devices such as smartwatches or fitness trackers to monitor the physical activity of an individual. This can help in analyzing the overall health of an individual and provide personalized recommendations for improvement.
The ThingSpeak platform also provides visualization tools to create charts, graphs, and other visual representations of the health data. This can help in tracking the progress of an individual and providing insights into their health patterns.
Overall, an IoT based health monitoring system using ThingSpeak can provide a comprehensive approach to monitor and manage an individual's health. It can enable early detection of health issues and provide timely intervention, thus improving the overall quality of life.
