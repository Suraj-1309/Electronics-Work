# random()

The random function generates pseudo-random numbers.

## Syntax
```c++
random(max);
random(min, max);
```
- `min` : lower bound of the random value, inclusive (optional).
- `max` : upper bound of the random value, exclusive.

- **return value** : A random number betwen `min` and `max - 1`. Data type : `long`.

**Example** :
```c++
long randNumber;

void setup(){
    Serial.begin(9600);

    // if analog input pin 0 is unconnected, random analog noise will cause the call to randomSeed() to generate different seed numbers each time the sketch runs.
    // randomSeed() will then shuffle the random function.
    randomSeed(analogRead(0));
}

void loop(){
    // print a random number from 0 to 299
    randNumber = random(300);

    Serial.print("A random number from 0 to 299: ");
    Serial.println(randNumber);

    // print a random number from 10 to 19
    randNumber = random(10, 20);
    Serial.print("A random number from 10 to 19: ");
    Serial.println(randNumber);

    delay(1000);
}
```

**Note**

Arduino’s `random()` function **does not generate true randomness** on its own. Instead, it produces a **pseudo‑random sequence** — a list of numbers that looks random but is actually predictable.

If you don’t call `randomSeed()`, Arduino always starts with the **same default seed** every time it powers on. That means:

- You get **the same sequence of “random” numbers** every time the program runs.

- Your project behaves identically on each reset — not very random.


The `max` parameter should be chosen according to the data type of the variable in which the value is stored.

---
---  

# randomSeed()

`randomSeed()` initializes the random number generator with a starting value (seed).

If the seed changes each time, the random sequence changes too.

## Syntax
```c++
randomSeed(seed);
```

- `seed` : number to initialize the pseudo-random sequence. data types: `unsigned long`.

**Example Code**
```c++
long randNumber;

void setup(){
    Serial.begin(9600);
    randomSeed(analogRead(0));
}

void loop(){
    randNumber = random(300);
    Serial.print("A random number: ");
    Serial.println(randNumber);
    delay(1000);
}
```