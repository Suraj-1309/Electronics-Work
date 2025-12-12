# String.charAt()

Access a particular character of the String.

## Syntax
```c++
myString.charAt(n);
```
**Return Values** : The n'th character of the String.

## Example
```c++
void setup(){
    Serial.begin(9600);

    String myString = "Arduino";
    char myChar = myString.charAt(2);
    Serial.println(myChar);
}

void loop(){
    
}
```