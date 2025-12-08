# Serial.print()

Prints data to the serial port as human-readable ASCII text.  
This command can take many forms.

- Numbers are printed using an ASCII character for each digit.
- Floats are similarly printed as ASCII digits, defaulting to two decimal places.
- Bytes are sent as a single character.
- Characters and strings are sent as is.

For example:

```cpp
Serial.print(78);       // gives "78"
Serial.print(1.23456);  // gives "1.23"
Serial.print('N');      // gives "N"
Serial.print("Hello world."); // gives "Hello world."
```

## Syntax
```
Serial.print(val)
```
or

```
Serial.print(val, format)
```
## Parameter Values

- **Serial**:  
Serial port object.  
See the list of available serial ports for each board on the Serial main page.

- **val**:  
The value to print.  
Allowed data types: any data type.

- **format** *(optional)*:   
Specifies:   

1️ **The base (format) for integral data types**  
*(byte, char, int, long, short, unsigned char, unsigned int, unsigned long, word)*  
Permitted values:

| Format | Base | Description |
|--------|------|-------------|
| `BIN`  | 2    | binary (base 2) |
| `OCT`  | 8    | octal (base 8) |
| `DEC`  | 10   | decimal (base 10) |
| `HEX`  | 16   | hexadecimal (base 16) |

2️ **Number of decimal places for printing floating-point numbers**  
*(double, float)*  
Example:
```c++
Serial.print(78, BIN) // 1001110
Seril.print(1.23456, 0) // 1
```
**NOTE** :
We can pass flash-memory based strings to `Serial.print()` by wrapping them with `F()`:

```
Serial.print(F("Hello World"))
```

## Return Values
`print()` return the number of bytes written, though reading that number is optional. Data type: `size_t`.
