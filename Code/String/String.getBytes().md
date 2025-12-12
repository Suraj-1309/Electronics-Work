# String.getBytes()

Copies the String's characters to the supplied buffer.

## Syntax
```c++
myString.getBytes(buf, len);
```
- `buf` : the buffer to copy the characters into. Allowed data types: array of `byte`.
- `len` : the size of the buffer. Allowed data types: `unsigned int`.

## Example
```c++
void (){
    Serial.begin(9600);

    String myString = "Arduino";
    byte buffer[myString.length() + 1];

    myString.getBytes(buffer, myString.length() + 1);

    for(int i = 0; i < myString.length() + 1; i++){
        Serial.println(buffer[i], HEX);
    }
}

void loop(){

}
```
