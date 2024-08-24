# Lession 5 - Static Allocation
Memory in Baabnq, is always allocated as continuous pieces of varying length. These so called chunks of memory, are prefixed by their length which is accessible through [negative indexing]().
In static allocation, that address and instantiation of the chunk is done at compile-time, meaning that only the one specific instance of the chunk is present in memory.
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
The above program first statically allocates a chunk containing the string "hello", then iterates over it, printing out the content. 
Strings are always formatted with a [null-terminator](https://en.wikipedia.org/wiki/Null-terminated_string), which is why the program checks for when the character value is zero.

## Lenght Allocation
```
use 'libs/chunk.baabnq';

static 3 _pMem;

put 3 -> _pMem + 0;
put 1 -> _pMem + 1;
put 4 -> _pMem + 2;

push _pMem;
sub Chunk::Print;

```
The above program statically allocates 3 words of memory, then fills them with the first 3 digits of pi, after which it prints the chunk.





