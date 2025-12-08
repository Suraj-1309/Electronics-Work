# Serial.availableForWrite()

Get the number of bytes (characters) available for writing in the serial buffer without blocking the write operation.

## Syntax:
```c++
Serial.availableForWrite();
```
**Return Value**  
The number of bytes available to write.

## Example:
```c++
String myString = "Welcome to ArduinoGetStarted.com!\n";

void setup() {
  Serial.begin(9600); // opens serial port, sets data rate to 9600 bps
  int wlen = Serial.availableForWrite();
  // prints the received data
  Serial.print("TX buffer size: ");
  Serial.println(wlen);
}

void loop() {
  // check if Tx buffer is enough to write the string
  if (Serial.availableForWrite() > myString.length()) {
    // prints the string
    Serial.print(myString);
    delay(1000);
  }
}
```