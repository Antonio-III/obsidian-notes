
Algorithms is about making efficient automated tasks with constraints. We can't all have fast computers, so a more optimized algorithm will be better for everyone.

# Lecture 2 

## Programming Paradigms

### Compiled vs. Interpreted

![[Compiled vs Interpreted.png]]


When you write a code in Python, you typically have to run a program called "Python" to run that code. What this software does is convert your code into bytecode, which is what the sequence is in the "Interpreted" side.

And once it is converted into bytecode, it is then converted to the sequence in "Compiled", which is in machine code or assembly. And Python does this in runtime (i.e. while the code is executing).

The difference with Python and C is that C needs to be compiled into machine code first, which creates a separate file, and that file can then be executed by the computer's CPU.



### Imperative 

Tell the computer to execute code, line by line. Like Python, and JavaScript. Python falls under the Interpreted and Imperative computer langauge, and C is a Compiled and Imperative of the same.



Example:
```python
print("hello world")
```

### Declarative 

The computer executes what you want, not how you want it. Like SQL.

Example:
```sql
select * from table where id = 2;
```

Whereas an imperative might be:
```python
l = []
for i in table:
	if i == 2:
		l.append(i)
print(l)
```

### Functional

Something close math. Using functions to execute tasks. Like: f( g( k(x) ) ).




## Why learn C?

Learning C enables the user to have an understanding of the underlying design of computers. Like how it understands instructions, and how we need to setup our code in a way that doesn't crash the computer. And along the way, we hopefully learn to be more efficient with our code as well.


## Bell Labs and Unix

One of the founders of C worked for a research institution, Bell Labs. This institution created the transistor, and won a nobel prize. Bell Labs also created an operating system, Unix OS, which Mac OS, and Linux are a derivative of.

### Hello, world!

```C
#include <stdio.h>

int main(int argc, char **argv){
	printf("hello, world!\n");
	return 0
}
```


In C, you should always add a semicolon `;` to denote the end of a statement. Additionally, every function should have a `return` keyword at the end. This is to signal to the computer the function exits,  outputting a `0`, in this case.



## C code needs to be compiled before execution.

### clang / gcc

Compilers for the C language.

Syntax: 
```terminal
$ clang inputFile.c -o outputFileName
```

It can be written in a diffent order as well:
```terminal
$ clang -o outputFileName inputFile.c
```

Example:
```terminal
$clang hello.c -o hello
```



# `#include <stdio.h>

"C doesn't come with batteries". 

We have to include functions we want and remember which library it comes from. `stdio.h` contains the `printf` function.

What we've written in C is a text file, it is not the program, as it cannot run unless it's compiled. **The compiled file is the program.**


# Terminal, and Shell 

A `shell` is a special type of program where it executes OS functions given by the user.


The program that executes the shell is a `Terminal`. Another type of program. A way to run the shell (Terminal) is different from the shell itself.


Example:
```terminal
cp hello.c helloCopy.c
```

The shell executes the command by copying the contents of `hello.c` to the designated file. If the file hasn't been created, the file will be created from this command. If the file exists, it will be overwritten.

## Shell Commands

![[Shell Commands.png]]



# `int main()

The compiler always looks for a function called `main`.  Whatever is inside the main function is the place the program starts. Also notice how we don't call `main`, unlike in Python. The code under `main` is executed by-default.


# Printf, and scanf

```C
#include <stdlib.h>
#include <stdio.h>

int main(int argc, char **argv[]){
	int n;
	double x;

	scanf("%d %lf",&n, &x); 
	printf("n=%d x=%f\n", n, x);

	return EXIT_SUCCESS; // From std lib. Can be changed to EXIT_FAILURE
}

```

`lf` stands for `long-float`, which is `double` the size of a float. This is because floats go into the negatives, while doubles don't.

`EXIT_SUCCESS` (`0`) is from the standard library (`stdlib.h`). Can be changed to `EXIT_FAILURE` (`1`).

The ambersand (`&`) is a pointer.
