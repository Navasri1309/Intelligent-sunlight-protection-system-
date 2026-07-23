## Intelligent Sunlight Protection System
## Project Description:

The Intelligent Sunlight Protection System is an Arduino-based automation project that protects sunlight-sensitive objects from excessive sunlight. An LDR sensor continuously detects the light intensity, and the Arduino UNO processes the sensor output. When bright light is detected, the servo motor automatically rotates to close a protective cardboard shield. When the light intensity decreases, the shield returns to its original position. This project demonstrates a simple, low-cost, and beginner-friendly automation system.

## Procedure
-Assemble the prototype by fixing the Arduino UNO, LDR sensor, and servo motor on the base.
-Connect the LDR sensor and servo motor to the Arduino according to the circuit connections.
-Open the Arduino IDE and upload the program to the Arduino UNO.
-Power the Arduino using a USB cable.
-Place the LDR sensor where it can detect sunlight.
-When bright light falls on the LDR, the servo rotates to 90°, closing the shield.
-When the light returns to normal, the servo rotates back to 0°, opening the shield.
-Verify the operation by using a flashlight or exposing the sensor to bright light.

## Arduino Program
```
#include <Servo.h>

Servo shieldServo;

const int ldrPin = 2;

void setup()
{
  pinMode(ldrPin, INPUT);
  shieldServo.attach(9);
  shieldServo.write(0);
  Serial.begin(9600);
}

void loop()
{
  int lightState = digitalRead(ldrPin);

  Serial.print("Light State: ");
  Serial.println(lightState);

  if (lightState == 0)
  {
    shieldServo.write(90);
    Serial.println("Shield Closed");
  }
  else
  {
    shieldServo.write(0);
    Serial.println("Shield Open");
  }

  delay(500);
}
```
## Output:
Normal Light
Light State = 1
Servo Position = 0°
Shield Open

Bright Light
Light State = 0
Servo Position = 90°
Shield Closed

## Created By

Navasri B
B.Tech – Artificial Intelligence and Data Science
