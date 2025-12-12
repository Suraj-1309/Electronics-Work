# String.setCharAt()

Sets a character of the String. Has no effect on indices outside the existing length of the String.

## Syntax:
```c++
myString.setCharAt(index, c);
```
- `myString` : a variable of type `String`.
- `index` : the index to set the character at.
- `c` : the character to store to the given location.

**Return Values**  
- Nothing

## Example Code
```c++
void setup() {
  Serial.begin(9600);

  String myString = "Arduino";
  Serial.println(myString); // string before

  myString.setCharAt(0, 'B');
  myString.setCharAt(6, 'Y');
  Serial.println(myString); // string after
}

void loop() {
}

```