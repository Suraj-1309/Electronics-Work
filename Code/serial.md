# Serial

`Serail` is used for communication between:
- An Arduino board and another Arduino board
- An Aduino board and other sensors/devices.
- An Arduino board and computer.
    - Any Serial softwares on computer
    - Serial Monitor of Arduino IDE

All Arduino boards have at least one serial port(also known as a UART or USART), and some have several.


| Board                 | USB CDC name                       | Serial pins       | Serial1 pins        | Serial2 pins         | Serial3 pins         |
|----------------------|-----------------------------------|------------------|--------------------|---------------------|---------------------|
| Uno, Nano, Mini      | —                                 | 0(RX), 1(TX)      | —                  | —                   | —                   |
| Mega                 | —                                 | 0(RX), 1(TX)      | 19(RX), 18(TX)     | 17(RX), 16(TX)      | 15(RX), 14(TX)      |
| Leonardo, Micro, Yún | Serial                            | 0(RX), 1(TX)      | —                  | —                   | —                   |
| Uno WiFi Rev.2       | —                                 | Connected to USB  | 0(RX), 1(TX)       | Connected to NINA   | —                   |
| MKR boards           | Serial                            | —                | 13(RX), 14(TX)     | —                   | —                   |
| Zero                 | SerialUSB (Native USB Port only)  | Connected to Programming Port | 0(RX), 1(TX) | —                   | —                   |
| Due                  | SerialUSB (Native USB Port only)  | 0(RX), 1(TX)      | 19(RX), 18(TX)     | 17(RX), 16(TX)      | 15(RX), 14(TX)      |
| 101                  | Serial                            | 0(RX), 1(TX)      | —                  | —                   | —                   |

<br>
<br>

In Arduino, `Serial` is actually a global object (an instance) of the `HardwareSerial` class (on boards like the Uno, Mega, etc.) or `USBSerial` (on boards with native USB).

This object is created for you by the Arduino core, so you don’t need to instantiate it yourself. That’s why you can directly call methods like Serial.begin(9600) or Serial.print("Hello").

**NOTE**  
On Uno, Nano, Mini, and Mega pins 0 and 1 are used for communication with the computer. Connecting anything to these pins can interfare with the communication, including causing failed uploads to the board.

We can also use the Arduino environment's built-in serial monitor to communicate with an Arduino board. Click the serial monitor button in the toolbar and select the same baud rate used in the call to `begin()`.

Serial communication on pins TX/RX uses TTL logic levels (5V or 3.3V depending on the board). Don't connect these pins directly to an RS232 serial port; they operate at +/- 12V and can damage your Arduino board.

To use these extra serial ports to communciate with your personal computer, you will need an additional USB-to-serial adaptor, as they are not connected to the Mega's USB-to-serial adaptor.  
To use them to communicate with an external TTL serial device, connect the TX pin to your device's RX pin, the RX to your device's TX pin, and the ground of your Mega to your device's ground.

## Functions
1. [Serial.available()](serial/Serial.available().md)
1. [Serial.availableForWrite()](serial/Serial.availableForWrite().md)
1. [Serial.begin()](serial/Serial.begin().md)
1. [Serial.end()](serial/Serial.end().md)
1. [Serial.print()](serial/Serial.print().md)
2. [Serial.println()](serial/Serial.println().md)
3. [Serial.write()](serial/Serial.write().md)
