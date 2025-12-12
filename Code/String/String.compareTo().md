# String.compareTo()

Compares two Strings, testing whether one comes before or after the other, or whether they're equal. the strings are compared character by character, using the ASCII values of the characters. That means, for example, that `'a'` comes before `'b'` but after `'A'`. Number come before letters.

## Syntax
```c++
myString.comparetTo(myString2);
```
**Return Values**  
- `a negative number` : if myString comes before myString2.
- `0` : if String equals myString2.
- `a positive number` : if myString comes after myString2.

## Example
```c++
void setup() {
  Serial.begin(9600);

  String myString = "Arduino";
  String myString2 = "ArduinoGetStarted.com";

  int result = myString.compareTo(myString2);
  Serial.println(result);
}

void loop() {
}
```
