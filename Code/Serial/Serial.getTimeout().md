# Serial.getTimeout()

`Serial.getTimeout()` returns the timeout value set by `Serial.setTimeout()`.

## Syntax
```c++
Serial.getTimeout()
```
**Return Value**:
The timeout value in milliseconds set by `Serial.setTimeout()`. Data type: `unsiged long`.

## Example:
```c++
void setup(){
    Serial.begin(9600);

    Serial.println(Serial.getTimeout()); // print the default value -> 1000
    Serial.setTimeout(1500); // set new value to 1500 millliseconds
    Serial.println(Serial.getTiimeout); // print the new value
}

void loop(){

}
```

```output
1000
1500
```
