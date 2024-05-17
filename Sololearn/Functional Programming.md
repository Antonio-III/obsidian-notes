When you use functions to make a program, as opposed to classes (like in Python?)

# Pure functions

These are the 'vanilla' functions that returns a data using only their own arguments. It also cannot alter any variable.

Example:
	```def pure_function(x, y):
	temp = x + 2*y
	return temp / (2*x + y)```

Impure function:
	```some_list = \[]
	def impure(arg):
	  some_list.append(arg)```

This is impure because it altered a variable and the variable is outside the function(?)

# Lambda Functions

We can create on-the-fly functions using 'lambda' keyword.

This is used when you want to use a function as an argument of another function.

The syntax is: 'lambda' keyword, argument/s, colon, operation to perform and return.

Example:
	```def my_func(f, arg):
	  return f(arg)
	my_func(lambda x: 2*x*x, 5) # f(5)= 2*5*5 = 50```

You can make a varianle store a lambda function and call the variable with the argument. It will return a value after performing the operation.

Example 2:
	```x=(lambda a: a+6)
	print(x(5)) # 11```

You can also hard-code the argument to the lambda.

Example:
	```x=(lambda a: a+6) (5) # 5 is hard-coded
	print(x) # 11```

Lambdas are called 'anonymous functions'.

Lambdas can only do operations in a single expression, this means it can only perform 1 line of code at most.


# map() function 

Built-in python function. It takes a function as an argument, then an iterable object. So 2 arguments.

Returns a new iterable object that applies the function to each index. The only way to obtain its values is to iterate over it or to convert the map object to a list/tuple.

Example:
	```def add_five(x):
	    return x + 5
	nums = \[11, 22, 33, 44, 55]
	result = map(add_five, nums)
	for i in result: # access elements #1
		print(i)
	result_l=list(result) # access elements #2
	print(result_l)```


Note that the map object is not subscriptable, meaning you can't use \[] to access its indices.

You can also use a lambda function to the map() function.

Example:
	```nums = [11, 22, 33, 44, 55]
	result = list(map(lambda x: x+5, nums))```

# filter() function

Another built-in Python function that takes a function argument and an iterable. It only returns an item if it meets the given condition. 

Example:
	```nums = [11, 22, 33, 44, 55]
	res = list(filter(lambda x: x%2==0, nums))
	print(res) # [22,44]```

If you used a conditional function, it returns a boolean for all the indices. 

Example:
	```nums = [11, 22, 33, 44, 55]
	res = list(map(lambda x: x%2==0, nums))
	print(res) # [False, True, False, True, False]```


The filter object has to be converted to a list/tuple if you want to subscript it.

# Generator objects

More memory efficient than lists/tuples because you don't create all the elements at once.

To make a function a generator, put a 'yield' statement anywhere in the function. When a function has a yield statement, calling it returns a generator object without executing anything in the function-now-generator.

The only way to execute the function is by iterating over it. No matter how many iterations the function-now-generator has, it will only execute the function once. But to generate a lot of numbers, put the 'yield' statement inside a loop.

Example:
	```def countdown():
	  i=5
	while i > 0:
	    yield i
	    i -= 1
	for i in countdown():
	  print(i)```
When you iterate a function-now-generator with a loop, the function will be executed normally until it encounters a yield statement. The inline value after the yield statement is returned as an index of the function-now-generator.

The state of the function-generator is saved. In the next iteration, it will execute from where it left off (1 line of code after the yield statement).

The pausing-the-current-state-and-remembering-where-it-left-off feature of a generator is because when the function encounters a 'yield' statement, it "yields" the value to the caller. This includes the local variable's values and which line of code we've stopped in.

It can be useful if you're using a function like 'next()' to the generator.

Example:
	```def count_up_to(n):
	    i = 1
	    while i <= n:
	        yield i
	        i += 1
	# Using the generator
	counter = count_up_to(3)
	print(next(counter))  # prints 1
	print(next(counter))  # prints 2
	print(next(counter))  # prints 3```

You can see that it saves the previous state (i) of the function when calling it for the second and third time. Now when you perform next() again, it continues on `i+=1` and back to the top of the while loop again.


The 'yield' is different from 'return' because 'return' exits out of the function whereas yield can only exit if there are no more iterables (The loop condition inside fails). 

# Decorators

A function that returns its child function. This makes the variable storing the parent function to become a function itself. The variable becomes the child function. And so you have to call the variable to execute the code.

Example:
	```def decor(func):
	  def wrap():
	    print("============")
	    func()
	    print("============")
	  return wrap
	def print_text():
	  print("Hello world!")
	decorated = decor(print_text)
	decorated()```

Notice how we created a function for executing a print() function. This is because we need to avoid the calling of the print() function. Doing so will execute the function, causing us to pass no function to the 'decor()' function. 

So instead, we pass a reference of the function storing the print() statement (`decor(print_text)`). We pass its reference so as not to call the function and execute its command.

In the 'decor()' function, we create a function inside it. This is just to define the function, of which we will return its reference when calling 'decor'. 

Inside `wrap`, we pass the argument and we're calling it. Note it does not execute the nested function unless the parent function is called.

In this code: `decorated = decor(print_text)`, the variable 'decorated' stores the reference to the function 'wrap'.

We then call 'decorated' to execute the 'wrap' function.

We can call a function to use another function as an argument by using @, proceeded by the function name. The @'ted function will use the below function as its argument, and calling the below function will result in calling the returned function 'wrap'.

What you see:
	```def d(arg):
		def wrap():
		print("============")
		arg()
		print("============")
	return wrap
	@d # we @ the reference of the function 'd'
	def print_text():
		print("Hello world!")
	print_text()```

What it's like:
	```def decor(func):
		def wrap():
		print("============")
		func()
		print("============")
	return wrap
	def print_text():
		print("Hello world!")
	print_text = decor(print_text)
	print_text()```

# Recursion

The recursion occurs when a function calls on itself. This is used in place of loops.

Sometimes using recursion may not be the best when passing large parameters. This is because by design, a process' (program's) stack stores temorary data in its memory as a result of calling a function. The data stores every function parameters, local variables, and the function pointer.

Every time a function is called, its data is pushed onto the stack, when the function exits or gives a return, the stack is removed, freeing any memory used. This is known as 'garbage collecting'.

This means that every recursing function's parameters, variables, and pointers are stored in memory. If the recursion is handling a data that is too big (ie causing a deep recursion), then it will exceed the stack's allocated memory, causing the program to crash.

## Example:
	```def facto(arg):
	    if arg==1:
	        return 1
	    else:
	        return arg*facto(arg-1)
	print(facto(5)) # return 120```

How it works:

We look at this from the inside out, meaning we have to get to the root of the recursion to understand the product of the higher order recursions.

At the innermost recursion, the return is 1. This means that facto(1) returns 1. From the code, we can assume that facto(1) is called inside facto(2). This is because the only case where we get to facto(1) is from 2 (arg) * facto(2-1). 2 being the argument belonging to facto(2). 

This means that facto(2) returns its arg (2) * 1. Facto(2)'s return value is 2. 

Facto(2) is called within facto(3). This means that facto(3) return value is arg (3) * (return value of facto(2), which is 2). The return value of facto(3) is 6. 

Facto(3) is called within facto(4). This means that the return value of facto(4) is arg (4) * 6. 

Facto(4) is called within facto(5). So facto(5)'s return value is 5 * 24, which after evaluation, is expressed as 120.

To make a recursion work, we need to call a function inside itself, but before we do that, we need a condition. This is to make the recursion execute in a finite amount of times. In this case, we call the function, but we decrement its value in the next code. And inside the function itself, we check the value of 'arg'.

This code `if arg==1: return 1`  acts as a 'base case'. The base case acts as an exit condition of the recursion. This finally means we can perform the operation to get out of the innermost recursion. Note that the exit condition doesn't involve calling the function anymore.

## Example 2:
	def is_even(x):
	  if x == 0:
	    return True
	  else:
	    return is_odd(x-1)
	def is_odd(x):
	  return not is_even(x)
	print(is_even(1)) # return False
	print(is_odd(3)) # return False

This is an indirect recursion, which is a function calling another function, which calls the original function.

How it works:

Calling is_even(1):
is_even(1) returns the value of is_odd(1-1). 
is_odd(0) calls is_even(0), and inverses the result. This means in boolean, if is_even(0) returns True, is_odd(0) will necessarily return False. 
is_even(0) returns True.

After reaching our 'base case' (ie no more recursions), we finally have an absolute data to work off of, and we work ourselves from bottom to the top. 

is_odd(0) negates the result of is_even(0). Is_even(0) will always be True (hard-coded), and so is_odd(0) will always be False.

We use the return value of is_odd(0) when calling is_even(1). Since we don't alter the data, is_even(1) will return False.

Calling is_odd(3):
is_odd(3) calls a negated result of is_even(3).
is_even(3) returns is_odd(3-1)
is_odd(2) returns a negated result of is_even(2)
is_even(2) returns is_odd(2-1)
is_odd(1) returns a negated result of is_even(1)
is_even(1) returns is_odd(1-1)
is_odd(0) returns a negated result of is_even(0) 
is_even(0) returns True

From bottom to the top:
is_even(0) - True
is_odd(0)  - False
is_even(1) - False
is_odd(1)  - True
is_even(2) - True
is_odd(2)  - False
is_even(3) - False
is_odd(3)  - True

This means that:
is_odd(3) calls a negated result of is_even(3), TRUE
is_even(3) returns is_odd(3-1), FALSE
is_odd(2) returns a negated result of is_even(2); FALSE
is_even(2) returns is_odd(2-1), TRUE
is_odd(1) returns a negated result of is_even(1); TRUE
is_even(1) returns is_odd(1-1), FALSE
is_odd(0) returns a negated result of is_even(0); FALSE
is_even(0) returns TRUE


# Example 3:
	def fib(x):
		if x == 0 or x == 1:
			return 1
		else: 
			return fib(x-1) + fib(x-2)
	print(fib(4)) # 5

Write this down in a notebook or something to figure it out I'm not writing any more lmao

# \*args and \*\*kwargs

If you don't want to create a positional argument (mandatory data before executing the function), you can use \*args to create any amount of argument or \*\*kwargs to create any amount of keyword argument.

The difference between \*args and \*\*kwargs is that the 'args' variable will be a tuple and 'kwargs' will be a dictionary. 

If you have a tuple, you can only manipulate the given parameters with whatever is allowed to do in a tuple object. Like you can perform sum() on the argument on the 'args' variable.

If you have a dictionary, to obtain the given value, you must write:
`kwargs.get('keyword_argument')`. 

Note that the argument in `kwargs.get` is in string form. This is because we are getting a dictionary key with the name "keyword_argument". In the context of \*\*kwargs, it will always be string. 

There is a way where you can put a defined variable as a dictionary key, but never in the context of \*\*kwargs. 

