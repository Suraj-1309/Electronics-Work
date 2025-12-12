# String.substring()

Get a substring of a String. The starting index is inclusive ( the corresponding character is included in the substring), but the optional ending index is exlusive (the corresponding character is not included in the substring). If the ending index is omitted, the substring continues to the end of the String.

## Syntax
```c++
myString.substring(from);
myString.substring(from, to);
```

## Example
```c++
void setup(){
    Serial.begin(9600);

    String myString = "ArduinoGEtStarted.com";
    String sub = myString.substring(0, 7);

    Serial.println(myString);
    Serial.println(sub);
}

void loop(){
    
}
```