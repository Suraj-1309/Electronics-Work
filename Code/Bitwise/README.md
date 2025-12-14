# Bitwise Operator

Bitwise Operator are used to do operations with binary digits of the Value.

## 1. `<<` (left shift)

The left shift operator `<<` causes the bits of the left operand to be shifted `left` by the number of positions specified by the right operand.

### Syntax
```variable << number_of_bits;```

**Example Code** : 
```c++
int a = 5;      // binary: 0000000000000101
int b = a << 3; // binary: 0000000000101000, or 40 in decimal
```
   Operation  Result
   ---------  ------
    1 <<  0      1
    1 <<  1      2
    1 <<  2      4
    1 <<  3      8
    ...
    1 <<  8    256
    1 <<  9    512
    1 << 10   1024
    ...

## 2. `>>` (right shift)

The right shift operator `>>` causes the bits of the left operand to be shifted **right** by the number of positions specified by the right operand.

### Syntax
`variable >> number_of_bits;`

**Example**
```c++
int a = 40;     // binary: 0000000000101000
int b = a >> 3; // binary: 0000000000000101, or 5 in decimal
```
**NOTE**  
When you shift `x` right by y bits (x >> y), and the highest bit in `x` is a `1`, the behaviour depends on the exact data type of `x`. If x is of type `int`, the highest bit is the sign bit, determining whether `x` is negative or not, as we have discussed above.   
In that case, the sign bit is copied into lower bits, for esoteric historical reasons:
```c++
int x = -16;         // binary: 1111111111110000
int y = 3;
int result = x >> y; // binary: 1111111111111110
```

Thie behaviour, called `sign extension` and is often not the behaviour you want.

Instead, you may wish zeros to be shifted in from the left. It tunrs out that the right shift rules are different for unsigned int expressions, so you can use a typecast to suppress ones being copied from the left:
```c++
int x = -16;                       // binary: 1111111111110000
int y = 3;
int result = (unsigned int)x >> y; // binary: 0001111111111110
```

**Short Trick**  
You can use `>>` to divide number by powers of `2`:
```c++
int x = 1000;
int y = x >> 3; // integer division of 1000 by 8, causing y = 125.
```

## 3. `&` Bitwise AND
- if both input bits are `1`, the resulting output is `1`, 
- Otherwise the output is `0`.
Precise,  
```
    0  0  1  1    operand1
    0  1  0  1    operand2
    ----------
    0  0  0  1    (operand1 & operand2) - returned result
```
In Arduino, the type int is a `16-bit` value so using `&` between two int expressions causes `16` simultaneous AND operations to occur.

**Example**
```c++
int a =  92;    // in binary: 0000000001011100
int b = 101;    // in binary: 0000000001100101
int c = a & b;  // result:    0000000001000100, or 68 in decimal.
```

One of the most common uses of bitwise AND is to select a particular bit (or bits) from an integer value, often called `masking`. 
```c++
PORTD = PORTD & B00000011;  // clear out bits 2 - 7, leave pins PD0 and PD1 untouched (xx & 11 == xx)
```

## 4. `~` Bitwise NOT
Bitwise NOT changes each bit to its opposite: `0` becomes `1`, and `1` becomes `0`.
```
    0  1    operand1
    -----
    1  0   ~operand1
``` 
**Example**
```c++
int a = 103;  // binary:  0000000001100111
int b = ~a;   // binary:  1111111110011000 = -104
```



## 5. `|` Exclusive OR
The bitwise OR of two bits is `1` if either or both of the input bits is `1`, otherwise it is `0`.
Precise, 
```
    0  0  1  1    operand1
    0  1  0  1    operand2
    ----------
    0  1  1  1    (operand1 | operand2) - returned result
```
**Example**:
```c++
int a =  92;    // in binary: 0000000001011100
int b = 101;    // in binary: 0000000001100101
int c = a | b;  // result:    0000000001111101, or 125 in decimal.
```

One of the most common uses of the Bitwise OR is to set mulitple bits in a bit-packed number.
```c++
// Note: This code is AVR architecture specific
// set direction bits for pins 2 to 7, leave PD0 and PD1 untouched (xx | 00 == xx)
// same as pinMode(pin, OUTPUT) for pins 2 to 7 on Uno or Nano
DDRD = DDRD | B11111100;
```


## 6. `^` Exclusive XOR
- also known as **bitwise XOR**

A bitwise XOR operation results in a `1` only if the input buts are different, else it results in a `0`.

Precisly,
```
    0  0  1  1    operand1
    0  1  0  1    operand2
    ----------
    0  1  1  0    (operand1 ^ operand2) - returned result
```

**Example:**
```c++
int x = 12;     // binary: 1100
int y = 10;     // binary: 1010
int z = x ^ y;  // binary: 0110, or decimal 6
```

The `^` operator is used to **toggle** (i.e. change from 0 to 1, or 1 to 0) some of the bits in an integer expression. In a bitwise XOR operation if there is a `1` in the mask bit, that is inverted, if there is a `0`, the bit is not inverted and stays the same.

```c++
// Note: This code uses registers specific to AVR microcontrollers (Uno, Nano, Leonardo, Mega, etc.)
// it will not compile for other architectures
void setup() {
  DDRB = DDRB | B00100000;  // set PB5 (pin 13 on Uno/Nano, pin 9 on Leonardo/Micro, pin 11 on Mega) as OUTPUT
  Serial.begin(9600);
}

void loop() {
  PORTB = PORTB ^ B00100000;  // invert PB5, leave others untouched
  delay(100);
}
```
