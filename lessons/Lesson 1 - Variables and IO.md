# Lession 1 - Variables and IO
## Variables
```
put _a = 100;
put _b = 200;
put _a = _b;
```
Variables in Baabnq are always prefixed by an underscore "_" and are always assigned with the "put" command. However, they are not declared, but inferred by the compiler, meaning a variable is created when it's first assigned. Baabnq is a typeless languages, which means that variables are not created with a type and are always 16-bit ( 0 - 65535 ) unsigned integers.
## Output
### Print
```
print 100;
put _a = 200;
print _a;
```
The "print" command takes a variables or a constant and outputs it to stdout as a unsigned decimal integer. So the stdout of the program above would be:
```
100
200
```
### Putchr
```
putchr 10;
```
The "putchr" command also takes a variable or a constant but it outputs the corresponding [unicode character](https://en.wikipedia.org/wiki/Unicode). So the above program would output a line feed.
## Input
```
input _a;
input _b;
```
The "input" command read a decimal unsigned integer from stdin and write it to the specified variable.
## Example
## Next Lession
