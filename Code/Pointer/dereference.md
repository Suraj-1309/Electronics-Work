# *

Dereferencing is one of the features sepcifically for use with pointers. 

The asterisk `*` is used for this purpose. 

If `p` is a pointer, then `*p` represents the value contained in the address pointed by `p`.

## example
```c++
int *p;       // declare a pointer to an int data type
int i = 5;
int result = 0;
p = &i;       // now 'p' contains the address of 'i'
result = *p;  // 'result' gets the value at the address pointed by 'p'
              // i.e., it gets the value of 'i' which is 5

```