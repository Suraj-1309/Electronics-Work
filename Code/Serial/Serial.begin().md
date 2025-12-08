# Serial.begin()

`Serial.begin()` is used to initialize serial communication between the Arduino board and a computer or other serial devices.  

It sets the **baud rate** (data transfer speed) for communication over USB or UART.

## Syntax
```c++
Serial.begin(speed);

Serial.being(speed, config);
```

## Common Baud Rates

| Baud Rate | Use Case |
|----------:|----------|
| 9600      | Most common and default communication speed |
| 57600     | Faster communication |
| 115200    | Very fast, used for advanced/high-speed data transfer |

## Example Code
```c++
void setup(){
    Serial.begin(9600); // start serial communication at 9600 bits per second
}

void loop(){
    Serial.println("Hello");
    delay(1000);
}
```

## What Serial.begin() Does

- Opens the serial port
- Initializes communication hardware
- Prepares Arduino to **send and receive** serial data
- Must be called **before** using:
  - `Serial.print()`
  - `Serial.println()`
  - `Serial.write()`

---

## Important Notes

- Place inside the `setup()` function
- Both communicating devices **must use the same baud rate**
- For boards with native USB (Leonardo, Micro), add:

```cpp
while (!Serial); // Wait for Serial Monitor to open
```

### 🔹 When to Use Serial.begin()

- Debugging programs via Serial Monitor
- Communication with modules like:
  - Bluetooth
  - GPS
  - ESP8266 / WiFi modules
- Logging data to PC
