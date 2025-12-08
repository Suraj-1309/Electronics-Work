# Serial.write()

Writes binary data to the serial port. This data is sent as a byte or series of bytes; to the characters representing the digits of a number use the `print()` function instead.

## Syntax
```c++
Serial.write(val)

Serial.write(str)

Serial.write(buf, len)
```

## Parameter Values

- **Serial**: Serial port object.  
  See the list of available serial ports for each board on the Serial main page.

- **val**:  
  A value to send as a single byte.

- **str**:  
  A string to send as a series of bytes.

- **buf**:  
  An array to send as a series of bytes.

- **len**:  
  The number of bytes to be sent from the array.

---

## Return Values

- **write()** returns the number of bytes written.  
  Reading that number is optional.  
  Data type: **size_t**

## Example:
```c++
void setup() {
  Serial.begin(9600);

  Serial.write(45);     // write a byte with the value 45 => '-' character
  Serial.write('\n');   // write a newline character
  Serial.write("ArduinoGetStarted.com\n"); // write a string terminated by a newline character

  byte buf[] = {'A', 'r', 'd', 'u', 'i', 'n', 'o'};
  Serial.write(buf, 7); // write an array
}

void loop() {
}

```