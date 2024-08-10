# Lession 5 - Static Allocation
Memory in Baabnq, is always allocated as continuous pieces of memory. These so called chunks of memory, are prefixed by their length which is accessible through negative indexing.
In static allocation, that address and instantiation of the chunk is done at compile-time, meaning that only one specific instance of the chunk is present in memory.
## String Allocation
```
static 'hello' _sHello;

put _i = 0;
lab printLoop;
	put _char <- _sHello + _i;
	put _i = _i + 1;
	putchr _char;
jump printLoop ~ _char != 0;
```
The above program first defines a chunk containing the string "hello" and then iterates over it, printing out the content. Strings are always allocated with a [null-terminator](https://en.wikipedia.org/wiki/Null-terminated_string), which is why the program checks for when the character value it find is zero.

