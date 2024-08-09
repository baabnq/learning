# Learning

For download and setup refer to [the development kit](https://github.com/baabnq/kit).

### Quickstart - Hello World
```
use 'libs/string.baabnq';
static 'Hello, World!' _sHello;
push _sHello;
sub String::Print;
```
Save it under hello.baabnq, then compile and run with:
```
python compi.py -i hello.baabnq
python vm.py -f build.s1
```
Compilation always has to take place in the directory where the compiler is located, so that it can correctly resolve and link dependencies.

