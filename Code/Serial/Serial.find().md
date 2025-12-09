# Serial.find()

`Serial.find()` reads data from the serial buffer until the target is found.
- The function returns `true` if target is found
- `false` if it times out.

`Serial.find()` inherits from the `stream` utility class.

## Syntax
```c++
Serial.find(target);
Serial.find(target, length);
```