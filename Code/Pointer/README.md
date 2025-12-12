# Pointers in Embedded C (Arduino)

Pointers hold memory addresses. On Arduino (AVR 8-bit, ARM 32-bit), they let you access variables, buffers, peripheral registers, and program memory efficiently.

READ FIRST:
- **[*](dereference.md)**
- **[&](reference.md)**

## Why Pointers Matter

- Work with arrays, strings, and buffers without copying.
- Access hardware registers and memory-mapped I/O.
- Pass data to functions by reference to avoid copying.
- Share data between ISRs and `loop()` when combined with `volatile` and interrupt safety.

## Core Syntax

```c
int value = 42;
int *p = &value;   // p stores the address of value
int x = *p;        // dereference: read the data at that address
*p = 7;            // write through the pointer
```

### Pointer Types and Sizes (typical)

- AVR (UNO/Nano): 16-bit addresses → pointers are 2 bytes.
- ARM (Due/MKR/Zero): 32-bit addresses → pointers are 4 bytes.

## Arrays and Pointers

```c
int samples[4] = {10, 20, 30, 40};
int *p = samples;       // same as &samples[0]
int first = *p;         // 10
int third = *(p + 2);   // 30
```

Pointer arithmetic moves by element size (here, 2 bytes per int on AVR, 4 bytes on ARM).

## Pointer to `const`

```c
const int limit = 100;
const int *p = &limit;   // data is read-only through this pointer
// *p = 5;  // not allowed
```

Use `const` pointers to protect data and enable compiler optimizations.

## Pointers and `volatile`

Use `volatile` when data changes outside normal flow (ISRs, hardware). Combine with interrupt safety when multi-byte types are accessed on 8-bit MCUs.

```c
volatile uint16_t ticks = 0;

ISR(TIMER1_COMPA_vect) {
	ticks++;  // modified in interrupt
}

void loop() {
	uint16_t snapshot;
	noInterrupts();
	snapshot = ticks;   // atomic read on AVR for 16-bit value
	interrupts();
	// use snapshot
}
```

## Pointers to Functions

Function pointers let you select behavior at runtime (state machines, callbacks).

```c
void ledOn()  { digitalWrite(LED_BUILTIN, HIGH); }
void ledOff() { digitalWrite(LED_BUILTIN, LOW);  }

void (*action)(void) = ledOff; // pointer to function

void setup() {
	pinMode(LED_BUILTIN, OUTPUT);
	action = ledOn;
	action();
}
```

## Pointers and PROGMEM (Flash on AVR)

On AVR, string literals live in flash; copying to RAM wastes space. Use `PROGMEM` plus `pgm_read_*` helpers.

```c
#include <avr/pgmspace.h>

const char msg[] PROGMEM = "Hello";

char buffer[6];
void setup() {
	strcpy_P(buffer, msg);    // copies from flash to RAM buffer
	Serial.begin(9600);
	Serial.println(buffer);
}
```

On ARM boards, flash and RAM share address space, so `PROGMEM` is typically unnecessary.

## Structs and Pointers

```c
struct Point { int x; int y; };

Point p1 = {2, 3};
Point *ptr = &p1;
int yval = ptr->y;   // 3
ptr->x = 10;         // write via pointer
```

## Casting Pointers (use sparingly)

Casting is sometimes needed for low-level work (registers, byte access). Avoid unsafe casts unless required.

```c
uint16_t val = 0x1234;
uint8_t *b = (uint8_t *)&val; // byte view
// On little-endian AVR/ARM: b[0] = 0x34, b[1] = 0x12
```

## Common Pitfalls

- **Dangling pointers:** Never dereference after the target goes out of scope.
- **Out-of-bounds:** Pointer arithmetic must stay within the object/array.
- **Alignment:** On 32-bit MCUs, misaligned access can slow or fault (rare on AVR, relevant on ARM).
- **Volatile + multi-byte:** Protect multi-byte shared data on AVR with interrupt masking or `ATOMIC_BLOCK`.
- **String literals:** On AVR, accessing large literals without `PROGMEM` can exhaust RAM.

## Minimal Examples

### Iterate an Array with a Pointer

```c
int data[] = {1, 2, 3, 4};

void setup() {
	Serial.begin(9600);
	for (int *p = data; p < data + 4; p++) {
		Serial.println(*p);
	}
}

void loop() {}
```

### Pass by Pointer to Modify a Value

```c
void increment(int *v) { (*v)++; }

void setup() {
	Serial.begin(9600);
	int count = 0;
	increment(&count);
	Serial.println(count); // prints 1
}

void loop() {}
```

### State Table with Function Pointers

```c
typedef void (*StateFn)();

void red()   { /* set outputs */ }
void green() { /* set outputs */ }
void yellow(){ /* set outputs */ }

StateFn states[] = {red, green, yellow};

void loop() {
	static uint8_t idx = 0;
	states[idx]();
	idx = (idx + 1) % 3;
	delay(1000);
}
```

## Best Practices

- Prefer clear types: `uint8_t*`, `int16_t*`, etc., for portability.
- Use `const` to signal read-only data; combine `const` with `PROGMEM` on AVR for large tables.
- Mark shared ISR data `volatile` and protect multi-byte accesses on 8-bit MCUs.
- Initialize pointers; set to `NULL` (or `nullptr` in C++) when unused.
- Avoid casting unless interfacing with hardware or protocols.
- Keep pointer arithmetic simple and bounds-checked.

## Further Reading

- Arduino Reference: pointers and PROGMEM examples
- AVR Libc: `<avr/pgmspace.h>`, `<util/atomic.h>`
- ARM (SAMD/Due) datasheets: memory map and alignment considerations
