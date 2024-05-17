
# Documentation

**Python comes with many built-in functions** https://docs.python.org/3/library/functions.html. (Pset 0-4)

`input()` returns a `str`, per https://docs.python.org/3/library/functions.html#input. (Pset 0-1)

`int()` can convert a `str` to an `int` data type, per https://docs.python.org/3/library/functions.html#int. (Pset 0-4)

`float()` can convert a `str` to a `float` data type, per https://docs.python.org/3/library/functions.html#float. (Pset 0-5)

`str` data types come with built-in methods, per https://docs.python.org/3/library/stdtypes.html#string-methods. (Pset 0-1)

An iterable can be **sliced**, per https://docs.python.org/3/library/stdtypes.html#common-sequence-operations. More on [[#`str` slicing (Pset 2-4)]]. 

`dict` comes with built-in methods, per https://docs.python.org/3/library/stdtypes.html#mapping-types-dict. (Pset 3-2)

`list` comes with built-in methods , per https://docs.python.org/3/tutorial/datastructures.html#more-on-lists (Pset 3-5)

You can format an `int` `n` with code like `f"{n:02}"`, per https://docs.python.org/3/library/string.html#format-string-syntax. More on [[#Padding 0s format (Pset 3-5)]].



# Errors

[`ValueError`](https://docs.python.org/3/library/exceptions.html#ValueError) (Pset 3-1) More on [[Week 4 - Exceptions#`ValueError]]
[`ZeroDivisionError`](https://docs.python.org/3/library/exceptions.html#ZeroDivisionError)  (Pset 3-1)
[`EOFError`](https://docs.python.org/3/library/exceptions.html#EOFError) (Pset 3-2). More on [[#EOFError]].
[`KeyError`](https://docs.python.org/3/library/exceptions.html#KeyError) (3-2)


## EOFError

Triggers when an `input()` function terminates without reading any data.

We can recreate this error by pressing `ctrl + d`.

# Tricks

## An emoji is a `char`.  (Pset 0-3)

Which means you can quote (`""`) it like so: `"😭"`, and store it to a variable. 


## Type comparison. (Pset 1-1)

You can compare a `str` `"42"` with the same instead of comparing to an `int` `42`.


## Sequence unpacking (Pset 1-4)

When a `str` has been `.split()`, it returns a `list`, which can then be **assigned to** multiple values **equal to** the length of the `list`.

Example:
```python
str = "1 + 1"
a, b, c = str.split(" ")
print(a,b,c)
```


Execution:
```python
>> python code.py
>> 1 + 1
```


## `str` iteration (Pset 2-1)

You can iterate a `str` object, going through its contents **one at a time**, like so:

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


## `str` slicing (Pset 2-4)

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


## `in` keyword (Pset 2-5)

To be able to check if a data is inside a `list` or `dictionary`, use the `in` keyword. The expression returns a `boolean`. 

Example:
```python
if i in d:
	pass
```


## Handling two or more exceptions (Pset 3-1)

When faced with two or more exceptions, there are two ways to handle the exceptions.

```python
# v1
try:
	pass
except ValueError:
	pass
except ZeroDivisionError:
	pass
```

```python
#v2 
try:
	pass
except (ValueError,ZeroDivisionError):
	pass
```


# Membership Testing (Pset 3-5)

This refers to the use of the `in` and `not in` keyword for any sequence.

Example:
```python
d = {"a":2, "b":3}
print("a" in d) # True

l = [1,2]
print(1 not in l) # False

s = {"yasuo", "yone", "voli"}
print("gwen" in s) # False

str = "warliege"
print("l" not in str) # False
```

# Padding 0s format (Pset 3-5)

If you want to pad zeroes to your text, you can do so, like:
```python
n = 2
print(f"{n:02}") # Output: 02
```

`n` is an `int` object, `0` is the padding (technically, it's a **fill** character), `2` is the **minimum width** of the formatted `str`.

If the **minimum width** is `3`, then the output would be `002`.

