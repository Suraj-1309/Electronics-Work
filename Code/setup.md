# setup()

The `setup()` function is calleed when a sketch starts. Use it to initialize variables, pin modes, start using libraries, etc.

The `setup()` function will only run once, after each powerup or reset of the Arduino Board.

```c++
void setup(){
    Serial.begin(9600);
}

void loop(){
    Serial.println("Hello World");
    delay(1000);
}
```