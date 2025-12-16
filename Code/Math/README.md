# Math

## abs()

Calculates the absolute value of a number.

### Syntax
```c++
abs(x);
```
**Return Value**  
- `x` : if `x >= 0`
- `-x` : if `x < 0`

**Example** 
```c++
void setup(){
    Serial.begin(9600);

    int x = -4;
    int y = abs(x);
    Serail.print("The absolute value of x : ");
    Serial.print(x);
}

void loop() {}
```

## constrain()
Constrains a number to be within a range.
### Syntax
```c++
constrain(x, a, b);
```
- `x` : the number to constrain
- `a` : the lower end of the range
- `b` : the upper end of the range

**Return Value**
- `x` : if `x` is between `a` and `b`
- `a` : if `x` is less than `a`
- `b` : if `x` is greater than `b`

**Example**  
```c++
sensVal = constrain(sensVal, 10, 150);  // limits range of sensor values to between 10 and 150
```

## map()
the map() function is used to `convert (scale) a number from one range to another`.
### Syntax
```c++
map(value, fromLow, fromHigh, toLow, toHigh);
```
**Example**
```c++
int sensorValue = analogRead(A0);   // 0 to 1023
int outputValue = map(sensorValue, 0, 1023, 0, 255);
```
- `analogRead()` gives values from **0–1023**
- PWM output (`analogWrite()`) needs **0–255**
- `map()` converts the sensor reading into a usable PWM value

**Most Populat Example**
```c++
int pot = analogRead(A0);
int angle = map(pot, 0, 1023, 0, 180);
servo.write(angle);
```
Turns a potentiometer into a servo angle controller.

### Formula used
```
(value - fromLow) * (toHigh - toLow) / (fromHigh - fromLow) + toLow
```

## max()
Calculates the maximum of two numbers
### Syntax
```c++
max(x, y);
```
**Example**  
```c++
void setup() {
  Serial.begin(9600);

  int x = 2;
  int y = 3;
  int z = max(x, y);

  Serial.print("x   = ");
  Serial.println(x);
  Serial.print("y   = ");
  Serial.println(y);
  Serial.print("max = ");
  Serial.println(z);
}

void loop() {}

```

## min()
Calculates the minimun of two numbers.
```c++
min(x, y);
```
**Example**
```c++
void setup() {
  Serial.begin(9600);

  int x = 2;
  int y = 3;
  int z = min(x, y);

  Serial.print("x   = ");
  Serial.println(x);
  Serial.print("y   = ");
  Serial.println(y);
  Serial.print("min = ");
  Serial.println(z);
}

void loop() {}
```

## pow()
Calculates the value of a number raised to a power. `pow()` can be used to raise a number to a fractional power.
### Syntax
```c++
pow(base, exponent);
```
**Example**
```c++
void setup() {
  Serial.begin(9600);

  int x = 2;
  int y = 3;
  double z = pow(x, y);
  Serial.print(x);
  Serial.print(" raised to the power of ");
  Serial.print(y);
  Serial.print(" is ");
  Serial.println(z);
}

void loop() {}
```

## sq()
Calculates the square of a number: the number multiplied by itself.

### Syntax
```c++
sq(x);
```
**Example**:
```c++
void setup() {
  Serial.begin(9600);

  int x = 4;
  double y = sq(x);
  Serial.print("The square of ");
  Serial.print(x);
  Serial.print(" is ");
  Serial.println(y);
}

void loop() {}
```

## sqrt()
Calculates the square root of a number.
### Syntax
```c++
sqrt(x);
```
**Example**
```c++
void setup() {
  Serial.begin(9600);

  int x = 4;
  double y = sqrt(x);
  Serial.print("The square root of ");
  Serial.print(x);
  Serial.print(" is ");
  Serial.println(y);
}

void loop() {}
```