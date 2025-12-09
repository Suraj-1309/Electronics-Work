# Constant
Constant are predefined expressions.

## Boolean Constants
Define logical levels.   
There are two constants used to represent truth and falsity `true` and `false`

### false
`false` is defined as 0 (zero).

### true
`true` is often said to defined as 1, which is correct, but true has a wider definition.  
Any integer which is non-zero is true, in a Boolean sense.

**NOTE** that the `true` and `false` constants are typed in lowercase unlike `HIGH`, `LOW`, `INPUT` and `OUTPUT`.

## PIN Levels:
When reading or writing to a digital pin there are only two possible values a pin can take/ be - set - to: `HIGH` and `LOW`.

### HIGH (Arduino Digital Pin Logic Level)

The meaning of **HIGH** depends on whether a pin is configured as `INPUT` or `OUTPUT`.

<br>

#### HIGH when Pin is an INPUT

A pin configured as an `INPUT` using `pinMode()` and read using `digitalRead()` will return **HIGH** if:

- Voltage > 3.0V on 5V boards
- Voltage > 2.0V on 3.3V boards

<br>

#### INPUT with Pullup Enabled

If a pin is set as `INPUT` and then written **HIGH** using `digitalWrite()`, the internal pull-up resistor (≈20kΩ) is activated.

This causes:

- The input pin to read **HIGH** by default
- The pin will read **LOW** only if pulled low externally

Alternative method to enable pull-up resistor:

```cpp
pinMode(pin, INPUT_PULLUP);
```

<br>

#### HIGH when Pin is an OUTPUT

When an Arduino pin is configured as an `OUTPUT` using `pinMode()` and set to **HIGH** using `digitalWrite()`:

The pin voltage will be:
- **5V** on 5V Arduino boards (e.g., Uno, Mega)
- **3.3V** on 3.3V Arduino boards (e.g., Due, some Nano models)

In this state:
- The pin can **source current** to external components  
  (Example: powering an LED through a series resistor to ground)

<br>

### LOW 

The meaning of **LOW** depends on whether a pin is configured as `INPUT` or `OUTPUT`.

<br>

#### LOW when Pin is an INPUT

A pin configured as an `INPUT` using `pinMode()` and read with `digitalRead()` will return **LOW** if:

- Voltage < 1.5V on 5V boards
- Voltage < 1.0V (approx.) on 3.3V boards

<br>

#### LOW when Pin is an OUTPUT

When a pin is configured as `OUTPUT` with `pinMode()` and written **LOW** using `digitalWrite()`:

The pin voltage becomes:
- **0V** on both 5V and 3.3V Arduino boards

In this state:
- The pin can **sink current** from external components  
  (Example: LED connected through a resistor to +5V or +3.3V will turn ON)

<br>

## Digital Pins Modes
Digital pins can ve used as `INPUT`, `INPUT_PULLUP` or `OUTPUT`.  
Chainging a pin with `pinMode()` changes the electrical behavior of the pin.

### INPUT

```cpp
pinMode(pin, INPUT);
```

#### What it does:
- The pin acts as a **receiver** of electrical signals
- Used to **read** voltage levels using `digitalRead()`
- Has **very high impedance** → draws almost no current

#### How voltage is interpreted:
- **HIGH** → ~3V to 5V (on 5V boards)  
             ~2V to 3.3V (on 3.3V boards)
- **LOW** → ~0V to 1.5V (approx. threshold)

#### When to use:
- Reading push buttons or switches
- Reading digital sensors
- When an **external circuit** controls the signal on the pin

> ⚠️ Important: Floating inputs can read **unstable**, random HIGH/LOW values if nothing is connected.

<br>

### INPUT_PULLUP
```c++
pinMode(pin, INPUT_PULLUP);
```
#### What it does:
- Works like `INPUT` but **activates the internal pull-up resistor**
- Keeps the pin **HIGH by default**
- Reads **LOW** only when externally connected to **GND**

#### When to use:
- For buttons **without external resistors**
- To prevent **floating input** (random HIGH/LOW readings)

#### Example wiring:
```Arduino
Pin ── Button ── GND
(Default = HIGH, Pressed = LOW)
```

<br>

### OUTPUT
```c++
pinMode(pin, OUTPUT);
``` 
#### What it does:
- Allows the pin to **supply (source) or remove (sink) current**
- Used with `digitalWrite()` to control devices

#### Voltage output:
- **HIGH** → 5V (or 3.3V depending on the board)
- **LOW** → 0V

#### When to use:
- Turning LEDs **ON/OFF**
- Driving relays, buzzers, or motors (with proper transistor/driver circuits)

> ⚠️ Note: OUTPUT pins can only source/sink a limited current  
> Typically up to **~20mA per pin** (do not exceed to avoid damage)


## LED_BUILTIN
Most Arduino boards have a pin connectec to an on-board LED in series with a resistor, The constant `LED_BUILTIN` is the number of the pin to which the on-board LED is connected. Most boards have the LED connected to digital pin 13.