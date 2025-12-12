# String
`String` is a Data type in Arduino are used to handle text. They can be created using the `String` class or as character arrays (C-strings).

string

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

## String Functions
1. [String.charAt()](String/String.c_str().md)
1. [String.charAt()](String/String.charAt().md)
1. [String.compareTo()](String/String.compareTo().md)
1. [String.concat()](String/String.concat().md)
1. [String.endsWith()](String/String.endsWith().md)
1. [String.equals()](String/String.equals().md)
1. [String.equalsIgnoreCase()](String/String.equalsIgnoreCase().md)
1. [String.getBytes()](String/String.getBytes().md)
1. [String.indexOf()](String/String.indexOf().md)
1. [String.lastIndexOf()](String/String.lastIndexOf().md)
1. [String.length()](String/String.length().md)
1. [String.remove()](String/String.remove().md)
1. [String.replace()](String/String.replace().md)
1. [String.reserve()](String/String.reserve().md)
1. [String.setCharAt()](String/String.startsWith().md)
1. [String.startsWith()](String/String.startsWith().md)
1. [String.substring()](String/String.substring().md)
1. [String.toCharArray()](String/String.toCharArray().md)  
1. [String.toDouble()](String/String.toDouble().md)
1. [String.toFloat()](String/String.toFloat().md)
1. [String.toInt()](String/String.toInt().md)
1. [String.toLowerCase()](String/String.toLowerCase().md)
2. [String.toUpperCase()](String/String.toUpperCase().md)
3. [String.trim()](String/String.trim().md)