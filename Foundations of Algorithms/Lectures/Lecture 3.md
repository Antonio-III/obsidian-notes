
`if` statements. Comparisons between things.

`0` is treated as `false`, a `non-0` is `true`. (might include negatives?). **Numbers are used in blace of booleans.**

`bool` type not widely used; until 2023??


# if/else compared to Python

**Whitespace insensitive**, unlike Python. 

Python needs the right number of indentations, which are whitespaces.

Code blocks denoted by curly brackets `{ }`, or `;`(what?)

`else if` instead of `elif`


Sample program:
```C
#include <stdio.h>

void main(void){
	int n=1;

	if (n < 0){
		printf("it was negative\n");
	}

	if (n==0) printf("it was zero\n");

	else { printf("it was positive\n"); }
	
}
```


Sample Error:
`elseif.c:13:45: error: expected ';' after expression

This is saying: *line `13`, character `45` of `elseif.c` should be a semicolon.*


There is a difference between **warnings** and **errors**. Warnings will not prevent the code from being compiled, it's just that the method of writing the code isn't standard. Errors will prevent the code from being compiled because the compiler encounters text do not follow the rules of C.

`=` is **not** the same as `==`, but it can be used C. However, there will be no comparisons in the cases where this is used.

Sample program:
```C
#include <stdio.h>
#define MAX_CLASS_SIZE 50

int main(int argc, char *argv[]){
	int class_size;
	
	printf("Enter class size: ");
	scanf("%d", &class_size);
	
	if (class_size = MAX_CLASS_SIZE){
		printf("Class is full\n");
		
		}
	else{
		printf("Class is not full\n");
		}
	return 0;
}
```

[[#^4fb75d|What happens in the program?]]

`#define MAX_CLASS_SIZE 50` finds and replaces instances of `MAX_CLASS_SIZE` with `50`. Before the compiler compiles the text file, it runs a `pre-processor` and it replaces instances of the constant (`MAX_CLASS_SIZE`) with the given data (`50`).

If you just use a number `50`, it is unclear what the number means. Writing `MAX_CLASS_SIZE` and assigning it `50` is cleaner to read, and it makes it so that the value isn't hard coded.

These are what are called **constants**. A data that's fixed throughout the program.

As a sign of good programming, always use a **hash desfine** whenever there's an intended constant in the program.

## Scanf syntax

Example: 
`int class_size;
`scanf("%d", &class_size);


Whenever using `scanf`, always put an ambersand (`&`) before the variable name that receives the input from the user.

In the example, whatever is inputted by the user, after formatting, `scanf` will assign it to `class_size`.

## if/else compared to Python

What ends up happening in the program is the computer evaluates `50`.  In C, you can have an assignment expression (`x=50`) be evaluated, whereby the computer evaluates the receiver of the assigment (`x`), after the assigment. 

And in boolean context, any non-zero is considered `True`, which means the code block of this statement executes, outputting `"Class is full"`.  ^4fb75d

However, this is different from the UNIX convention of returning exit statuses where a `0` indicates a successful exit, and `1` does not.


# What is the output of this program?

### 1

```C
#include <stdio.h>

int main(int argc, char *argv[]){
	int x = 3, y = 4, z = 6;
	if (x > 2)
		if (y > 6)
			z = 7;
	else z = 8;
	printf("Z is z=%d",z);
	return 0;
}
```

- [ ] 6
- [ ] 7
- [ ] 8

> [!info]- What is the value of `z`?
> 8. This is because the `else` corresponds to the nearest `if`; and in this case, the nearest `if` is `False` which in turn makes the `else` block to execute, assigning `8` to `z`.


In the way it's been indented, a Python programmer would think it looks like this, leading to an answer of 6:

```Python
if x>2:
	if y>6:
		z=7
else:
	z=8
```


But in actuality, it's intended to be like this:
```Python
if x>2:
	if y>6:
		z=7
	else:
		z=8
```


Viewing the code in this way would make the question clearer:
```C
if (x > 2)  if (y > 6) y = 7;
else z = 8;
```



### 2

```C
#include <stdio.h>

int main(int argc, char *argv[]){
	int x=3,y=4,z=6;

	if (x < y < z) z = z+1;
	if (z > y > x) z = z+2;
	printf("Z is z=%d\n",z);
	return 0;
}
```

- [ ] 6
- [ ] 7
- [ ] 9

> [!info]- What is the value of `z`?
>9


This is because in C, `booleans` are replaced with `integers`. An evaluation of `True` outputs an `integer` `1`, whereas `False` outputs `0`. 

In the code `x < y` yields `1` (`True`), which is then compared to the value of `z` (`6`). The output is `1`, and so the statement executes (`z=z+1`). Next, `z > y` yields `1` and is compared to `x` (`3`). This results in `0`, leading to the statement **not** executing.

Therefore, the value of `z` after two comparisons is `7`.

# When you don't use braces,

Only the first statement that ends with a semicolon `;` is the one part of that control statement.

Example:
```C
#include <stdio.h>
int main(int argc, char *argv[]){
	int x=3,y=4,z=0;

	if (z!= 0) z = z+1; z = z+1;
	if (z > y > x) z = z+2;
	printf("Z is z=%d\n",z);
	return 0;
}
```

The **second** `z = z + 1` is not part of the `if (z != 0)` block. This means that it is an independent statement that will execute regardless of the condition of the block.

# Return Values

![[GNU manual.png]]

In the context of `scanf`, its return value is based on the **number of items read**. 

# Special Casing

Use of `if-else` in a way that should **only apply if there are special scenarios to a given value**. Using multiple `if` statements over individual values is **inefficient** and a **bad practice**.

Example:
	![[Special casing 0.png]]

The `if` block is only specific to an edge case, where our values are modified, otherwise it stays the same. 

Example 2:
	![[Special casing 1.png]]


# Operators in C

![[Operators in C.png]]


Order of operation:
	![[Order of operation.png]]


Sample program:
```C
#include <stdio.h>
#include <stdbool.h>

int main(void){
	int n = 0;
	bool k = true;

	printf("AND! %d\n", n && k);
	printf("OR! %d\n", n || k);
	return 0
}
```

Output:
```terminal
AND! 0
OR! 1
```

In the first `printf` statement, `n && k` is evaluated, which is determining if both values are `True`. This is false, as `0` is evaluated as `False` in boolean context. So it outputs `0`, which is `False` in C.

The second statement outputs `1` because the expression `n || k` requires only one value to be `True` for the expression to evaluate to `True`, which is `1` in C.

**truthy value** - A characteristic of a data if it is evaluated to `True` by the programming language.

The expression `n && k` is evaluating whether **both** values are **truthy values**. 

![[Order of operation pitfalls.png]]

In `&&`, values are evaluated from left to right, and terminate once it encounters a `False` or after it went through the entire expression. 

In `||` it terminates once it encounters a `True` or after evaluating the entire expression.

Only `&&` and `||` have defined order of operations, and it is up to the compiler to determine what order should everything else go. 

Take `a * b + c * d`. We don't know which multiplication operation happens first. 

*"Precedence only tells you what comes after, not what comes before."*


# Types

ASCII - American Information Standard Information Interchange

Way to represent human symbols in the computer. In the computer, letters are electrical and magnetic impulses. Letters are representation on top of these electric impulses.

Just like how `0` and `1` correspond to electrical impulses, groups of `0` and `1` are used to correspond to decimal. And certain groups of `0` and `1` correspond to letters. 

One of the ways we implemented this is ASCII.

ASCII is limited to the English alphabet, and so we have made a bigger system to encompass foreign characters as well.


## `char`acter

Data type to store **one** ASCII symbol.

![[ASCII.png]]


## Fixed-width integers

Much like a clock, where you start go back to 1 after going past 12, integer representation behaves the same. This is because computers don't have infinite memory, so we have to put a limit on how high a number should go.

In C, our *12 o'clock* is 2^31. And the highest number we can get is **(2^32)-1**. This is known as a *32-bit system*. When you have 32 `1`s, in binary, it is **(2^32)-1**.

Much like our *nth places* in Mathematics with base 10, we also have the same system in binary. But the multipliers can only be `0` or `1`.

In base 10, `32` has 2 columns, the *ones* place, and *tens* place. In every column, the number is multiplied by 10, starting from 1. In binary, every column is multiplied by 2 instead. 

A way to find the places of a number in binary is to perform `log2(n)`, where `n` is the number in question (in positive form).  The output for `32` is 5. So in binary, `32` `int` is calculated as `32 * 1 + 16 * 0 + 8 * 0 + 4 * 0 + 2 * 0`, and so represented as `10000`. In a *32-bit system*, it is more like `000...10000`.

We can use more bits than the standard 32/64-bit through C libraries.

## What happens if you go over the allowed bits in integers?


Sample Program:
```C
int main(int argc, char *argv[]){
	int big, bp1, bt2, bp1t2;
	big = 2147483647; 
	bp1 = big + 1;
	bt2 = big * 2;
	bp1t2 = bp1 * 2;
	printf("big=%d, bp1=%d, bt2=%d, bp1t2=%d\n", big, bp1, bt2, bp1t2);
	return 0;
}
```

Output:
```terminal
big=2147483647, bp1=-2147483648, bt2=-2, bp1t2=0
```

