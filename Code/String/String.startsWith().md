# String.substring()

check whether or not a String starts with the characters of another String.

## Syntax
```c++
myString.startsWith(myString2);
```
- `myString` `myString2` : a variable of types `String`.

**Return Values**  
- `true` : If myString starts with the characters of myString2.
- `false` : Otherwise.

## Example Code
```c++
void setup() {
  Serial.begin(9600);

  String myString = "ArduinoGetStarted.com";
  String myString2 = "Arduino";

  if (myString.startsWith(myString2))
    Serial.println("The string is started with Arduino");
  else
    Serial.println("The string is NOT started with Arduino");
}

void loop() {
}

```