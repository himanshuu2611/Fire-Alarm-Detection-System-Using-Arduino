# Fire Alarm Detection System (Arduino)

A basic **Fire Alarm Detection System** using **Arduino C++**.  
This project uses a **flame sensor** or **temperature sensor** to detect fire and triggers a **buzzer/alarm** when fire or high temperature is detected. It’s a simple IoT prototype built for learning and safety simulation purposes.

---

## Features

- Real-time fire detection using flame or temperature sensor  
- Buzzer alarm when fire is detected  
- LED indicator (optional) for visual alert  
- Compact and efficient code  
- Suitable for safety demonstration or small prototypes

---

## Tech Stack

- **Language:** C++ (Arduino)
- **Hardware:** Arduino Uno/Nano, Flame Sensor / DHT11 / LM35, Buzzer, LEDs, Resistors, Breadboard, Jumper wires
- **IDE:** Arduino IDE

---

## Circuit Components

| Component       | Quantity |
|----------------|----------|
| Arduino Uno     | 1        |
| Flame Sensor / DHT11 / LM35 | 1        |
| Buzzer          | 1        |
| LED (optional)  | 1        |
| Resistors       | 1–2      |
| Jumper Wires    | As needed |
| Breadboard      | 1        |

---

## How It Works

1. Flame sensor outputs HIGH or LOW based on detection
2. Arduino reads the sensor input
3. If fire is detected, the buzzer sounds and LED turns on
4. Otherwise, the system stays idle

---

## Code Overview

```cpp
int sensorPin = A0;     // Flame or temperature sensor pin
int buzzerPin = 8;      // Buzzer connected to pin 8
int ledPin = 7;         // Optional LED

void setup() {
  pinMode(sensorPin, INPUT);
  pinMode(buzzerPin, OUTPUT);
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int sensorValue = analogRead(sensorPin);

  if (sensorValue < threshold) { // e.g., threshold = 100
    digitalWrite(buzzerPin, HIGH);
    digitalWrite(ledPin, HIGH);
    Serial.println("Fire Detected!");
  } else {
    digitalWrite(buzzerPin, LOW);
    digitalWrite(ledPin, LOW);
  }

  delay(200);
}
