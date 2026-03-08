# radar-detection-system
A basic radar detection system that utilises Arduino UNO, ultrasonic sensor, servo motor, LED's and an active buzzer.
# Arduino Radar System

## Overview

This project implements a **simple radar-style object detection system** using an Arduino Uno, an ultrasonic sensor, and a servo motor to scan the environment.

The system continuously rotates the ultrasonic sensor across a defined angular range and measures the distance to nearby objects. When an object is detected within a predefined threshold distance, the system provides both **visual and auditory feedback** using LEDs and a buzzer.

This project demonstrates the integration of **sensor data acquisition, actuator control, and real-time feedback systems** in an embedded robotics platform.

---

## System Features

- Environment scanning using a rotating ultrasonic sensor
- Distance measurement using time-of-flight principles
- Servo-based angular sweep for directional sensing
- Real-time object detection alerts
- Visual indication using LEDs
- Audible alert using a buzzer
- Modular embedded code structure

---

## Hardware Components

- Arduino Uno
- Ultrasonic Distance Sensor (HC-SR04 or equivalent)
- Servo Motor (SG90 or similar)
- Active buzzer
- Red LED (object detected warning)
- Green LED (no object detected)
- Current limiting resistors for LEDs
- Breadboard
- Jumper wires
- External power source (optional for servo stability)

---

## System Architecture

The system consists of three main subsystems:

### 1. Sensing
An ultrasonic sensor measures the distance to nearby objects by emitting a sound pulse and measuring the return time of the reflected signal.

### 2. Scanning Mechanism
A servo motor rotates the ultrasonic sensor across a predefined angular range (e.g., 0°–180°). This allows the system to detect objects across a wider field of view.

### 3. Feedback System
When the measured distance falls below a specified threshold:

- A **red LED** turns on
- A **buzzer** sounds an alert

If no object is detected within the threshold distance:

- A **green LED** remains on

---

## Hardware Connections

### Ultrasonic Sensor
- VCC → Arduino 5V
- GND → Arduino GND
- Trig → Arduino digital pin
- Echo → Arduino digital pin

### Servo Motor
- VCC → Arduino 5V (or external supply)
- GND → Arduino GND
- Signal → PWM pin on Arduino

### LEDs
Green LED:
- Anode → Digital pin via resistor
- Cathode → GND

Red LED:
- Anode → Digital pin via resistor
- Cathode → GND

### Buzzer
- Positive → Digital pin
- Negative → GND

---

## System Operation

1. The servo motor begins sweeping the ultrasonic sensor across a specified angular range.
2. At each angle position:
   - The ultrasonic sensor emits a pulse.
   - The echo return time is measured.
   - The distance to the nearest object is calculated.
3. If the detected distance is **below a predefined threshold**:
   - The red LED turns on
   - The buzzer is activated
4. If the detected distance is **above the threshold**:
   - The green LED remains active
   - The buzzer stays off
5. The scanning process repeats continuously.

---

## Detection Logic

Example detection condition:
