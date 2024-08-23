# Lession 4 - Stack and Routines
Routines in Baabnq as kind of like functions or methods in higher-level programming languages. They define encapsulated parts of the program that can be called multiple times from different points in the program.
Baabnq uses one shared stack for both [return addresses](https://en.wikipedia.org/wiki/Return_statement) and routine parameteres. Furthermore, Baabnq doesn't build stack frames as the underlying VM only provides a stack pointer and not a base pointer.

## Calling Routines
```
sub routine;
sub routine;
asm 'brk';

lab routine;
	print 123;
return;
```
The above program defines a routine, that prints 123 and then calls that routine twice.
The "asm" is an [inline assembler statement]() and just halts the program. Halting the program before it reaches the definiton of the routine is important, because otherwise execution would continue and run through the defintion as if it were normal code. There is nothing that inherently distinguishes the routine from the rest of the program, except the fact that it's called by the "sub" command.
A rule of thumb is that routine calls are used globally, while jumps are used locally.
## In and Out Parameters
Parameters, sometimes also called arguments, functions to pass values in and out of a routine.
They are kept on the stack alongside the return address when calling a routine.
```
use 'libs/stack.baabq';

push 1;
push 2;
sub add;
pull __;
print __;

asm 'brk';

lab add;
	sub Stack::Swap; pull _a;
	sub Stack::Swap; pull _b;

	push _a + _b;
	sub Stack::Swap;
	return;
```
In the program above, a routine is defined for adding two values together and is then called with the in-parameters 1 and 2. After the routines finishes, the one out-parameter is pulled from the stack and then output. In the first line of the program, the stack library is imported to provide the Stack::Swap routine, which is used to swap the top two values on the stack. This is necessary because right before the routine is called, the return address it pushed onto the stack last, which buries the in-parameters under it. The return address could also be taken off of the stack by the routine, but this is rather uncommon, due to it's high risk of [variable collision]().


