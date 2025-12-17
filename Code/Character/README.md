# Characters

## isAlpha()
Check if a characters is alpha (that is letter) or not. Returns true if the characters contains a letter.

### Syntax
```c++
isAlpha(thisChar);
```

**Example**
```c++
char myChar;
void setup() {
  Serial.begin(9600);

  myChar = ' ';
  Serial.print(myChar);
  Serial.print(": ");
  if (isAlpha(myChar))  // tests if myChar is a letter
    Serial.println("The character is a letter");
  else
    Serial.println("The character is not a letter");

  myChar = 'A';
  Serial.print(myChar);
  Serial.print(": ");
  if (isAlpha(myChar))  // tests if myChar is a letter
    Serial.println("The character is a letter");
  else
    Serial.println("The character is not a letter");
}

void loop() {}
```

## isAlphaNumeric()
Check if a character is alphanumeric (that is a letter or a numbers) or not. Returns `true` if the character contains either a `number` or a `letter`.

### Syntax
```c++
isAlphaNumeric(thisChar);
```

**Example**
```c++
if (isAlphaNumeric(myChar)) { 
  Serial.println("The character is alphanumeric");
}
else {
  Serial.println("The character is not alphanumeric");
}
```

## isAscii()
Check if a character is Ascii or not. Returns true if the characters contains an Ascii character.

### Syntax
```c++
isAscii(thisChar);
```

**Eample**
```c++
if (isAscii(myChar)) { 
  Serial.println("The character is Ascii");
}
else {
  Serial.println("The character is not Ascii");
}
```

## isControl()

Check if a character is a control character or not. Returns true if the character is a control character.
### Syntax
```c++
isControl(thisChar);
```
**Example**
```c++
if (isControl(myChar)) {  // tests if myChar is a control character
  Serial.println("The character is a control character");
}
else {
  Serial.println("The character is not a control character");
}
```

A **control character** in Arduino is simply a non‑printable character used to control how text behaves when sent over Serial communication. These characters don’t show up as visible symbols; instead, they trigger actions like moving to a new line, sounding a beep, or ending a transmission.

| Control Character | Escape Code | ASCII Value | Meaning                                      |
|-------------------|-------------|-------------|----------------------------------------------|
| New Line          | `\n`        | 10          | Moves the cursor to the next line            |
| Carriage Return   | `\r`        | 13          | Moves cursor to the start of the line        |
| Tab               | `\t`        | 9           | Inserts a horizontal tab                     |
| Backspace         | `\b`        | 8           | Moves cursor back one position               |
| Null              | `\0`        | 0           | Marks end of a string (important in C/C++)   |


## isDigit()
Check if a character is a digit (that is a number) or not. Returns true if the character is a number.

### Syntax
```c++
isDigit(thisChar);
```

**Example**
```c++
if (isDigit(myChar)) {  // tests if myChar is a digit
  Serial.println("The character is a number");
}
else {
  Serial.println("The character is not a number");
}
```

## isGraph()
Check if a character is **printable** with some content (space is printable but has no content) or not. Returns true if the character is printable.

### Syntax
```c++
isGraph(thisChar);
```

**Example**
```c++
if (isGraph(myChar)) {  // tests if myChar is a printable character but not a blank space.
  Serial.println("The character is printable");
}
else {
  Serial.println("The character is not printable");
}
```

## isHexadecimalDigit()
Check if a character is an hexadecimal digit (A-F, 0-9) or not. Returns true if the character contains an hexadecimal digit.

### Syntax
```c++
isHexadecimalDigit(thisChar);
```

**Example**
```c++
if (isHexadecimalDigit(myChar)) { // tests if myChar is an hexadecimal digit
  Serial.println("The character is an hexadecimal digit");
}
else {
  Serial.println("The character is not an hexadecimal digit");
}
```

## isLowerCase()
check if a character is lower case (that is a letter in lower case) or not. Returns true if the character contains a letter in lower case.

### Syntax
```c++
isLowerCase(thisChar);
```

**Example**
```c++
if (isLowerCase(myChar)) {  // tests if myChar is a lower case letter
  Serial.println("The character is lower case");
}
else {
  Serial.println("The character is not lower case");
}
```

## isPrintable()

Check if a character is printable (that is any character that produces an output even a blank space) or not. Returns true if the character is printable.

### Syntax
```c++
isPrintable(thisChar);
```

**Example**
```c++
if (isPrintable(myChar)) {  // tests if myChar is printable char
  Serial.println("The character is printable");
}
else {
  Serial.println("The character is not printable");
}
```

## isPunct()
Check if a character is punctuation (that is a comma, a semicolon, an exlcamation mark and so on) or not. Returns true if the character is punctuation.

### Syntax
```c++
isPunct(thischar);
```

**Example**
```c++
if (isPunct(myChar)) {  // tests if myChar is a punctuation character
  Serial.println("The character is a punctuation");
}
else {
  Serial.println("The character is not a punctuation");
}
```

## isSpace()
Check if a character is a white-space character or not. 
- A space(`' '`)
- From feed (`'\f'`)
- Newline (`'\n`)
- Carriage return (`'\r'`)
- Horizontal tab (`'\t'`)
- Vertical tab (`'\v'`)

### Syntax
```c++
isSpace(thisChar);
```

**Exapmle**
```c++
if (isSpace(myChar))  // tests if myChar is a white-space character
    Serial.println("The character is white-space");
else
    Serial.println("The character is not white-space");
```

## isUpperCase()
Check if a character is upper case (that is, a letter in upper case) or not. Returns true if the character is upper case.

### Syntax
```c++
isUpperCase(thisChar);
```

**Example**
```c++
 if (isUpperCase(myChar)) // tests if myChar is an upper case letter
    Serial.println("The character is upper case");
else
    Serial.println("The character is not upper case");
```

## isWhitespace()
Check if a character is a space character or not. Returns true if the character is a space or horizontal tab (`\t`).
### Syntax
```c++
isWhiteSpace(thisChar);
```
**Example**
```c++
if (isWhitespace(myChar)) // tests if myChar is a space character
    Serial.println("The character is a space or tab");
else
    Serial.println("The character is not a space or tab");
```

