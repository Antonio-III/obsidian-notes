
A feature, a concept, in Python and other programming langauges that let you perform an action again and again. 

Some forms of loops require a condition to run whereas others do not.

Consider this code:
	![[loops_example_0.png]]


Its flowchart will be:
	![[loops_example_0_fc.png]]

How can we improve the code?

# while

One of the keywords to create a loop code block.

Example:
	![[while_example_0.png]]

The syntax  (`True`) after writing `while` is the condition that must be evaluated (`True` or `False`) before running the code block. 

The conditions can be:
	`x!=y
	`salary==0
	`exit!=True
	`n<6

The expressions are similar to how conditionals evaluate conditions.

If the condition of the `while` block is evaluated to `True`, then the code indented beneath it will execute. Once the code block finishes execution, it jumps back to the `while` condition for evaluation. Another evaluation of `True` will run the code block again, a `False` will move past the code block and onto the next similarly-indented code for execution.

If in the case where you've given an initially-`True` condition without a process to manipulate the same, you can **`ctrl+c` to stop a loop**. This is to stop your computer from executing a loop infinite times.

Improved code:
![[while_example_1.png]]

Flowchart:
	![[while_example_1_fc.png]]

In the case of a `while` loop, finishing the execution of the last code in the code block will always let the computer jump to the condition of the `while` loop, to be reevaluated.

## Counting-from-0 convention

In programming, it's usually practiced to start counting from 0~9, instead of 1~10. This is because in programming, the numbers don't have to map onto real life, whereas irl, we have to prove a positive when making statements.

In the improved code:
	![[while_example_2.png]]

You want to set the condition to where you reach up to, but not through, the amount of loops you want to execute. This means that our number can go up to 3, but it will not go through (the code block will not execute once the value is 3) 3.

How else can we improve the code?
	Instead of writing `i=i+1`, in coding in general, it can be written as `i+=1`.

# for

Another type of loop in python where it iterates through "iterable" data types.

These iterable data types tend to have an opening and closing symbol. These can be `str` with its quotation and `list` with its `[]` brackets as well as other datatypes yet to be covered.

## list 

Another datatype that python supports. With this datatype, you are able to store different values within a single variable using this datatype.

This datatype uses square `[]` brackets to signify the start and stop of the list.

## for, list

Example:
	![[for_example_0.png]]

It works by the programmer initializing an arbitrary variable, `i` in this case. Then using the `in` keyword to refer to the individual values in that iterable. And finally, the iterable data type itself.

`in` is used to refer to the data inside the opening and closing symbol. `[]` in this case. So `in [0,1,2]` means "inside the `[]` symbols". This can be understood as: "For every data inside \[0,1,2]".

The data is the highest-order of data, so in the case of `dictionaries`, The data used would be the `keys` pair by default.

Iteration works by assigning the value of `i` to the first value of the iterable. Note that the first value of the `[0,1,2]` iterable is `0`. So in the first iteration, `i` will be assigned `0`. After the assignment is done, it will execute the code block beneath it. 

It is up to the programmer to perform any operations with `i`. In this case, none was used.

Once the code block has finished executing, the interpreter goes back to the `for` loop and check if there are any more values that haven't been iterated through. If there are, `i` will be assigned the next value: `1`, and the code beneath is again executed.


While the program is *correct*, it is not the same a *well-designed*. 

What could be improved in this code?
	Instead of manually specifying the values of the list, Python has a built-in function to create the list within fewer keystrokes.

# range()

A function that takes a positive integer as an **input**, and returns a list from `[0~(input-1)]`. The numbers will go **to but not through**, the input value.

Example:
	![[range_example_0.png]]
Similar to manually creating `[0,1,2]`, `range(3)` returns the same list.

When you want a bigger list, or loop more times,:
	![[range_example_1.png]]
	You can just enter the number of times it will execute. `i` will get assigned **up to but not through** `1000000`.


You will notice in the improved code that while we do assig values to a variable called `i`, we don't ever actually use it. In Python, it is a convention to name the unused variable to a single underscore (`_`).

Improved code:
	![[range_example_2.png]]

This is merely a convention. It signals to other programmers that this variable is not used for the purpose of the `for` loop.

If you look at the code, we are only executing a single operation, namely `print("meow")`. We can further distill the code to a single line by multiplying the string `meow` 3 times. 

Improved code:
	![[range_example_3.png]]

Remember that the polished code from `while` and `for` loops are just as valid and well-designed as the method for `print`. This is just another way to perform the same output.

What matters is its **readability** to others.

# Validating inputs (continue, break)

`continue` and `break` are keywords that can only be used in the use of loops. 

When the interpreter encounters `continue`, it goes back to the top of the loop it's in for evaluation of the next iteration.

On the encounter of `break`, it exits the loop it's inside of.

When either `continue` or `break` is encountered, the operation will be performed on the nearest loop (i.e. the loop they are contained in).

So in the case of nested loops, if a `break` is encountered in the outer loop, it will exit the outer loop. Encountering it in the inner loop will exit the inner loop, but the outer loop goes on.
 
Suppose we want to `print("meow")` `n` times, `n` being an integer-greater-than-1 from the user.

And what if the user keeps entering a negative value? The program will simply never end if we keep hard-coding conditionals.

We can use this code:
![[validating_input_example_0.png]]
	We know that `True` will always evaluate to `True` so it is an infinite loop unless a `break` keyword is encountered. `continue` is used if we want to skip the rest of the code and move on to the next iteration.

We can further improve the code:
	![[validating_input_example_1.png]]
	Keep in mind that when creating an infinite loop, having an exit condition is a **must** to be able to exit the loop.


Finalized code:
	![[validating_input_example_2.png]]


Suppose we have this code,:
	![[validating_input_example_3.png]]
	While we could return `n` from here --remember that the `return` keyword exits out of the function ultimately, even with loops,-- we can also use `break` and have `return n` on the next line of code, outside of the loop. This makes it so that we exit out of the loop, and then the function. Both methods are equally correct, and it's only a matter of readability.
	Remember, only the `return` keyword of the function is the main effect of a function, everything else is a side effect, like this loop.


# Iteration with lists (lists)

It's generally useful in programming languages to have a list of values to be able to work more with data, so Python, too, has a list.

Example of a list:
	![[list_example_0.png]]
	Just like the list of `[0,1,2]`, the data type in the list is instead a `str`. 


How do we print the contents of a list?
	To be able to represent a value inside a list, that is to say you want to "index into the list", we can use square brackets `[]` on the list data type, variable or directly.
	![[list_example_1.png]]
	Lists in Python are zero-indexed. That means the first element is indexed at 0.
	We can further improve the code by using loops so that we don't have to hard-code the contents infinitely in the case of a bigger list.

Improved code:
	![[list_example_2.png]]
	The `student` variable iterates over the contents of `students`, 1 at a time, all the while outputing the current content of that `student` variable. It doesn't matter if the list has 3 elements or 300, it will print out all the contents individually.
	Notice that we use `student` instead of `_`. This is because we do use the variable in the loop. While we can use `_`, it makes it difficult for others to read so we should instead use appropriate names.



# len

A pre-built function in Python that accepts an iterable data type, and returns an `int` value. The function returns `1` if there is an iterated data in the iterable, else `0`.

An alternative solution to the code previously is to instead refer to the elements by their indexed values (`print(students[0])`) rather than iterate over the list and print its contents directly (`print(student)`). 

We can infer that the index values are going to be `0,1,2` in the list but what we're really looking for is the **length** of the list.

Instead of `for student in students:`,:
	![[len_example_0.png]]

Instead of hard-coding numbers in the indexes, we can instead use a variable to represent those numbers. Since the `i`'s value will take on the elements of `[0,1,2]`, we can use `i` to represent the index values of the `students` list.

We can use the `i` variable multiple times in our loop:
	If we want to do some ranking based on their index positions, we can do something like this:
	![[len_example_1.png]]

The reason why we transitioned to use `range` instead of a hard-coded list of integers is because it does not **scale** very well in bigger loops.

# Dictionaries (dict)

A data **structure**, **not type**, that allows us to associate a value with another. All it is is we can associate something with something else.

Dictionaries in the real word contain **words** and **definitions**. In the programming world, these are **keys** and **values**. Or what I would call **key-pair** and **value-pair**.

We initialize the start and end of a dictionary using curly `{}` brackets. The use of curly brackets for dictionaries is unrelated to the use of the same in `f-strings`. Sometimes we run out of symbols to use in the keyword, so the authors just have to reuse some of them.

This is an **iterable** but will iterate over the **keys-pairs** by default.

Suppose we want to keep track of **who** is in what **house**. While we can create another list variable to store houses that correspond to the index values of the `students`, this, too, will **not scale** well in bigger programs.
	![[dict_example_0.png]]


Example:
	![[dict_example_1.png]]
	When we refer to a key-pair, what we're really doing is calling upon its value-pair, only using the key-pair as a method to access its value-pair.
	Unlike lists, we index the dictionary with key-pairs. Specifically, the values of the keys-pair themselves. This can be a `str`, `int`, or `list` as long as it matches the key-pair in the `dict`'s initialization. 
	So this will output `"Gryffindor"`, using the `str` "Hermione" as the key-pair.

All we've done is gone from a list of names to two dimensions, a key associated with a value...
	![[dict_example_2.png]]


To be able to output the key-and-value-pairs in the same line:
	![[dict_example_3.png]]
	We iterate over the key-pairs by default, and we output the same. Then the name of the dictionary (`students`), but we index the `dict` by its key-pair value, `student`. This outputs: `key-pair value-pair`.


# Lists of dictionaries

What if we want to associate multiple things with a student?

How would we write this code?
	![[list_dict_example_0.png]]

We would write it like this:
	![[list_dict_example_1.png]]

## None

A keyword in Python, spelled `None`. This keyword represents an absence of a value. While we can write an empty string `""`, we can better communicate an absence of value by deliberately writing `None`. 

There are cases where using an empty string may be better than `None`, such as for default Python functions where a `None` value will perform the default value.

Example:
	`print("str",end=None)
	Will output:
	`str`
	`$
	But,
	`print("str",end="")
	will output:
	`str$

If you want to explicitly remove the default value for a built-in function, you have to specify an empty value than to assign `None`.

## lists of dictionaries

We have, by design, made 4 separate dictionaries with the same keys but different values.

We can loop through the contents of the list and access the values by hard-coding the key-pairs to print out the value-pairs of the dictionaries.
![[list_dict_example_2.png]]


# Nested Loops

"Abstractions are a simplification of a potentially more complicated idea."

"You can change the implementation details of a function, so long as you maintain the name, parameters, and return value."


So these 2 implementations have the same output:
	![[nested_loops_example_0.png]]
	![[nested_loops_example_1.png]]


Abstraction is when you brute force a problem by "shooting in the dark" to solve it.
	![[nested_loops_example_2.png]]
	We don't have to know how `print_row()` has to work but all we know is that we want to print a value dynamically, in a row orientation. 


What if it were **both rows and columns at the same time**, like a square?
	![[nested_loops_example_3.png]]
	The way `print` works is just like a printer. It goes from **top to bottom**. At the very top, it will print out every column, only then can it move down the row to do the same.
	What's been implemented here is that given a `size` square, we first loop through the `size`, we can abstract this as the **height**. We then create another loop inside the abstracted height. This inner loop, we can abstract as the **width**. Inside the width, we print out a `"#"` with an empty `end`. The empty `end` is to make it so that the next call of the `print` function will output on the same line.
	After the width has been filled, the inner loop stops, and we can start the next outer loop iteration, but we need a way to output a newline outside of the width, so we add a `print` on line 15. It is specifically outside the inner loop because we want to introduce the newline only after the last `"#"` has been printed. This `print` statement is purposely empty as it acts as a newline character only.

The output will look like this:
	```###\n
	###\n
	###\n```
	Remember that having an empty `end` will make it so that your next output will be on the same line.


Abstraction is when you break down a big task into smaller tasks. So instead of 1 big function doing all the task, we create simpler functions to do those tasks, and the big function will embody all of the smaller functions.

# Appendix


## Hints

### `str` iteration

You can iterate a `str` object, iterating through its contents **one at a time**, like so:

```python
s = "camelCase"
for l in s:
	print(l, end="")
```

Execution:
```python
>> python code.py
>> camelCase>>
```


### `str` slicing

Per https://docs.python.org/3/library/stdtypes.html#common-sequence-operations

You can separate the elements of an iterable like `str` and `list`s to only contain from `i` element onwards, just before `j`, with intervals `k`. All these variables represent an `int` data type, specifically, the **index positions of the iterable**.  


Example:
```python
s="spirits"
print(s[2:7:2])
```

Execution:
```python
>> python code.py
>> iis
```
### `in` keyword

To be able to check if a data is inside a `list` or `dictionary`, use the `in` keyword. Returns a `boolean`. 

Example:
	`if i in d:
		`pass


