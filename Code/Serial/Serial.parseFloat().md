# Serial.parseFloat()

`Serial.parseFloat()` returns the first valid floating point number from the Serial buffer.  

`parseFloat()` is terminated by the first character that is not a floating point number. The function terminates if it times out.

## Syntax
```c++
Serial.parseFloat();
Serial.parseFloat(lookahead);
Serial.parseFloat(lookahead, ignore);
```

