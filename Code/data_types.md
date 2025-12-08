# Data Types

## Array
Collection of variables that are accessed with an index number.

```c++
int myInts[6];
int myPins[] = {2, 4, 8, 3, 6};
int mySensVals[6] = {2, 4, -8, 3, 2, -7};
char message[6] = "hello";
```

## bool
A `bool` holds one of the values, `true` or `false`. (Each `bool` variables occupies one byte of memory.)
```c++
bool var = val;
```

## boolean
`boolean` is a non-standard type alias for `bool` defined by Arduino. It's recommended to instead use the standard type `bool`, which is identical.

## byte
A byte stores an 8-bit unsigned number, from 0 to 255.

```c++
byte var = val;
```

## char 
A data type used to store a character value. 
**NOTE** A character literals are written in single quotes, like this: 'A'.  
Characters are stored as numbers(**ASCII**).

Size - 8 bytes
```c++
char var = val;
```

## double
double precision floating poin number. 

On **Uno** and other **ATMEGA** based boards, this oppuies **4 bytes**. That is the double implementation is exaclty the same as the float.

On **Arduino Due**, doubles have **8-byte(64 bit)** precision.

```c++
double var = val;
```

## float
stores a number that has a decimal point.
They are stored as **32 bits (4 bytes)** of information

```c++
float var = val;
```

## int
integers are your primary data-type for number storage.
### Size & Range Differences by Board

| Arduino Board Type | `int` Size | Value Range |
|------------------|-----------|-------------|
| **Uno / ATmega-based boards** | 16 bits (2 bytes) | −32,768 to 32,767 *(−2¹⁵ to 2¹⁵−1)* |
| **Due / SAMD-based boards** (e.g., MKR1000, Zero) | 32 bits (4 bytes) | −2,147,483,648 to 2,147,483,647 *(−2³¹ to 2³¹−1)* |

---

### Negative Number Representation

Arduino uses **2’s complement** to store negative values:

- The **most significant bit (MSB)** → sign bit
- Remaining bits are inverted and **+1** is added to form negative numbers

---

### Behavior in Code

- Arduino automatically handles arithmetic with negative numbers correctly.
- Some edge cases may appear when using **right bit-shift (`>>`)** with signed values.

```c++
int countUp = 0;
```

## long
Long variables are extended size variables for number storage, and store 32 bits (4 bytes) from -2,147,483,648 to 2,137,483,647.
```c++
long var = val;
```

## short
A short is a 16-bit data - type.

```c++
short var = val;
```

## size_t
**size_t** is a data type capable of representing the size of any object in bytes. 

Example of the use of `size_t` are the return type of `sizeof()` and `Serial.print()`.

```c++
size_t var = val;
```

## string

Strings are used for storing and manipulating text in Arduino programs.

There are **two types** of strings in Arduino:
1. **String Object** (Capital `S`)
2. **Character Array Strings** (C-style strings)

---

### 1️. String Object

- Comes from the **String** class in Arduino
- Easy to use for text manipulation
- Supports functions like:
  - `length()`
  - `concat()`
  - `substring()`
  - `indexOf()`
  - `toInt()`, etc.

**Example:**
```cpp
String name = "Arduino";
```
**Note**: Uses dynamic memory → may cause memory fragmentation on small boards (like Uno).

### 2. C-style character Arrays

- Traditional C-strings using a `char` array  
- Always end with a **null character (`\0`)**
- More memory-efficient and safer for small microcontrollers

**Example:**
```c
char name[] = "Arduino";
```

## String()
Constructs an instance of the String class.
```c++
String(val);
String(val, base);
String(val, decimalPlaces);
```
Constructing a String from a number results in a string that contains the ASCII representation of that number.
- The default is base ten, so `String thisString = String(13);` gives you the String `"13"`;
- However, you can use other bases. For example: `String thisString = String(13, HEX);` gives you the String `"D"`, which is the hexadecimal representation of the decimal value 13.

### Example:
```c++
String stringOne = "Hello String";                   // using a constant String
String stringOne = String('a');                      // converting a constant char into a String
String stringTwo = String("This is a string");       // converting a constant string into a String object
String stringOne = String(stringTwo + " with more"); // concatenating two strings
String stringOne = String(13);                       // using a constant integer
String stringOne = String(analogRead(0), DEC);       // using an int and a base
String stringOne = String(45, HEX);                  // using an int and a base (hexadecimal)
String stringOne = String(255, BIN);                 // using an int and a base (binary)
String stringOne = String(millis(), DEC);            // using a long and a base
String stringOne = String(5.698, 3);                 // using a float and the decimal places

```


## unsiged char
The unsigned char data type encodes numbers from 0 to 255.

**Note** for the consistency of Arduino programming style, the **byte** data type is to be preferred.
```c++
unsigned char var = val;
```


## unsigned int
Work same as `int` data type but it not store an negative value which makes it range from 0 to 65535.
```c++
unsigned int ledPin = 13;
```

## unsigned long
Unsigned long variables are extended size variables for number storage, and store 32 bits (4 bytes).

They don't store any negative numbers, making range from 0 to 4,294,967,295.
```c++
unsigned long var = val;
```

## void 
The `void` keyword is used only in function declarations.

It indicates that the function is expected to return no information to the function from which it was called.

```c++
void setup(){
    // code goes here
}
```

## word
A word can store an unsigned number of at least 16 bits (from 0 to 65535).
```c++
word var = val;
```
example:
```c++
word w = 10000;
```
