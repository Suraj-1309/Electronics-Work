# Serial.available()

Get the number of bytes (characters) available for reading from the serial port. This is data that's already arrived and stored in the serial receive buffer (which holds 64 bytes).

`Serial.available()` inherits from the `Stream` utility class.

## Syntax
```c++
Serail.available()
```
**Return values** : The number of bytes available to read.

