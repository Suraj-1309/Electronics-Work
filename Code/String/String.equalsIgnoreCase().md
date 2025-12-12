# String.equalsIgnoreCase()

Compares two Strings for equality. The Comparsion is not case-sensitive, meaning the String("hello") is equal to the String("Hello").

## Syntax
```c++
myString.equalsIgnoreCase(myString2);
```
**Return Values**
- `true` : if myString equals myString2 (ignoring case).
- `false` : Otherwise.

## Example
```c++
void setup() {
  Serial.begin(9600);

  String myString = "Arduino";

  if (myString.equalsIgnoreCase("ARDUINO"))
    Serial.println("Two strings is equal to each other");
  else
    Serial.println("Two strings is NOT equal to each other");
}

void loop() {
}

```
