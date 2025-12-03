# Blink Multiple LED

## Hardware Required

- **Arduino Board**
- **3 LED**
- **3 - 220 Ω resistor**
- **5 Jumper Wires**

## Circuit

### Circuit Diagram

![Arduino UNO Circuit To Blink Multiple LED](assets/circuit.png)

### Circuit Block Diagram

![Arduino UNO Block Diagram To Blink Multiple LED](assets/block_diagram.png)

### Circuit Explanation

- **Overview:** Three LEDs are connected to the Arduino digital pins `13`, `11`, and `9`. Each LED anode is connected to its respective pin through a `220 Ω` resistor; each LED cathode is connected to the common ground (GND) on the breadboard.
- **Wiring details:**
  - `Pin 13` -> `220 Ω` resistor -> LED 1 anode
  - `Pin 11` -> `220 Ω` resistor -> LED 2 anode
  - `Pin 9` -> `220 Ω` resistor -> LED 3 anode
  - All LED cathodes -> common `GND`
- **Resistor purpose:** The `220 Ω` resistors limit current to safe levels for the LEDs and the Arduino pins (typical LED current ≈ 10–20 mA).
- **Operation:** The sketch sets the three pins as outputs and in `loop()` turns each LED on for `DELAY` milliseconds while ensuring the others are off, producing a sequential blinking pattern.
- **Notes:** If you change LED colors or use a different supply voltage, recalculate resistor values. Always ensure the Arduino and breadboard share a common ground.

## Code

```C
#include <Arduino.h>

#define LED_PIN1 13
#define LED_PIN2 11
#define LED_PIN3 9

#define DELAY 200


void setup() {
  // put your setup code here, to run once:
  pinMode(LED_PIN1, OUTPUT);
  pinMode(LED_PIN2, OUTPUT);
  pinMode(LED_PIN3, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:

  // shows  only FIRST LED ON
  digitalWrite(LED_PIN1, HIGH);
  delay(DELAY);
  digitalWrite(LED_PIN2, LOW);
  digitalWrite(LED_PIN3, LOW);

  // shows  only SECOND LED ON
  digitalWrite(LED_PIN2, HIGH);
  delay(DELAY);
  digitalWrite(LED_PIN1, LOW);
  digitalWrite(LED_PIN3, LOW);

  // shows  only THIRD LED ON
  digitalWrite(LED_PIN3, HIGH);
  delay(DELAY);
  digitalWrite(LED_PIN1, LOW);
  digitalWrite(LED_PIN2, LOW);
}

```

## Resource

### Ciruit Design and Code

- https://www.tinkercad.com/things/5J04l6fIKMT-blink-multiple-led-using-arduino?sharecode=MhiNrxr39wJcM7Gj17fN3mfTjjMGFEmPboWvhVqUHlQ

### Project Video

- https://youtu.be/GtDnGCd8TuY

## Compoents Documentation

- LED
- Arduino UNO R3
- Resistor
- Breadboard
- [Jumper Wires](../Jumper_Wires/README.md)
