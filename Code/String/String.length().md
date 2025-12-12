# Stirng.length()

Returns the length of the String, in Characters. (Note that this doesn't include a trailing null character.)

## Syntax
```c++
myString.length();
```
**Return Values** : the length of the String in characters.

## Example
```c++
void setup(){
    Serial.begin(9600);

    String myString = "Arduino";
    int length = myString.length();
    Serial.println(length);
}

void loop(){

}
```
