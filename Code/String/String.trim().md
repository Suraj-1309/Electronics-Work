# String.trim()

Det a version of the String with any leading and trailing whitespace removed.  
As of 1.0, `String.trim()` modifies the String in place rather than returning a new one.

## Syntax:
```c++
myString.trim();
```
**Return** : Nothing

**example**:
```c++
myString = " Arduino  ";
Serial.println(myString);          // "Arduino"
```