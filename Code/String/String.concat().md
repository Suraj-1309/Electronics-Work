# String.concat()

Appends the parameter to a String.

## Syntax
```c++
myString.concat(parameter);
```
**Return Values**  
- `true` : success  
- `false` : failure (in which case the String is left unchanged).

## Example Code
```c++
void setup(){
    Serial.begin(9600);

    String myString = "Aruino";
    Serial.println(myString);

    myString.concat("GetStarted.com");
    Serial.println(myString);
}

void loop(){

}
```
