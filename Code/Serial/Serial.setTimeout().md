# Serial.setTimeout()
`Serial.setTimeout()` sets the maximum milliseconds to wait for serial data. It defaults to 1000 milliseconds.

## Syntax
```c++
Serial.setTimeout(time);
```
`time` : timeout duration in milliseconds. Allowed data types: `long`.

## Example:
```c++
void setup() {
  Serial.begin(9600);     // opens serial port, sets data rate to 9600 bps
  Serial.setTimeout(100); // set new value to 100 milliseconds
  Serial.print("Timeout: ");
  Serial.println(Serial.getTimeout()); // print the new value
}

void loop() {
  // check if data is available
  if (Serial.available() > 0) {
    // read the incoming string:
    String incomingString = Serial.readString();

    // prints the received data
    Serial.print("I received: ");
    Serial.println(incomingString);
  }
}
```