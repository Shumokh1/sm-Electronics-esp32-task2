# sm-Electronics-esp32-task2

# Servo Sweep Example for ESP32

## Description

Task2: Create a circuit using esp32. 
This project demonstrates a servo motor sweep using an ESP32 microcontroller. The servo motor sweeps back and forth between 0 and 180 degrees.

## Demo

## Components Used

- ESP32 microcontroller
- Servo motor
- Required wiring as per the example

## Setup

### Circuit Setup

1. Connect the servo motor to the ESP32 as per the example code.
2. Ensure the servo motor is powered and connected to the correct GPIO pin (e.g., pin 22).

### Example Code

```cpp
#include <ESP32Servo.h>

const int servoPin = 22;

Servo servo;

void setup() {
  servo.attach(servoPin, 500, 2400);
}

int pos = 0;

void loop() {
  for (pos = 0; pos <= 180; pos += 1) {
    servo.write(pos);
    delay(15);
  }
  for (pos = 180; pos >= 0; pos -= 1) {
    servo.write(pos);
    delay(15);
  }
}
