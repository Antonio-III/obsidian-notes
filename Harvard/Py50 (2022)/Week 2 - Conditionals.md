
Ability to ask and answer a question of whether you can execute a line of code without executing other codes of the same condition.

Like a proverbial crossroad or fork.

# Conditionals
## Symbols

![[conditional_signs.png.png]]

From top to bottom: 
`>` greater than
`>=` greater than or equal to
`<` less than
`<=` less than or equal to
`==` equal to
`!=` not equal to

A single equal sign represents "assignment". A double equal sign represents "equal to".

Assignment - copying the data from the right to the left.

The exclamation point (`!`) represents "NOT".

In this context, `!=` represents "NOT equal to".

# if

To use the symbols, use the keyword `if`. 

Example:
	![[if_example.png.png]]


The evaluation of the statement (`x<y`) will determine whether or not to execute the code inside the code block. 

An evaluation of `True` will execute it, `False` will not.

Notice how the code below the `if` block is indented. This is to tell Python to only execute the code below if the evaluation of the statement (`x<y`) is `True`.

## In this code,
	![[compare_py.png.png]]

What just happened?
	![[if_flowchart.png.png]]

What about this code is not well-designed?
	No matter where you go, you're always asking 3 questions regardless of the evaluation result. Ideally, we would already know the relationship between `x` and `y` after evaluating a `True` answer in one of these questions, so that we don't have to ask any more questions.

# elif

Similar to `if`s, but `elif`'s code will only execcute if the nearest `if` is `False`, and the `elif` evaluation is `True`. If at least one `elif` is True, the code executes its code block, leaving remaining `elif`s unevaluated.

This keyword can be used in place of the second and beyond of mutually exclusive`if` statements. Mutually exclusive meaning: a situation where 2 statements cannot be`True` at the same time, only 1 of them can be, at a time.

Example:
	![[elif_example.png.png]]

Flowchart:
	![[elif_flowchart.png.png]]

How does `elif` help us?

This is just foundation for writing better code long-term. And we would probably notice a speed increase when we're writing bigger programs.

What else could be done to improve this?

# else

Execute the code in the `else` block if and only if its nearest `if` and `elif`s are `False`.

Since the scenario is mutually exclusive, it is the case that when we've ruled out all but one condition, the final one must be `True`.

Example:
	![[else_example.png.png]]

Flowchart:
	![[else_flowchart.png.png]]


# or

Execute the code below the `if` block if at least 1 of the 2 or more conditions is True.

Example:
	![[or_example.png.png]]

Flowchart:
	![[or_flowchart.png.png]]

In this new scenario, what can we do to improve the readability of this code?
	Instead of asking `<` or `>`, we can just use `!=`, since we're evaluating whether or not `x` is equal to `y`.
	![[not_equal_example.pmg.png]]

Flowchart:
	![[not_equal_flowchart.png.png]]

# and

If the the conditions on the left and right of `and` are `True`, the code block will execute.

Example:
	![[and_example_0.png.png]]

What can we improve in the code?

# Chaining Comparison Operators

We can remove the use of `and`, and do something like this:
	![[and_example_1.png.png]]

What else can we do to improve the code?
	Instead of checking for the upper bounds and lower bounds of the `score`, we can instead ask if the score is `>=` the lower bound of the bracket. Since the code is executed line by line, if the `score` fails the first `if` but it is `>=`  the lower bound of the second (80), we can conclude that the `score` is a B.
	![[and_example_2.png.png]]

# Modulo 

The modulo, represented by `%`, returns the remainder when a number on its left side is divided by the right.  

Example:
	`print(2%10)`
	Output: 2
	`print(3%3)`
	Output: 0

Example:
	![[modulo_example.png.png]]

# Boolean

Whereas the data types: `int`and `str` contain any combination of numbers and letters, `bool` can only contain `True` or `False`.

This can be useful for using functions as conditionals by making the function return either `True` or `False`.

Example:
	![[bool_example.png]]
	```
	15 main()
	```

We can return the same if we use `if` on a variable.

Example:
```
	x=0
	if x:
		return True
	else:
		return False
	Output: False
```


If a variable or object points to either `0`, an empty quotation `""`, `False`, or in general an empty data type, using an `if` statement will return a `bool` evaluation.


# Pythonic Expressions

Pythonic expressions are practices that "are just the way you do things in Python". These relate to features that may only be in Python exclusively.

Example:
	We can condense a 4-line `if-else` conditional expression to a single line. 
	![[pythonic_example_0.png]]

Note:
	This can only be done if there is an `if-else` scenario where only 1 operation is to be performed in both cases.

In the code in its current context, it can be refined further. The expression `n%2==0` has an answer of `True` or `False` in of itself. Therefore, having an `if-else` in this case is redundant.

Improved code:
	![[pythonic_example_1.png]]


# match

Allows you to use `if-else` but more compact. This is similar to the `switch` keyword in other programming languages.

Suppose we have this code:
	![[match_example_0.png]]

How do we make this less verbose?

It turns out a keyword called `match` can do the same thing. 
	![[match_example_1.png]]

Instead of writing `if name=="Harry"`, we can instead just write `case "Harry"`.

We are essentially "matching" an object with the values of the `case`s. 

How do we deal with names that don't have a case?
	![[match_example_2.png]]

The single underscore **in this context** is meant to say "any case that hasn't been handled", similar to the `else` statement.

But the code in its current form seems to have regressed.

**How can we write the equivalent of the `or` keyword using `match`?**
	We can use the `|` keyword.
	![[match_example_3.png]]


## Appendix

This is just another tool in your toolbox to solve problems. It's equally as correct to use the `if-else` to solve the same problem. 

You can argue that it has lessen the code, therefore it looks cleaner, it has less duplication of the equal sign and the variable name, but what you do at the end of the day is up to you, the programmer, to assess how the code is "usable" to other programmers.


