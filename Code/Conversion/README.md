# Conversion

Changing one Data type into another.

## Types of Conversion

### Widening (Safe, No Data Loss)

- Converting a smaller/less precise type to a larger/more capable type.
- Typically safe because the target type can represent all values of the source.
- Examples:
  - `uint8_t → uint16_t → uint32_t`
  - `int → long`
  - `int → float` (integer magnitude preserved; fractional precision added)
- In Arduino C/C++, these often happen implicitly without a cast.

### Narrowing (Potential Data Loss)

- Converting a larger/more precise type to a smaller/limited type.
- Risk of overflow, truncation, or precision loss; usually requires explicit cast.
- Examples:
  - `uint32_t → uint16_t` (high-order bits discarded if value > 65535)
  - `long → int` (on AVR, `int` is 16-bit; values outside −32768..32767 wrap)
  - `float → int` (fraction dropped; 3.9 → 3)
  - `double → float` (on ARM, `double` is 8 bytes; precision can be lost)

### Embedded Notes (Arduino)

- AVR (UNO/Nano): `int` is 16-bit; `long` is 32-bit.
- SAMD/Due: `int` is 32-bit.
- Be careful when mixing types across APIs (e.g., `analogRead()` returns `int` on AVR) and when doing arithmetic—promotions may occur, but assignments can still narrow.

### Good Practices

- Prefer widening when possible; avoid unintended narrowing in assignments.
- Use explicit casts for intentional narrowing and document the rationale.
- Check ranges before narrowing: clamp or saturate values.
- For floating → integer, decide rounding strategy (`floor`, `ceil`, `round`).
- In ISR/shared data, mind type sizes on 8-bit MCUs for atomic access.

## Fuctions retalted to conversion

### 1. byte()

Convets a value to the `byte` data type.

#### Syntax
```c++
byte(x);
(byte)x // c - style type conversion
```

### 2. char()

Converts a value to the `char` data type.

#### Syntax
```c++
char(x)
(char) x // c - style type conversion
```

### 3. float()

converts a value to the `float` data types.

#### syntax
```c++
float(x);
(float) x // c- style type conversion
```

### 4. int
Converts a value to the `int` data types.

#### Syntax
```c++
int(x);
(int) x // c-style type conversion
```

### 5. long
Converts a value to the `long` data type.

#### Syntax
```c++
long(x);
(long) x // c- style type conversion
```

### 6. (unsigned int)
Converts a value to the `unsigned int` data type.

#### Syntax
```c++
(unsigned int) x;
```

### 7. (unsigned long)
Converts a value to the `unsigned long` data type.

#### Syntax
```c++
(unsigned long) x;
```

### 8. word()
Converts a value to the `word` data type.

#### Syntax
```c++
word(x)
word(h, l)
(word) x (C-style type conversion)
```
- `x` : a value, allowed data types: any type.
- `h` : the high - order (leftmost) byte of the word.
- `l` : the low - order (rightmost) byte of the word.

