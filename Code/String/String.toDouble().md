# String.toDouble()

Converts a valid String to a double. The input String should start with a digit. If the String contains non-digit characters, the function will stop performing the conversion.  

For example, the Strings "123.45", "123", and "123fish" are converted to 123.45, 123.00 and 123.00 respectively.

Note that "123.456" is approximated with 123.46. Note too that floats have only 6-7 decimal digits of percision and that longer Strings might be truncated.

## Syntax
```c++
myString.toDouble();
```

## Example
```c++
void setup(){
    Serial.begin(9600);

    String myString = "20.9";
    float myDouble = myString.toDouble();
    Serial.println(myDouble);
}

void loop(){
    
}
```