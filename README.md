# ESP32 Three LED Sequential Control

A basic Embedded Systems project using ESP32 DevKit V1 to control three LEDs sequentially.

## Project Demonstration

[▶️ Watch the ESP32 Three LED Sequential Control Demonstration on YouTube](https://youtu.be/s-49XrLsxmM)

## Project Overview

This project demonstrates sequential LED control using an ESP32 DevKit V1.

Three LEDs are connected to GPIO 4, GPIO 5, and GPIO 18. Only one LED is ON at a time, while the other two LEDs remain OFF.

The LEDs turn ON one after another in sequence and the process repeats continuously.

## Components Used

- ESP32 DevKit V1
- 3 × LEDs
- 3 × 220Ω Resistors
- Breadboard
- Jumper Wires
- USB Cable

## Software Used

- Arduino IDE

## GPIO Configuration

| Component | ESP32 GPIO |
|---|---|
| LED 1 | GPIO 4 |
| LED 2 | GPIO 5 |
| LED 3 | GPIO 18 |

## Circuit Connection

```text
LED 1:
GPIO 4 ─── 220Ω ─── LED 1 (+)
LED 1 (-) ───────── Common GND

LED 2:
GPIO 5 ─── 220Ω ─── LED 2 (+)
LED 2 (-) ───────── Common GND

LED 3:
GPIO 18 ─── 220Ω ─── LED 3 (+)
LED 3 (-) ────────── Common GND

Arduino code

#define LED1 4
#define LED2 5
#define LED3 18

void setup() {
  pinMode(LED1, OUTPUT);
  pinMode(LED2, OUTPUT);
  pinMode(LED3, OUTPUT);
}

void loop() {
  digitalWrite(LED1, HIGH);
  digitalWrite(LED2, LOW);
  digitalWrite(LED3, LOW);
  delay(500);

  digitalWrite(LED1, LOW);
  digitalWrite(LED2, HIGH);
  digitalWrite(LED3, LOW);
  delay(500);

  digitalWrite(LED1, LOW);
  digitalWrite(LED2, LOW);
  digitalWrite(LED3, HIGH);
  delay(500);
}
