
Code is text. So we need some program that can create texts, like a text editor. 

# Command Line Interface

An interface to the underlying computer whether it's your computer or a server whose data is stored in the cloud.

A **cli** is used to execute programs instead of clicking apps. Used in the programming world?

dollar sign ($) - Indicate where your next command should be put in

# Interpreter

## Why do we write "python" to execute a file?
![[interpreter.png]]

When you write code in any programming language, to be able to execute it, you need a program to convert the text to machine code i.e. turn it to binary.

You need something to "interpret" the code-- top to bottom, left to right.

This is because computers don't understand the text written, so the interpeter converts it to binary to execute the commands written in the file.

Python is not only a language but also a program, which is the Python Interpreter.

# Functions, Arguments, Side effects
## Functions

An action that lets you do something in the program.

Most languages come with predetermined set of actions or verbs (functions) that the language knows how to do for you. 

`print()` is one of these predetermined functions.

## Arguments

Input to a function that influences its (the function's) behavior.

The function `print` cannot know what you want to print to the screen, so the authors designed the `print()` to take an input within its parentheses, and it will print the given arguments.


## Side Effects

Any effect/output other than returning a value to its invoker/caller.

Example:
	What is a program with only `print()` doing on the terminal screen?
	A: It outputs whatever is in its arguments.


Side effects can be visual, audio, etc.. In this case, the side effect is displaying something on the terminal.

Functions have 2 "kinds" of output, 1) its return value. 2) side effect.

# Bugs

A mistake in any program, be it from human error or otherwise.

If there is a bug in the program, it will not run at all, or it will not give you the result you want.


# Return Values and Variables

## Return Value

Think of a function as a person. An `input()` function is like a person you tell "Hey, can you get an input from the user", and the function receives an input, but not necessarily *returned* to the programmer.

Wouldn't it be nice to have that function return the name to you? (it's already done by default in the case of `input()`)

We would also need metaphorically, a piece of paper to write what the return value is of that function. In that case, we would use a variable to store the return value.


## Variables

In come variables. The metaphorical paper is represented as the computer's memory. Anything stored in a variable means that somewhere in memory, a container (memory address?) stores a value.

When assigning a value in Python, you're creating a reference (the variable on the left side) to the object representing a value (on the right side), rather than making a copy of the value.
### Why do you write 'name' instead of just 'x'?
![[variable_naming.png]]

Because you have a keyboard in front of you, which means we can write something more descriptive of what the variable stores.

### Assignment operator

Represented as `=`.

The data on the left will store the data on the right.

In the picture's context, we will assign the return value of the function `input()` to the `name` variable.  


# Comments and Pseudocode

## Comments

Programming languages support having notes in your code for the purpose of the user to look at.

In Python, the `#` symbol is used to signal a comment.


## Pseudocode

Express your thoughts argorithmically, written somewhere, perhaps as a comment.


# Multiple Function Arguments

Some predetermined functions can have multiple arguments. `print()` is one of them.
If you separate the arguments to a function using `,`, you can pass more than a single argument.

# Parameters, Named, Positional Parameters

Per https://docs.python.org/3/library/functions.html#print,

`print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)

## sep

An optional parameter in the `print` function that acts as a separator between 2 printed values. If only 1 `str` object is to be printed, this will not take any effect. But if you print 2 `str` values for instance, it will separate `str 1` and `str 2` with a blank space in between.


## Parameters

Outside the context of calling the function, the things you **can pass to a function**, and what they're called, are **parameters**.

When you **call the function**, the values you put in the parentheses, those inputs, are called **arguments**.


## Positional Parameters

In this context of `print()`, whatever argument you passed first will be printed first and the second argument will be printed second.


## Named Paramaters

In `print()`, there are named arguments called `sep` and `end`. Passing an argument for these parameters is optional because they have their default values (by default). 

And if you want to assign a value to these parameters, you have to assign the variables `sep` and `end` with values you wish to use as separators, and trailing string, respectively.


# Escaping Characters

If you wanted to `print()` a quotation mark, you can use a backslash (`\`) to be able to print a quotation mark. This is if you use `""` to represent the string you want to print.

Example:
	`print("Hi, my name is \"Eminem\"")

# f-strings

A new feature of Python to represent a variable while being inside the string that you want to print.

Example:
	```name="Antonio"
	print(f"Hello, {name}")
	output: Hello, Antonio```


# String methods

Per https://docs.python.org/3/library/stdtypes.html#string-methods,

the function `strip()` used in this context is a method. 

![[string_methods.png]]

In the documentation, there are a lot of functions for string data types in Python. You can access these functions by using a string or its container (variable), then a period `.`, then the name of the function.

In the picture, we want to **remember** that we've executed a function, so we want to store the return value of the `.strip()` method, so we store it in a container.


## Method Chaining

![[string_methods_chaining.png]]

We can chain our methods together like in the picture. 

Well what's going on here? 

Look at the very left of the chain (line 5), the return value of `name.strip()` would be then applied another method, `.title()`, and the return value after applying `.title()` would then be stored to `name`.

We can take this one step further, and put them all in one line:

![[string_methods_chaining_2.png]]

This results in the code being cleaner.


## Methods

A method is a built-in function to a type of data. 

Example:
	`str.capitalize()
	`.capitalize()` is the method.


# Style

Whether or not writing the code in multiple lines is better or worse, practice adapting to whatever is required.

And be consistent when using either single `'` or double `"` quotes. In Python documentation, every string data type is wrapped in single quotes.

**Prioritize simplicity and readability.**


# Split Method

Another method for strings in Python that splits a string into substrings. In the context of `name`, if the user inputs Antonio Intal, then that means we can split the string in to just 
`Antonio`, and `Intal`, separately.

![[split_method.png]]

There will be 2 return values, and we can store the separated strings into two variables, `first` and `last`.


# Int and Operators

## Integer 

Any number, positive or negative, that has **no decimal point**.

## Operators

The math symbols `+ - * / % **`
`%` is the remainder **after a division operation**.
`**` raises the base (left) to the power of (right). Example: 4 ** 2.


## Interactive Mode

Type `python` in the terminal.
![[interactive_mode.png]]

You can write 1 line of code or 1 operation, and it executes the the code after pressing `Enter`. 

You can chain these codes like declaring a variable on the first line, then printing the contents of the variable on the second.


## Integer

Why did this code not work?
![[concatenating_numbers_as_strings.png]]

Anything that comes from a keyboard is always going to be a `str` by default, in the context of how the `input()` function works.


# Type conversion

We can change a data type of a thing to another. In the picture, we will change the data type stored in `x` from a `str` to an `int`.

This is done by using the `int()` function. It takes a single input, and it converts its input to an integer.

## Nested Function

Suppose this code: `x=int(input("What's x? ))

The return value of the inner function will be then used as the argument for the outer function. Just like in math, you can do 5( 6 ( 7/( 8+9 ) ) ).=, whereby the innermost parenthesis is evaluated first, then proceed to go outwards.


# Floating Point Values

Any number with a decimal point, the data type is called `float`.

Think of float as the in-between integers, essentially "floating" instead of just one whole step.

Suppose this code:
![[floating_point_values.png]]

## `round` function

What if we want to just round the answer to the nearest integer?

Per https://docs.python.org/3/library/functions.html#round,

in the documentation, there exists a `round()` function.

`round(number[,ndigits])

When you see a square bracket `[]`, in tech, it is something optional. If you want to specify the number of digits you want the `round` function to round to, you can specify it by adding a comma `,` and that number.

A `0` will round to the nearest `ones` place. This is also the default value.

A positive `n` will round to the nearest `n`th place **after** the decimal point. An argument of `4` will round to the nearest `ten-thousandths` place (4 digits after the decimal point).

A negative `n` will round to the nearest `n`th place **before** the `ones` place. An argument `-1` will round to the `tens` place; 1 digit before the `ones` place. 

# Numeric Formatting

What if you want the output to have a separator, like a comma `,` after every 3 digits from right to left?

![[numeric_formatting.png]]

We can use something like: `print(f"{z:,}")

We essentially added a `:,` after `z` after formatting the string.


# Division

![[float_formatting.png]]

In the documentation, this is how you can specify how many numbers after the decimal to be shown.

`v:.nf` `v` for any numeric data type, `n` for any number, `f` for `float`. Works the same as the `round()` function.


# Defining Functions

Create your own function by using the `def` keyword.

What does this code (line 1~2) mean?
![[defining_functions.png]]

It means Python will now treat anything indented as the definition of the function `hello()`.

The empty parenthesis means that the function currently doesn't take any inputs.

The colon means: "There will be some indentation here". Anything indented after the colon will be part of the definition of `hello()`, unless escaped by an unindentation.

Since we've defined `hello()` (lines 1~2) before we call it, it will exist by the time we use it (line 6).

## Add a parameter to a function

![[add_parameter_to_function.png]]

What's going on here?

Lines 1~2: We define a function `hello`. This time, it has a parameter `to`. 
Then it prints "hello" and the value of `to`, which is whatever is input when calling `hello()`.

Line 5: Takes an input from the user and assign it to `name`.

Line 6: Call the `hello()` function and use the variable `name` as the argument to the function.

Summary:
The interpreter **copies** the value of `name` and puts it into `to`. In the function definition, we plug in the value of `to` to the `print()` statement.


## Default Values

Recall in the documentation of `print()` it had a default value for `sep` and `end`.

Our custom functions can have this too.

Example:
	![[default_values_to_functions.png]]



## Point of defining functions

So you don't have to repeat yourself again and again.

So you don't have to keep reinventing the wheel, so to say.


## What if you put the function definition after you call it?

The Python interpreter will take the code in its face-value and raise an error that the function has not been defined. 

The interpreter wants you to define the function before you call it.

This implies that you have to write the functions at the top of the file.

But this is writing code in reverse! Instead of writing top-to-bottom, I have to write the functions above the code that I first started writing on!


## Where to put functions?

You do indeed put the main part of your code at the top of the file, but you do this by putting it inside the `main()` function (a custom function). 

The word `main` is just a convention.

![[main_function.png]]

I've called python to run the file but nothing happens!

You have defined the functions `main` and `hello` but it doesn't mean that you have used or called them!

You've used `hello()` but you didn't tell Python to use `main()`.


# Scope

The concept of a variable only existing in the context of where you defined it.

Example:
Why does this code not work?	
![[scope.png]]

If you have multiple functions and you (a function) use a variable that's defined in another function, will raise an error because that variable hasn't been assigned in the other function's definition.


# Return values

Just like how the `input()` returns a string of what the user typed in, how the `int()`, `float()`, and string methods returns a value, we can also make our custom functions have it.

![[return_values.png]]

It's not enough to just write `n*n`, we have to somehow return the value of `n*n` to whoever called it. 

In this context, we have called it as our argument to the `*objects` parameter of `print()` and the parameter will be the one to remember the value.


