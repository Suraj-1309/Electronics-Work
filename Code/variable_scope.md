# Variable Scope and Qualifiers

## const
- stand for constant
- a variable `qualifier`
- makes a variable `read-only` means once you declare it you can't change it's value.

```c++
const float pi = 3.14;
```

## scope
Variables in programming have a *scope*, meaning where they can be accessed in the program.

### Types of Variables

#### Global Variables
- Declared **outside** all functions (e.g., before `setup()` and `loop()`)
- Accessible by **every function** in the program
- Useful for data shared across multiple functions

#### Local Variables
- Declared **inside** a function or a block `{ }`
- Only accessible **within that function or block**
- Helps prevent functions from accidentally changing other variables


## static
The `static` keyword is used to create variables that are visible to only one function. However unlike local variables `static` variables persist beyond the function call, preserving their data between function calls.

Variables declared as static will only be created and initialized the first time a function is called.

```c++
void loop(){
    static int score = 0;
    if(wins){
        score++;
    }
}
```

## volatile
`volatile` directs the compiler to load the variable from RAM and not from a storage register, which is temporary memory location where program variables are stored and manipulated.

A variable should be declared `volatile` whenever its value can be changed by something beyond the control of the code sectiion in which it appers, such as a concurrently exectuing thread.


**NOTE**  
If a **volatile variable** is larger than 1 byte (e.g., 16-bit `int` or 32-bit `long`), the Arduino (an 8-bit microcontroller) **cannot read it in one step**.

### Why this is a problem:
- The main code might read the first 8 bits of the variable
- At the same time, an interrupt may change the next 8 bits
- This can result in **corrupted or random values**


### Remedy:
Disable interrupts while reading the variable, so interrupts **cannot modify** the variable mid-read.

### Methods to safely read multi-byte volatile variables:
1. Use `noInterrupts()` to disable interrupts while reading
2. Use **ATOMIC_BLOCK** macro  
   - Ensures the read is performed as a single atomic operation (smallest possible MCU unit)

Example
```c++
#include <util/atomic.h> // this library includes the ATOMIC_BLOCK macro.
volatile int input_from_interrupt;

// Somewhere in the code, e.g. inside loop()
  ATOMIC_BLOCK(ATOMIC_RESTORESTATE) {
    // code with interrupts blocked (consecutive atomic operations will not get interrupted)
    int result = input_from_interrupt;
  }
```