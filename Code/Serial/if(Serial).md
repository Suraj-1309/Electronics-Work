# if(Serial)

Indicates if the specified Serial port is ready.

On the boards with native USB, `if(Serial)` (or `if(SerialUSB)` on the Due) indicates whether or not USB CDC ( USB Communications Device Class) serial connection is open. For all other boards, and the non-USB CDC ports, this will always return true.

## Syntax
```c++
if(Serial)
```

**Return type**  
Returns true if the specified serial port is available. This will only return false if querying the Leonardo's USB CDC serial connection before it is ready.  
Data type: `bool`

## Example
```c++
void setup(){
    Serial.begin(9600);

    While(!Serial){
        ; // wait for serial port to connect. Needed for native USB
    }
}

void loop(){
    // proceed normally
}
```