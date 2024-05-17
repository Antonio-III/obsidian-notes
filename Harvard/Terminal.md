# Commands

## code

Example:
	$ code hello.py

Runs "Visual Studio Code" to open a file. Will create the file if file name doesn't exist. Performs this action in the currenct directory.

## python

Example:
	$ python hello.py

Runs "Python", a software that interprets "py" language. Only executes the file if it is in the same directory.

## ls

Lists all files in your current directory.

Example:
	$ ls
## cp

Create a copy of a file.

Example:
	$ cp hello.py goodbye.py
	The contents of `hello.py` are copied to a file named `goodbye.py`.
## mv

Move a file from a directory to another. Can also rename a file. 

Example:
	$ mv hello.py "python codes/"
	This moves `hello.py` to `python codes` folder.

Example:
	$ mv hello.py welcome.py
	This renames `hello.py` to `welcome.py`.
## rm

Delete a file.

Example:
	$ rm welcome.py
## mkdir

Make a folder.

Example:
	$ mkdir "python codes"
## cd

Change directories.

Examples:
	$ cd ..
	$ cd folder/
	It is not required to use a `/`.
## rmdir

Delete a folder.

Example:
	$ rmdir "python codes"
## clear

Aesthetically clear the terminal window.

Example:
	$ clear

### clang / gcc

Compilers for the C language.

Syntax: 
```terminal
$ clang inputFile.c -o outputFileName
```


Example:
```terminal
$clang hello.c
```

This compiles the code from `hello.c` to machine language (assembly) and writes it into a file called `a.out`. `gcc` can be used in place of `clang`. The assembly file cannot be seen as 


### -o

The dash is a flag, and `o` means: "call the output by whatever string that comes after". The default output file name is `a.out`.

Example:
```terminal
$clang -o hello hello.c
```

The output is called `hello`, with no extension name.


## pwd


Stands for: **Print current directory**.

Example:
```terminal
$pwd
```

## cat

Prints the code of the intputted file.

Example:
```C
// In an uncompiled `hello.c` file.
#include <stdio.h>

int main(int argc, char **argv){
    printf("hello, world\n");
    return 0;
}
```

```terminal
// In an uncompiled `hello.c` file.
$cat hello.c
#include <stdio.h>

int main(int argc, char **argv){
    printf("hello, world\n");
    return 0;
}
$
```


## .

Shorthand for **current directory**. This is used when executing a file in the current directory.

Example:
```terminal
$./hello
```

We know that `hello` is a file in the current directory, but just writing `hello` wouldn't be enough to tell the computer to actually run the file; this is because the computer doesn't which where the `hello` file is.

The reason why it doesn't just look at the current directory is because writing `code hello.c` would mean to run a file called `code` in the current directory as well; and this is just inconvenient.

## echo

Just prints whatever is inputted, **except** in special cases. 

One such special case:
```
$./hello
"hello, world"
$echo $?
1
```

An `echo` of 1 means the return value of the previously-executed code is a `fail`, whereas a return of `0` means it's a `success`. This in the case of determining how a compiled `C` program exited.


# Quirks

## To use the previous command,

Press the **up** arrow key.

## Autocompleting

Write enough characters of a file name or whatever and press the **tab** key.

## When prompted,

Press **y** for yes, **n** for no.

## To move to the default directory,

Only enter `cd`.

## To move to the parent directory,

Enter `cd ..`.

`..` is an expression to move up the current directory.