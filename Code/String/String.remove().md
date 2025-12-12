# String.remove()

Modify in place a String removing chars from the provided index to the end of the String or from the provided index to index plus count.

## Syntax
```c++
myString.remove(index);
myString.remove(index, count);
```
- `index` : the position at which to start the remove process (zero indexed).
- `count` : The number of characters to remove.

**Return Values** : Nothing  

## Example
```c++
void setup(){
    Serial.begin(9600);

    String myString = "Arduino";
    Serial.println(myString);

    myString.remove(2, 2);
    Serial.println(myString);
}

void loop(){

}
```

