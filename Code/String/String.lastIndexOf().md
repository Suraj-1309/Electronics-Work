# String.lastIndexOf()

Finds the position of the last occurrence of a character or a string inside another string.

By default, searches from the end of the String, but can also work backwards from a given index, allowing for the locating of all instances of the character or String.

## Syntax
```c++
myString.lastIndexOf(val);
myString.lastIndexOf(val, from);
```

- `val` : the value to search for.
- `from` : the index to work backwards from.

**Return Value** : The index of val within the string, or `-1` if not found.

## Example Code
```c++
void setup(){
    Serial.begin(9600);

    String myString = "Arduino, ArudinoGetStarted.com";
    int index = myString.lastIndexOf("Arduino");
    Serial.println(index);
}

void loop(){

}
```
