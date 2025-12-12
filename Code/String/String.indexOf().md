# String.indexOf()

Finds the position of the first occurence of a character or a string inside another string. By default, searches from the beginning of the String, but can also start from a given index, allowing for the locating of all instances of the character or String.

## Syntax
```c++
myString.indexOf(val);
myString.indexOf(val, from);
```
- `val` : the value of the search for. Allowed data types: `char`, `String`.
- `from`: the index to start the search from.

## Example
```c++
void setup(){
    Serial.begin(9600);

    String myString = "Arduino, ArduinoGetStarted.com";
    int index = myString.indexOf("Arduino");
    Serial.println(index);
}

void loop(){

}
```

