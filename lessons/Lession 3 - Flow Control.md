# Lession 3 - Flow Control
Flow Control in Baabnq is done with label, which define specific points in a program and jumps to those labels. 
```
lab loop;
jump loop;
```
Consider the example above. A label called "loop" is defined and is then jumped to, which makes the program loop infinitely. Jumps can also be performed based on a condition to form [for loops](https://en.wikipedia.org/wiki/For_loop):
```
put _i = 0;
lab loop;
	put _i = _i + 1;
jump loop ~ _i < 10;
```
A Tilde "~" is used to attach a condition to a jump statement. 

## Examples
## Next Lession