# &

Referencing is one of the features specifically for use with pointers.

The ampersand operator `&` is used for this purpose. 

If `x` is a variable, then `&x` represents the address of the variable `x`.

## Example
```c++
int *p;       // declare a pointer to an int data type
int i = 5;
int result = 0;
p = &i;       // now 'p' contains the address of 'i'
result = *p;  // 'result' gets the value at the address pointed by 'p'
              // i.e., it gets the value of 'i' which is 5

```