# String.toFloat()

Converts a valid string to a float. The input string should start with a digit. If the String contains non-digit characters, the functions will stop perfoming the conversion.  

For example, the Strings "123.45", "123", and "123fish" are converted to 123.45, 123.00 and 123.00 respectively.  

Note too that floats have only 6-7 decimal digits of precision and that longer Strings might be truncated.

## Syntax
```c++
myString.toFloat();
```

## Example:
```c++
void setup(){
    Serial.begin(9600);

    String myString = "20.05";
    float myFloat = myString.toFloat();
    Serial.println(myFloat);
}

void loop(){
    
}
```
