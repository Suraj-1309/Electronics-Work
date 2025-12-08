# Constant
Constant are predefined expressions.

## Boolean Constants
Define logical levels.   
There are two constants used to represent truth and falsity `true` and `false`

### false
`false` is defined as 0 (zero).

### true
`true` is often siad to defined as 1, which is correct, but true has a wider definition.  
Any integer which is non-zero is true, in a Boolean sense.

**NOTE** that the `true` and `false` constants are typed in lowercase unlike `HIGH`, `LOW`, `INPUT` and `OUTPUT`.

## PIN Levels:
When reading or writing to a digital pin there are only two possible values a pin can take/ be - set - to: `HIGH` and `LOW`.

### HIGH
The meaning of `HIGH` is so

## LED_BUILTIN
Most Arduino boards have a pin connectec to an on-board LED in series with a resistor, The constant `LED_BUILTIN` is the number of the pin to which the on-board LED is connected. Most boards have the LED connected to digital pin 13.