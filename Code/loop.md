# loop()
After `void setup()` finishes,  `void loop()` starts running - and it keeps repeating forever. But `loop()` does not run inside `setup()`; it only starts after `setup()` ends.

The Arduino core basically does this internally:
```c++
int main() {
  init();        // internal hardware init
  setup();       // run once
  while (true) { // run forever
    loop();
  }
}
```
<br>
<br>

So after creating a `setup()` function which initializes and sets the initial values, the `loop()` function does precisely what its name suggests, and loops consecutively, allowing program to change and respond. Use it to actively control the Arduino board.
```C++
void setup(){
    Serial.begin(9600);
    Serial.println("This is setup code");
}

void loop(){
    Serial.println("This is loop code");
    delay(1000);
}
```