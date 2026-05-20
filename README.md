**#Task 4**
# Speech Recognition Based Home Automation System

This project is developed using Arduino UNO, HC-05 Bluetooth Module, and Relay Module to control home appliances wirelessly using voice commands through a mobile application.

## Components Used
- Arduino UNO
- HC-05 Bluetooth Module
- 2-Channel Relay Module
- Jumper Wires
- Android Mobile App

## Features
- Wireless appliance control
- Bluetooth communication
- Voice command support
- Real-time relay switching

## Commands
- A → Relay 1 ON
- a → Relay 1 OFF
- B → Relay 2 ON
- b → Relay 2 OFF

## Technologies Used
- Arduino IDE
- Embedded Systems
- Bluetooth Communication
- IoT Basics

## Project Outcome
Successfully implemented a speech recognition based home automation system for controlling devices wirelessly.

**#Task 3**
# Arduino Push Button Counter

This project counts the number of push button presses using Arduino UNO and displays the count in the Serial Monitor.

## Components Used
- Arduino UNO
- Push Button
- Breadboard
- Jumper Wires

## Features
- Counts button presses
- Displays output in Serial Monitor
- Uses digital input concepts

## Concepts Learned
- Digital Input Handling
- Push Button Interfacing
- Arduino Programming Basics
- Embedded Systems Fundamentals

## Circuit Connection
- Push Button connected to Digital Pin 2
- GND connection used with pull-down/pull-up logic

## Arduino Code

c++
int button = 2;
int count = 0;
int lastState = HIGH;

void setup() {
  pinMode(button, INPUT_PULLUP);
  Serial.begin(9600);
}

void loop() {
  int state = digitalRead(button);

  if(state == LOW && lastState == HIGH) {
    count++;
    Serial.print("Button Count: ");
    Serial.println(count);
    delay(200);
  }

  lastState = state;
}

**#Task 2**
# Home Automation System using Arduino UNO

This project simulates a simple Home Automation System using Arduino UNO in Tinkercad. Multiple LEDs are controlled using push buttons, representing basic home appliance control.

## Components Used
- Arduino UNO
- LEDs
- Push Buttons
- Resistors
- Breadboard
- Jumper Wires

## Features
- Controls multiple LEDs
- Push button based switching
- Simulates home appliance automation
- Implemented in Tinkercad simulation

## Concepts Learned
- Arduino Programming
- Digital Input/Output Control
- Circuit Design and Simulation
- Basic Home Automation Concepts

## Circuit Connections

### LEDs
- LED 1 → Digital Pin 2
- LED 2 → Digital Pin 3
- LED 3 → Digital Pin 4

### Push Buttons
- Button 1 → Digital Pin 5
- Button 2 → Digital Pin 6
- Button 3 → Digital Pin 7

### Power Connections
- GND → Breadboard Ground Rail
- 5V → Breadboard Positive Rail

## Arduino Code
c++
int led1 = 2;
int led2 = 3;
int led3 = 4;

int btn1 = 5;
int btn2 = 6;
int btn3 = 7;

void setup() {
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);

  pinMode(btn1, INPUT_PULLUP);
  pinMode(btn2, INPUT_PULLUP);
  pinMode(btn3, INPUT_PULLUP);
}

void loop() {

  if(digitalRead(btn1) == LOW) {
    digitalWrite(led1, HIGH);
  } else {
    digitalWrite(led1, LOW);
  }

  if(digitalRead(btn2) == LOW) {
    digitalWrite(led2, HIGH);
  } else {
    digitalWrite(led2, LOW);
  }

  if(digitalRead(btn3) == LOW) {
    digitalWrite(led3, HIGH);
  } else {
    digitalWrite(led3, LOW);
  }
}

**#Task 1**
# Temperature Monitoring System using Arduino UNO

This project is a Temperature Monitoring System developed using Arduino UNO and TMP36 Temperature Sensor in Tinkercad. The system reads temperature values and displays them in the Serial Monitor.

## Components Used
- Arduino UNO
- TMP36 Temperature Sensor
- Breadboard
- Jumper Wires
- USB Connection / Tinkercad Simulation

## Features
- Reads real-time temperature
- Displays temperature in Serial Monitor
- Sensor interfacing using analog input
- Simple IoT and Embedded Systems project

## Concepts Learned
- Arduino Programming
- Sensor Interfacing
- Real-time Temperature Monitoring
- Serial Monitor Visualization

## Circuit Connections

| TMP36 Pin | Arduino Connection |
|---|---|
| Left Pin (+Vs) | 5V |
| Middle Pin (Vout) | A0 |
| Right Pin (GND) | GND |

## Arduino Code
c++
int sensorPin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {

  int sensorValue = analogRead(sensorPin);

  float voltage = sensorValue * (5.0 / 1023.0);

  float temperatureC = (voltage - 0.5) * 100;

  Serial.print("Temperature: ");
  Serial.print(temperatureC);
  Serial.println(" °C");

  delay(1000);
}
