# Serial.findUntil()

`Serial.findUnitl()` reads data from the serial buffer until a targer string of given length or delimiter string is found.

- The function returns `true` if target is found
- `false` if it times out.

`Serial.findUntil()` inherits from the `stream` utility class.

## Syntax
```c++
Serial.findUntil(target, terminal);
```
`target` : the string to search for. Allowed data types: `char`.  
`terminal` : the terminal string in the search. Allowed dat types: `char`.
