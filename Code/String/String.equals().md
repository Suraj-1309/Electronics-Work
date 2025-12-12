# String.equals()

Compares two Strings for equality. The comparison is case-sensitive, meaning the String "hello" is not equal to the String "HELLO".

## Syntax
```c++
myString.equals(myString2);
```
**Return Values**
- `true` : if string equals string2.
- `false` : otherwise

## Example
```c++
void setup() {
  Serial.begin(9600);

  String myString = "Arduino";

  if (myString.equals("Arduino"))
    Serial.println("Two strings is equal to each other");
  else
    Serial.println("Two strings is NOT equal to each other");
}

void loop() {
}

```