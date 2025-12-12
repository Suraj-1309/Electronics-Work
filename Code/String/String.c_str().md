# String.c_str()

Converts the contents of a String as a C-style, null-terminated string. Note that the gives direct access to the internal String buffer and should be used with care.

In particular, you should never modify the string throught the pointer retured. When you modify the String Object, or when it is destroyed, any pointer, previously returned by c_str() becomes invalid and should not be used any longer.

## Syntax
```c++
myString.c_str();
```

**Return Values** : A pointer to the C-style version of the invoking String.

