# 190 - File handling 

Syntax: 
	`file_handler=open(filename,mode)
	`file_handler.close()
	file_handler - variable name
	filename - target file name
	mode - to read (r), write (w), or append (a). string type
	Default `mode` is `r` if unspecified

Syntax 2:
	`with open(filename,mode) as variable_name:
		`statement 1
		`statement 2
	Not required to write close method

## Reading text files

Methods:
	`read()
	`readline()
	`readlines()

Syntax of `.read()`:
	file_object.read(size)
	Size argument optional. If given, the method returns strings up to `size`-1 characters in the file.
	Else, it returns the whole file's content as a string.

## Reading text files line by line

Example: 
	`with open(notepad.txt) as notepad:
		`for i in notepad:
				`print(i)

This has 2 newlines (1 from the text file and another as a default option of the `print()` function.

Be careful of the blank spaces in the text file as it can create unnecessary newline elements.

To remove the newline from the notepad:
	`i.rstrip()

This removes any spaces or hidden characters after the visible one.

## Readline() method

Returns a list. Each call iterates through this list object.

Example:
	Notepad contents:
	1
	2
	3
	`with open('text.txt') as file_handler:
		`print(file_handler.readline())
		`print(file_handler.readline())
	Output:
		`1
		`2

## Readlines() method

Returns a list object of the contents of the file. An element is created when it encounters \\n in the file.

Example:
	`with open(file.txt) as file:
		`lines=file.readlines()
	`for i in lines:
		`print(i.rstrip())
	Output:
		`1
		`2
		`3

This includes the newline character from the notepad, so we strip it.

**DO NOT USE `for i in notepad` AND `notepad.readlines()` IN THE SAME CODE BLOCK. `for i` ITERATES THROUGH THE STRINGS AND `notepad.readlines()` ALSO ITERATE THROUGH THE SAME INDEX `for i` USED. 

**THIS MEANS SOME ELEMENTS WILL BE SKIPPED.
## Write mode

Example:
	Notepad contents: 
	None
	`filename='directory/to/notepad.txt'
	`with open(filename,'w') as file_handler:
		`file_handler.write('I love programming')
		`file_handler.write('ye')
	Notepad contents:
		I love programmingye
	Each execution of this program replaces whatever text was written before.
	It does not include newline characters, so it will be written in the same line.

## Append mode

Example:
	`filename='directory/notepad.txt'
	`with open(filename,'a') as file_handler:
		`file_handler.write('I like big datasets\n')
		`file_handler.write('I need money\n')
	Notepad contents:
		I love programmingyeI love datasets
		oh ye


## Split method

Syntax:
	`var.split('separator','maxsplit')
	separator - character in the string, when encountered, separates 2 strings (left and right). Default is space when not assigned.
	maxsplit - ???

Example:
	`watches = 'rolex hublot cartier omega'
	`print(watches.split())
	Output:
	![[regex-split_out.png]]

Example 2:
	`watches='rolex|hublot|cartier|omega'
	`print(watches.split('|'))
	Output:
	![[regex-split_out.png]]

# Regular expression

Methods:
	`findall()` - Returns list containing all matches.
	`search()` - Returns Match object if there is match anywhere in string.
	`split()` - Returns list where string has been split at each match.
	`sub()` - Replaces one or many matches with string.

## Methods
### findall()

Syntax: 
	`regex_object.findall(string_to_find,string_to_search)

Example:
	![[regex-findall_ex.png]]

### finditer()
	![[BSU-finditer_ex.png]]

### search()
	![[BSU-search_ex.png]]

### sub()
	![[BSU-sub_ex.png]]




## Meta Characters

### Brackets \[ ]

Matches a set of characters inside bracket.

Dash (-) is used inside the brackets to represent ranges.
	Example:
		\[az] matches ONLY LOWERCASE A AND OR Z.
		\[a-z] matches ANY LOWERCASE FROM A TO Z.

Caret (^) is used inside to invert the group
	Example:
		\[^az] matches ANY THAT IS NOT LOWERCASE A AND OR Z.

### Period .

Matches ANY character except newline (\\n)

### Caret ^

Asserts the combination starts with the proceeding characters.

Example:
	\^ab ONLY MATCHES IF IT STARTS WITH LOWERCASE 'AB'.

### Dollar $

Asserts the combination end with the preceding characters.

Example:
	ba$ ONLY MATCHES IF IT ENDS WITH LOWER CASE 'BA'.

### Star *

Asserts the preceding CHARACTER occurs AT LEAST 0 OR MORE times (maybe like an optional thing?).

Example:
	ma\*n ONLY MATCHES if 'a' is 0 OR MORE, followed by 'n'.

### Plus +

Asserts the preceding CHARACTER occurs AT LEAST 1 TIME (so, it's required).

Example:
	ma+n ONLY MATCHES if 'a' appears at least once, followed by 'n'.
	The string 'maaaan' MATCHES because 'm' is present and 'a' is present at least once, followed by 'n'.

### NOTE:  

BRACKETLESS expressions mean ORDER MATTERS.

This means the regex 'ma+n' only matches if there is an 'm', 'a', and 'n'. In that order. 'a' can have duplicates but the order must remain.

Example:
	string: 'man' match: y
	string: 'mman' match: n
	string: 'amn' match: n
	string: 'maaan' match: y
	string: 'mmmamamamaman' match: n

### Question Mark ?

Asserts the preceding CHARACTER has 0 or 1 occurrence.

Example:
	ma?n
	string: 'mn' match: y
	string: 'maan' match: n
	string: 'main' match: n

### Curly Brackets {}

Asserts the preceding character repeats {min,max} inclusive.

Order matters, which means it produces a match if there is a match at the START. It will not match if the match is at the END.

Example:
	```import re
	string=r'a{2,3}'
	if re.match(string,'a aa'):
		print('match')
	else:
		print('no match')```
	Output: no match
	```import re
	string=r'a{2,3}'
	if re.match(string,'aa a'):
		print('match')
	else:
		print('no match')```
	Output: match

### Alternation |

Matches if any of the COMBINATIONS (left and right) of the symbol are used. As long as it starts with one of the combinations. 

Example:
	pattern: a|b
	string: 'ba'1 match: y
	string: '1ab' match: n
	string: 'abbbbaaabb' match: y
	string: 'b' match: y

Example 2:
	pattern: a|bxz
	string: 'abxz' match: y
	string: 'baxz' match: n
	string: 'bxzyrt4' match: y
### Group ()

Group sub-patterns. Kind of like groupings in math.

Example: 
	pattern: (a|b)xz 
	This means it will match any string that has either only 'a' or 'b', followed by 'xz'.
	string: 
	string: 'baxz' match: n
	string:  'axz123f' match: y

# Object-oriented Programming 

Based on the concept of objects—a user-defined data type.

Objects contain:
	Data members: aka its variables.
	Procedures: aka its methods (functions).

Objects are created from `classes` which define what the object can do.

There is a difference between a class variable and an instance variable. A class variable is initialized outside of the \_\_init__() method whereas an instance is initialized within. The way to access a class varible is through referencing the class (writing the class name but not creating an instance) whereas an instance variable has to be accessed by instantiating the class name, because otherwise the \_\_init__() method would not execute.

Class
	A blueprint from which objects are based off of.

Object
	An instance (a creation) of the blueprint. And a bundle of state (variables) and behavior (functions), and its own classes, too.

Objects represent the state of information about an abstraction of what you're modeling towards. And it can also represent the functionality you designed it for. 

Example:
	![[OOP-class_ex.png]]


## \_\_init__() Function

Whenever the interpreter encounters an instantiation of a class (ex. car_obj=Car()), the \_\_init__() function is called.

Upon instantiation of a class, it executes the code underneath the \_\_init__() method.

The \_\_init__ function is called as the constructor.
## Creating Classes

Any user-defined name after the `class` keyword will create a class by that name.

Ex:
	class myClass:
	\# Optional comment to explain what is the class (I guess?)
	\# Class variables and functions
	There is now a class called 'myClass'.

Ex 2:
	![[OOP-create_class_ex.png]]


## Accessing values of objects

Call the instance of the object (either 'myCat' or 'Cat('bob','blue',4,20)'), then call the variable (only if it's an attribute).

Ex:
	print(myCat.name) accessing attribute
	print(myCat.details()) accessing methods


The class' \_\_init__() method is a function, so you can assign default values to it like so.
	![[OOP-class_def_var.png]]
	Then modify its values after object creation.

You can also nest a class function inside a class definition.
	![[OOP-call_func_ins_class.png]]

If you want to make a class global variable, you have to define it outside of any methods in the class.

You then access the variable by referencing its class name, then write the variable name. This must be done inside the \_\_init__() method.

Ex:
	```class Cat:
	    cat_c=0
	    def __init__(self):
	        Cat.cat_c+=1
	instance_1=Cat()
	print(Cat.cat_c) # output: 1```

Even without the increment, the only way to access `cat_c` is through `Cat.cat_c`.

When you write `self.cat_c` inside the `__init__()` method, you can only access it through:
`Cat().cat_c`. 

Notice the difference where in the first example, I accessed the variable through referencing the class name `Cat`, then its variable. Whereas on the second, I Insantiated the class `Cat()` and accessed its variable.

Note that the latter doesn't have the same functionality as the former.

## Access Modifiers

public
private
protected

Class attributes with public access modifiers can be accessed inside or outside the class.

private attributes can only be accessed inside the class. Cannot use `Cat().variable_name` to return the value of the attribute because the attribute in question is limited to the internals of the `Cat()` class. 

You can circumvent this by calling a public function that returns the private variable. 

protected variables can only be accessed within the same package.

Ex:
	![[OOP-access_mod_ex.png]]

Example of accessing a private variable through calling a public function:
	![[OOP-access_mod_ex2.png]]


## Inheritance 

A class can inherit the attributes and methods of the base class (Practically speaking, the 2 classses should have a parent-child model). This only applies to anything defined OUTSIDE the \_\_init__() method of the parent class. 

The \_\_init__() method is not required to be defined when creating a parent class for the purpose of inheriting.

The child class can manipulate the attributes of its parent class, though the changes are its own.

Base classes are also called 'super class'.

Ex:
	![[OOP-inheritance_ex.png]]

## Creating Subclasses

Ex:
	![[OOP-inheritance_ex2.png]]
		In this example the subclass `Dog` only inherits the `speak` method of the parent class. With this information, we can access the method of the parent through the child object.

## Using superclass constructor

When you want the child class to inhert the \_\_init__() method of the parent, you can write:
`super().__init__()` inside the \_\_init__() method of the child class.

You have to write arguments that are passed to the parent's \_\_init__ to the child class' \_\_init__() as well. In the example below, it's `**kwargs` . 

Inside the \_\_init__() method of the child class, call the `super()` (pre-built class, maybe?) class and access its \_\_init__() and pass the arguments that are inside the \_\_init__() method of the child class. 

If the child class' \_\_init__() consists of \*\*xyz, then the init will also be \*\*xyz. It cannot be `**kwargs`.

But it is important to note that the \_\_init__ arguments of the child ought to be the same data type as its parent, as the `super().__init__()` can only use arguments passed in the child class.

So while 1 -> 2 are connected, it doesn't mean that 3 -> 1.


Ex:
	![[OOP-superclass_inherit_ex.png]]

## Overriding methods

When the parent class has a method, and you defined the same method in the child class, when you call the method of the child object, it will execute its nearest class. This means that the method executed is the child's.

Ex:
	![[OOP-overwr_method_ex.png]]

If you create a grandchild class and inherit the child class, executing the inherited method of the grandchild object will execute the child's method.

Ex:
	![[OOP-multiple_inheritance_ex.png]]

In the picture, `myCat1` will execute its defined method of `.speak()`. And myLion1 will execute its own defined `.speak()`.

This is because even though they are inheriting methods from their parents, it will execute its latest definition of a same-name function.

## Method Overloading 

A class that can output multiple values depending on the argument passed. This is done by giving a default argument in the initialization of the user-defined function.

Ex:
	![[OOP-method_overload_ex.png]]

Ex2:
	![[OOP-method_overload_ex2.png]]

# Python Standard Library

A Module is the name of a python file.

Inside the module file, it has a collection of functions, classes, constants pertaining to an area of topic.

A group of these files (modules) saved inside a folder is a Package.

A Library is a collection of these packages.

# API

An Application Programming Interace follows an arbitrary set of rules by an application to interact with the application you're working with. 

Think of it like following the rules set by country X so country Y can work with country X. Like foreign affairs.


## Request Library

Used for making HTTP requests in python

Basically anything related to using the browser. Like (1 )opening an img, (2) reading a json file.

