# pinMode()

Configures the specified pin to behave either as an input or an output.

## Syntax
```c++
pinMode(pin, mode);
```
**pin** : the Arduino pin number to set the mode of.  

**mode** : `INPUT`, `OUTPUT`, or `INPUT_PULLUP`.

**Return Values**  
Nothing

## Example:
```c++
void setup(){
    pinMode(13, OUTPUT);
}

void loop(){
    digitalWrite(13, HIGH);
    delay(1000);
    digitalWrite(13, LOW);
    delay(1000);
}
```
