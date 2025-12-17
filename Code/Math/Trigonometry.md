# Trigonometry

## cos()

Calculates the cosine of an angle (in radians). The result will be between -1 and 1.

### Syntax
```c++
cos(rad);
```
- `rad` : The angle in radians : Allowed data types: `float`;
**Return Value** : The cos of the angle.
**Example Code** : 
```c++
void setup() {
  Serial.begin(9600);

  for (int angle = 0; angle <= 360 ; angle += 15) {
    float angle_rad = angle * M_PI / 180;
    float cos_result = cos(angle_rad);

    Serial.print("cos(");
    Serial.print(angle);
    Serial.print("°) = ");
    Serial.println(cos_result);
  }
}

void loop() {
}
```


## sin()

Calculates the sine of an angle (in radians). The result will be between `-1` and `1`.

### Syntax
```c++
sin(rad);
```
- `rad`: The angle in radians.

**Example**
```c++
void setup() {
  Serial.begin(9600);

  for (int angle = 0; angle <= 180; angle += 15) {
    float angle_rad = angle * M_PI / 180;
    float sin_result = sin(angle_rad);

    Serial.print("sin(");
    Serial.print(angle);
    Serial.print("°) = ");
    Serial.println(sin_result);
  }
}

void loop() {
}
```

## tan()
Calculates the tangent of an angle (in radians). The result will be between  `-infinity` and `infinity`.

### syntax
```c++
tan(rad);
```

**Example**
```c++
void setup() {
  Serial.begin(9600);

  for (int angle = 0; angle <= 180; angle += 15) {
    float angle_rad = angle * M_PI / 180;
    float tan_result = tan(angle_rad);

    Serial.print("tan(");
    Serial.print(angle);
    Serial.print("°) = ");
    Serial.println(tan_result);
  }
}

void loop() {
}
```
