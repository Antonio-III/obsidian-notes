
**Exceptions** in Python and other programming languages refer to problems in your code.

This week shows us how to handle these errors.

Suppose this code:
```python
# 4.1
print("hello, world)
```


Execution:
```python
# 4.1
>> python code.py
>> SyntaxError: unterminated string literal (detected at line 1)
```


Let's try to understand the error. Generally, *unterminated* means we've started something but didn't stop it. *String* is data type for a sequence of text. *Literal* means something we've written that doesn't refer to any keywords or existing variables.

What this means is that we didn't stop the `str` that we typed i.e. there is no closing `"`.


# `SyntaxError

A problem on the programmer's side relating to the code written not being in the proper arrangement of keywords, etc.

"These errors must just be fixed."


There are other errors like `RuntimeError` that happen while your code is running. And it's up to the user to write code defensively to handle when these errors happen.


# `ValueError

`ValueError` refers to certain tasks not being performed because it violates Python or function rules, therefore a value cannot be evaluated.

Per the documentation:
	*Raised when an operation or function receives an argument that has the right type but an inappropriate value, and the situation is not described by a more precise exception such as [`IndexError`](https://docs.python.org/3/library/exceptions.html#IndexError "IndexError")*.


Example:
```python
# Case 1
x,y = [1]

# Case 2
int("cat")
```

This is because the underlying mechanisms of functions, and Python features, make it so performing a task like variable assignment or converting a `str` to an `int`, is not possible. 

Case 1:
	List `[1]` is attempted to be unpacked by variables `x` and `y`. List unpacking works by referencing the individual contents of the list to the variables that are signaled to unpack. A comma (`,`) is used to signal a list unpacking. Having too many or too little variables to perform the list unpacking will raise a `ValueError`. In this case, `y` is a variable that cannot be assigned a value from list unpacking, which raises a `ValueError`.


Case 2:
	`str` `"cat"` is used as an argument to the `int()` function. This is not possible since alphabets and numbers are treated differently by the `int()` function. Passing a non-number to `int()` will raise a `ValueError`. This is because it doesn't make sense to turn `"cat"` to an integer.



Suppose this program:
```python
# 4.2
x = int( input("What's x? ") )
print(f"x is {x}")
```


Execution:
```python
# 4.2
>> python code.py
>> What's x? 50
>> x is 50
```

What could go wrong in this program?
	If we typed in something that cannot be turned to an integer, an error will raise.

A good way to test your code it to think about **corner cases**. These are niche cases where it might not happen in most use cases, but it might just be able to raise an error to your program. 

So in our code, there might be a time where we input a number, but it's a non-integer, e.g. a `float`.  In the video, Malan, writes in `cat`, which cannot be converted to an `int`.

So we get this error:
	`ValueError: Invalid literal for int() with base 10: 'cat'

In Python and a lot programming languages, the errors are written for programmers.

So let's understand the error:
	`Invalid literal` means something that we typed in i.e. our input, and it is considered invalid for `int()` that works in base 10. Base 10 being the decimal system that consists of numbers from 0~9.
	Basically passing `"cat"` to `int()` caused the error.

From now on, we should write our code with error handling in mind.

# `try`, `except`

We can use `try` to attempt to execute a code block, and we can check if an error occurs based on whether or not this code block has been fully executed.

This is like saying: "Lets `try` this code, `except` when this error happens, then lets exit `try`, and execute another code." 


Improved code:
```python
# 4.3
try:
	x = int(input("What's x? "))
	print(f"x is {x}")
except ValueError:
	print("x is not an integer")
```


The name of errors are case-sensitive, so it has to be capitalized to refer to the error themselves.


## Q n A

What if we don't know the names of the errors in advance?
	There is a way in Python where you can have a catch-all to all errors by omitting the name of the error, but this hides bugs in your code because you can't know for sure what error is happening, therefore you won't be able to handle it correctly, so this is bad practice. So a better practice would be to figure out what kind of errors could happen and include them explicitly. Sometimes the documentation does show what error could go wrong, sometimes it doesn't.

Tl;dr: Refer to documentation to see errors, if not there, figure it out instead.


# `NameError

`NameError` refers to an error where you're "doing something with the a variable that you shouldn't".

In terms of best practices, the code above doesn't follow them. When using `try`, we should only include the lines of code that are capable of raising an error. 

You will notice that calling the `print()` function will never raise the error so let's move it somewhere.

Updated code:
```python 
# 4.4
try:
	x = int( input("What's x? ") 
except ValueError:
	print("x is not an integer") 
print(f"x is {x}")
```

Execution:
```python
# 4.4
>> python code.py
>> What's x? cat
>> x is not an integer
>> NameError: x is not defined
```


Why is `x` not defined on line 5 despite being intended to be defined on line 2?
	Scope issue is not the problem here, the `x` is still a global variable. The problem lies on the fact that `int()` cannot give a return value when given with something that doesn't look like an integer, therefore causing `x` to have no data on its right side to refer to.


# `else` 

This keyword also exists in the `try-except` feature of Python. What `else` does is that it executes its code block if **`try` works**. 

Think of it as: "*`Try` this, `except` if something goes wrong..., `else` nothing goes wrong, do this.*" 


Example:
```python
# 4.5
try:
	x = int( input("What's x? ") )
except ValueError:
	print("x is not an integer")
else:
	print(f"x is {x}")
```


Keep in mind that in the case of errors, it's best to not evaluate `x` like so `{x}`, in the `except` block, because this variable isn't pointing to any value, therefore it couldn't have been defined.


# Reprompting, `break

We can further refine our code from exiting after raising an error, by inducing a loop that reprompts the user again such that it only exits the loop once an error is no longer being raised.

Improved code:
```Python
# 4.6 v1
while True:
	try:
		x = int( input("What's x?") )
	except ValueError:
		print("x is not an integer")
	else:
		break

print(f"x is {x}")
```

Execution:
```Python
# 4.6 
# Case 1
>> python code.py
>> What's x? 50
>> x is 50

# Case 2
>> python code.py
>> What's x? cat
>> x is not an integer
>> What's x? dog
>> x is not an integer
>> What's x? bird
>> x is not an integer
>> What's x? 50
>> x is 50
```

We can "further improve" our code by putting `break` after the assignment of `x`.

Improved code:
```Python
# 4.6 v2
while True:
	try:
		x = int( input("What's x? ") )
		break
	except ValueError:
		print("x is not an integer")

print("x is {x}")
```

This makes it so that we exit the loop if `x` has been successfully assigned to.


Execution:
```python
# 4.6
>> python code.py
>> What's x? 50
>> x is 50
```

Now which of these 2 is better?
	You can go either way. If you want to shorten the code, `v1` is fine. If you want to minimize the amount of code you end up executing, `v2` is fine as well.


# `get_int()

We can further refine our code by turning it into a function if we ever want to reuse it in the future.

Code:
```python
# 4.7 v1
def main():
	x = get_int()
	print(f"x is {x}")


def get_int():
	while True:
		try:
			x = int( input("What's x? ") )
		except ValueError:
			print("x is not an integer")
		else:
			break
	
	return x

main()
```

Execution:
```python
# 4.7
>> python code.py
>> What's x? cat
>> x is not an integer
>> What's x? bird
>> x is not an integer
>> What's x? 50
>> x is 50
```


We can shorten the code by replacing `break` with `return`. This is because `return` is a stronger `break` whereby it ultimately exits out of the function by returning a value to the caller, so it exits out of any loop as well.

Improved code:
```python
# 4.7 v2
def get_int():
	while True:
		try:
			x = int( input("What's x? ") )
		except ValueError:
			print("x is not an integer")
		else:
			return x
```

We can further shorten the code by not defining the `x` variable, and instead use its  intended value directly to `return`. 

Improved code:
```python
# 4.7 v3
def get_int():
	while True:
		try:
			return int(input("What's x? ") )
		except ValueError:
			print("x is not an integer")
```


At the end of the day, you **must** come up with a good reason as to why you've consciously written the code in this way instead of just "*it worked*". A good reason will come with time and practice.


# `pass

If you want to handle an exception, but decide to do nothing about it, we can use `pass`.

We're saying we want to catch the error, but we want to ignore it.

This works with executing functions, statements, conditionals, and loops. Basically if you want to define any of these but leave the indented code block empty, use `pass`.

Improved code:
```python
# 4.8
def get_int():
	while True:
		try:
			return int( input("What's x? ") )
		except ValueError:
			pass
```

Execution:
```python
# 4.8
>> python code.py
>> What's x? cat
>> What's x? dog
>> What's x?
```

You can argue it's made the code worse or better. This is just another mechanism to handle errors.

## Q n A

### Why the indentations?

The designers of Python might've got tired of seeing ugly code from C, Java, etc., so indentation comes with the syntax of the language to refer to "*this code is associated with this code*". This is to say that when you write a code in Python, and the code below it is indented, the indented code is associated with that first line of code. 

The indented code is only executed when the first line of code told the computer to do so.


### Can the caller know about the errors?

If we handle the error with `try-except`, no. The error is not going to know anything about it. This is the point of handling it, so that `main()` or other callers cannot know about the error.

### Can we use `str.isnumeric()` to filter out non-integers? 

We could use a conditional like `.isnumeric()` and pass it to the `int()` function if so, but the *Pythonic* way to do things is to use the `try-except` statements.


# Function Arguments

It would be nice if the prompt of `"What's x? "` isn't hard-coded like it is now.  Because what if the `main()` function calls its variable `y` or `z`? 

So we can further refine the code by adding a `prompt` as a parameter to `get_int()`.

Improved code:
```python
# 4.9
def main():
	x = get_int("What's x? ")
	print(f"x is {x}")

def get_int(prompt):
	while True:
		try:
			return int( input(prompt) )
		except ValueError:
			pass
```


Execution:
```python
# 4.9
# Case 1
>> python code.py
>> What's x? 50
>> x is 50

# Case 2
>> python code.py
>> What's x? cat
>> What's x? dog
>> What's x? 50
>> x is 50
```

# `raise

We can also raise exceptions ourselves, but more on that, another time.


# Shorts
## Debugging

### `print()

One of the ways to simply check the value of a variable to see what it's currently storing. But it eventually loses favor in debugging once you start writing bigger programs.


### breakpoint

A mechanic from an IDE (like VS Code) that lets the programmer pick a line/s of code to pause the program in, once they've ran a debugger.


#### Setting a breakpoint
You can set a breakpoint by hovering your cursor on the space just before the line of your code.

Example:
	![[debugging_ex_0.png]]
	Notice the 🔴 where the 👆 is. **Clicking on it will set a breakpoint**.

What this indicates to VS Code is to pause your program **before** getting to line 12.

#### Run the debugging

Clicking on an icon that looks like: 🪲▶️, will run the program and debugger.

When you've set a **breakpoint**, you'll notice a yellow line of code:
	![[debugging_ex_1.png]]
	A yellow line indicates a code has not yet executed, and will only execute when the user is ready to proceed to the "next step" (next line of code).

You'll notice a menu of icons upon running the debugger:
	![[debugging_ex_2.png]]
	From left to right, **the first 3**: 
	**Continue** - Exits the debugger, and the program runs until it ends.
	**Step Over** - Executes the next line of code, but it doesn't go **into** the definition of a function, if any.
	**Step Into** - Go inside the definition of any functions in the next line.
