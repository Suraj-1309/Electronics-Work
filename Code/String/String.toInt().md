# String.toInt()

Converts a valid String to an integer.

The input string should start with an integer number.  
If the String contains non-integer numbers, the function will stop performing the conversion.

## Syntax
```c++
myString.toInt();
```

**Return**
- If no valid converion could be performed because the String doesn't start with an integer number, a zero `0` is returned. Data type `long`.

### Example
```c++
void setup(){
    Serial.begin(9600);

    String myString = "20";
    long myInt = myString.toInt();
    Serial.println(myInt);
}

void loop(){
}
```