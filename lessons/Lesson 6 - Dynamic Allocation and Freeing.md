# Lession 6 - Dynamic Allocation and Freeing
Dynamic memory alloction work exactly like static memory alloction, except that the size of the chunk does not have to be know at compiler-time and that the chunk can be freed again.

## Allocation
```
new 'Hello World!' _sHello;
new 3 _pMem;

put _size = 10;
new _size _pMemBasedOnVariableSize;
```
Allocation of dynamic memory uses the keyword "new" instead of "static".

## Freeing
```
new 'Hello World!' _sHello;
free _sHello;
```
The above program dynamically allocates a chunk containing the string "Hello World!" and then frees it immediately after.


