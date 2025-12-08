# digitalWrite()

Write a `HIGH` or `LOW` value to a digital pin.

If the pin has been configured as an `OUTPUT` with `pinMode()`, its voltage will be set to the corresponding value: 5V (or 3.3V on 3.3V boards) for `HIGH`, 0V (ground) for `LOW`.

If the pin is configured as an `INPUT`, `digitalWrite()` will enable(`HIGH`) or disable(`LOW`) the internal pullup on the input pin. 

**NOTE** : It is recommended to set the `pinMode()` to `INPUT_PULLUP` to enable the internal pull-up resistor.

If you do not set the `pinMode()` to `OUTPUT`, and connect an LED to a pin, when calling `digitalWrite(HIGH)`, the LED may appear dim. Without explicitly setting `pinMode()`, `digitalWrite()` will have enabled the internal pull-up resistor, which acts like a large current-limiting resistor.

```c++
digitalWrite(pin, value);
```
**pin**: the Arduino pin number.
**value** : `HIGH` or `LOW`.

**Return Value**   
nothing

## Example
```c++
void setup(){
  pinMode(13, OUTPUT);
}

void loop(){
  digitalWrite(13, HIGH);
  delay(1000);
  digitalWrite(13, LOW);
  delay(1000);
}
```