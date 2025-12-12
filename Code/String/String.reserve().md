# String.reserve()

The String reserve() function allows you to allocate a buffer in memory for manipulating Strings.

## Syntax
```c++
myString.reserve(size);
```
- `size` : The number of bytes in memory to save for String manipulation. Allowed data types : `unsigned int`.

**Return Values**  
Nothing

## Example
```c++
String myString;

void setup() {
  Serial.begin(9600);

  myString.reserve(26);
  myString = "Arduino";
  myString += "GetStarted";
  myString += ".com";

  // print the String:
  Serial.println(myString);
}

void loop() {
}

```