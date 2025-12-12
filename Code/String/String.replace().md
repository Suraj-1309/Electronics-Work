# String.replace()

The String replace() function allows you to replace all instances of a given character with another character. you can also use replace to replace substrings of a String with a different substring.

## Syntax
```c++
myString.repalce(substring1, substring2);
```

## Example
```c++
void setup() {
  Serial.begin(9600);

  String substring1 = "Arduino";
  String substring2 = "ArduinoGetStarted.com";
  String myString = "Hello Arduino!";
  Serial.println(myString); // string before

  myString.replace(substring1, substring2);
  Serial.println(myString); // string after
}

void loop() {
}

```