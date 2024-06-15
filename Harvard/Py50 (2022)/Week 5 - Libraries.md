
Files of code that have been written that you can use in your own program. Python has this feature. Having libraries is an ability to share code with others. It does so by way of 
**modules**. 


# Modules

A Python file with at least 1 or more functions, and other features as well. The purpose of modules is to encourage code reusability, so programmers don't have to "reinvent the wheel". 

If you find yourself copy-pasting functions from an old project, you can put that function into a library that you can **load into** your programs from now on.

These modules give functions that you don't have access to by default, unlike `print()` and `input()`.  These default functions are **built-in** to Python. In the case of modules, these functions are tucked away, so you have to be explicit when loading them into the computer's memory.


# `random.py

By installing the Python interpreter, you will have other modules installed as well. One of these modules is called: `random.py`. And while you can "reinvent the wheel" to achieve randomness, it's better to use someone else's code to waste less time.

Documentation:
	https://docs.python.org/3/library/random.html



# `import

Keyword to import contents from some module into your program. This enables you to use `functions` from that module in your program.

## `random.choice(seq)

A function from the `random` module, copy-pasted from the [documentation](https://docs.python.org/3/library/random.html). When you see `seq`, it refers to something that is a **list** or **list-like**.
