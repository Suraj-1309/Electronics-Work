# String.endsWith()

Check whether or not a String ends with the characters of another String.

## Syntax
```c++
myString.endsWith(myString2);
```
**Return Values**:  
- true : if myString ends with the charactes of myString2.
- false : Otherwise.

## Example:
```c++
void setup(){
    Serial.begin(9600);

    String myString = "ArduinoGetStarted.com";
    String myString2 = ".com";
    
    if(myString.endsWith(myString2)){
        Serial.printlln("The string is ended with .com");
    }
    else{
        Serial.println("The string is NOT ended with .com");
    }
}

void loop(){
    
}
```