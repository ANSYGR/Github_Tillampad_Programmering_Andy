Clock and Temp Project
This repository contains the code for a project that utilizes a DS3231 module to display the current time on a 1306 OLED display. Additionally, it measures the ambient temperature using an analog temperature sensor module and displays the temperature as a mapped value on a 9g servo motor. When the temperature falls below a defined threshold, a relay activates for additional control actions.

Features
Clock Display: Reads time from the DS3231 module and displays it on the OLED screen.
Temperature Monitoring: Reads temperature from an analog sensor and maps it to the servo motor angle.
Threshold Control: Activates a relay when the temperature drops below a certain level.
Hardware Requirements
DS3231 Real-Time Clock (RTC) Module
1306 OLED Display (128x64)
Analog Temperature Sensor Module
9g Servo Motor
Relay Module
Software Requirements
Arduino IDE (version 1.8.10 or higher recommended)
Arduino Libraries:
Wire.h for I2C communication
RTClib.h for DS3231 RTC module handling
U8glib.h for OLED display functionality
Servo.h for servo motor control
Wiring Connections
Component	Arduino Pin
Analog Temperature Pin	A0
Servo Motor Pin	9
Relay Pin	8
OLED Display	I2C Pins (A4 and A5 on Arduino UNO)
DS3231 RTC Module	I2C Pins (A4 and A5 on Arduino UNO)
Code Overview
The code includes several key functions:

getTime(): Reads the current time from the DS3231 module and formats it as hh:mm:ss.
getTemp(): Reads the analog temperature sensor value and calculates temperature in Celsius using the Steinhart-Hart equation.
oledWrite(): Writes a string to the OLED display.
servoWrite(): Maps the temperature to an angle and sets it on the servo motor.
relay(): Activates the relay if the temperature is below the threshold (27°C by default).
Example Usage
Setup:
Initialize communication with the DS3231 RTC and the OLED display.
Attach the servo motor to the designated pin and set the relay pin to OUTPUT mode.
Main Loop:
Continuously read the temperature and display it on the serial monitor.
Display the current time on the OLED display.
Adjust the servo motor based on the temperature.
Activate the relay if the temperature is below the defined threshold.
Installation
Clone the repository:
bash
Kopiera kod
git clone https://github.com/yourusername/clock-temp-project.git
Open the Project in Arduino IDE:
Ensure you have the required libraries installed. You can install them via the Arduino Library Manager.
Upload the Code:
Connect your Arduino board, select the appropriate board and port, and upload the code.
License
This project is licensed under the MIT License - see the LICENSE file for details.
