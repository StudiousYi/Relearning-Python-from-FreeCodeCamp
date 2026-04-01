# variable name
variables can only start with _ or a letter (no number)

only a-z A-Z 0-9 and _

no special characters in variable name

case sensitive (age, Age and AGE are all diff)
cannot be one of python's reserved keywords (if, class, def)

# common variable naming conventions
lowercase, with separate words separated by an underscore (aka snake case)
```
my_variable_name = 'freeCodeCamp'
```
***
descriptive names
```
user_age = 30
```
# comments
use #

explain the code to other users (and your future self)
```
# this is a single line
```
```
# comment1
# comment2
# comment3
```

# print()
```
print("hello world")
```
string "hello world" in an **argument** passed to the print function
```
print('My favorite colors are', 'blue', 'green', 'red')

# Output: My favorite colors are blue green red
```
python auto adds a space when items are separated with a comma

# Data type
Python is a **dynamically-typed language** like JavaScript, meaning you **don't need to explicitly declare** types for variables. The language knows what data type a variable is based on what you assign to it.

**type-related error** are only discovered during runtime (its  a bad thing)
***
#### String
name = 'John Doe'
***
#### Int
age = 25
***
#### Float
my_float_var = 4.50
***
#### Boolean
my_boolean_var = True
***
#### Set
An **unordered** collection of unique elements

my_set_var = {7, "hello", 4.5}
***
#### Dict
A collection of key-value pairs enclosed in curly braces

my_dict_var = {'name': 'John Doe', 'age': 28}
***
#### Tuple
An **immutable ordered** collection, enclosed in parentheses (immutable means cannot change)

my_tuple_var = {7, "hello", 4.5}
***
#### Range
A sequence of numbers, often used in loops

```
my_range_var = range(5)
print('Range:', my_range_var) #Range: range(0, 5)
```
***
#### List
An **ordered** collection of elements that supports different data types
```
my_list = [22, 'Hello world', 3.14, True]
print(my_list) # [22, 'Hello world', 3.14, True]
```
***
#### None
A special value that represents the absence of a value
```
my_none_var = None
```

# type()
To get the data type of a variable
```
my_var_1 = 'Hello world'
my_var_2 = 21

print(type(my_var_1)) # <class 'str'>
print(type(my_var_2)) # <class 'int'>
```
# isinstance()
check if a variable matches a specific data type -> returns true or false
```
isinstance('Hello world', str) # True
isinstance(True, bool) # True
isinstance(42, int) # True
isinstance('John Doe', int) # False
```

# Strings
multi-line string: you can use triple double quotes
```
my_str_3 = """Multiline
string"""
my_str_4 = '''Another
multiline
string'''
```

quotation mark in string:

1. use the opposite (single vs double quotation)
2. use backlash \\" 
```
msg = "It's a sunny day"
quote = 'She said, "Hello World!"'
```
```
msg = 'It\'s a sunny day'
quote = "She said, \"Hello!\""
```
**in operator**: check if a string contains one or more characters
```
my_str = 'Hello world'

print('Hello' in my_str)  # True
print('hey' in my_str)    # False
print('hi' in my_str)    # False
print('e' in my_str)  # True
print('f' in my_str)  # False
```
length of a string: **len()**
```
len(my_string)
```
**Indexing**: Each character in a string has a position called an index

To access a character by its index, you use square brackets [] with the index of the character
```
my_str = "Hello world"
print(my_str[0])  # H
print(my_str[6])  # w
```
**Negative indexing**: get the last character of any string with -1
```
my_str = 'Hello world'
print(my_str[-1])  # d
print(my_str[-2])  # l
```

##  Primitive or reference types
**Primitive** types are simple and **immutable**

**Reference** types can hold **multiple** values, and are **either mutable or immutable**

Python treat data types as objects, and some objects are immutable while others are mutable

**Reassignment is allowed** but you **can't change** the original object itself **by adding, removing, or replacing any of its elements**
```
# Reassignment
greeting = 'hi'
greeting = 'hello'
print(greeting) # hello

# Direct modification
greeting = 'hi'
greeting[0] = 'H' # TypeError: 'str' object does not support item assignment
```
## String Concatenation
combine multiple strings together using **+ plus operator**

concatenate a string with a number, you'll get a TypeError

to fix it, use built-in **str()** function, then use the plus operator

augmented assignment operator works too += for string concatenation
```
name = 'John Doe'
age = 26

name_and_age = name  # Start with the name
name_and_age += str(age)  # Append the age as string

print(name_and_age)  # John Doe26
```
## String interpolation
The process of inserting variables and expressions into a string

Python has a category of string called **f-strings (short for formatted string literals)**

F-strings start with f (either lowercase or uppercase) before the quotes, and allow you to embed variables or expressions inside replacement fields indicated by curly braces {}

no need to convert from int to string when using f-string

value of the age, num1, and num2 variables is converted under the hood into a string during the interpolation process.
```
name = 'John Doe'
age = 26
name_and_age = f'My name is {name} and I am {age} years old'
print(name_and_age) # My name is John Doe and I am 26 years old

num1 = 5
num2 = 10
print(f'The sum of {num1} and {num2} is {num1 + num2}') # The sum of 5 and 10 is 15
```

## String Slicing
extract a portion of the string

note that it doesnt modify the original string

note that the stop index is not included, [1:4] means index 1 to 3
```
# string[start:stop]

my_str = 'Hello world'
print(my_str[1:4]) # ell
```

can omit the start index, python default to 0
can omit the end index, python default til the end of string
```
my_str = 'Hello world'
print(my_str[:7])  # Hello w
print(my_str[8:])  # rld
```

**step** parameter (its at the end)
```
# string[start:stop:step]
my_str = 'Hello world'
print(my_str[0:11:2])  # Hlowrd
# extract every 2 step
```
string can be reversed by using -1 step parameter
```
my_str = 'Hello world'
print(my_str[::-1]) # dlrow olleH
```

## Common string methods
upper(): Returns a new string with all characters converted to uppercase

lower(): Returns a new string with all characters converted to lowercase

strip(): Returns a new string with the specified leading and trailing characters removed. If no argument is passed it removes leading and trailing whitespace
```
my_str = '  hello world  '

trimmed_my_str = my_str.strip()
print(trimmed_my_str)  # "hello world"
```

replace(old, new): Returns a new string with all occurrences of old replaced by new
```
my_str = 'hello world'

replaced_my_str = my_str.replace('hello', 'hi')
print(replaced_my_str)  # hi world
```

split(separator): Splits a string on a specified separator into a list of strings. If no separator is specified, it splits on whitespace
```
my_str = 'hello world'

split_words = my_str.split()
print(split_words)  # ['hello', 'world']
```

join(iterable): Joins elements of a list into a string with a separator
```
my_list = ['hello', 'world']

joined_my_str = ' '.join(my_list)
print(joined_my_str)  # hello world
```
startswith(prefix): Returns a boolean indicating if a string starts with the specified prefix
```
my_str = 'hello world'

starts_with_hello = my_str.startswith('hello')
print(starts_with_hello)  # True
```
endswith(suffix): Returns a boolean indicating if a string ends with the specified suffix
```
my_str = 'hello world'

ends_with_world = my_str.endswith('world')
print(ends_with_world)  # True
```
find(substring): Returns the index of the first occurrence of substring, or -1 if it doesn't find one
```
my_str = 'hello world'

world_index = my_str.find('world')
print(world_index)  # 6
```
count(substring): Returns the number of times a substring appears in a string
```
my_str = 'hello world'

o_count = my_str.count('o')
print(o_count)  # 2
```
capitalize(): Returns a new string with the first character capitalized and the other characters lowercased
```
my_str = 'hello world'

capitalized_my_str = my_str.capitalize()
print(capitalized_my_str)  # Hello world
```
isupper(): Returns True if all letters in the string are uppercase and False if not

islower(): Returns True if all letters in the string are lowercase and False if not

title(): Returns a new string with the first letter of each word capitalized
```
my_str = 'hello world'

title_case_my_str = my_str.title()
print(title_case_my_str)  # Hello World
```

### Integers and Floating Point Numbers
perform arithmetic calculations
```
+ - * /
```
If you mix integers and floats, Python will return a float as the result
***
modulo operator: find remainder

floor division: divides two numbers and returns the greatest integer <= result

exponentiation: raises a number to the power of another
```
% modulo
// floor division 
** exponentiation
```
result of an operation involving floats has more decimal digits than expected:

0.30000000000000004 instead of 0.3

because numbers are stored in **binary format**, and some fractions cannot be represented exactly in binary
***
float() function returns a floating-point number constructed from int/string

int() function returns an integer constructed from float/string

round(): Rounds a number to the specified number of decimal places (default 0 so integer)
```
my_int_1 = 4.798
my_int_2 = 4.253

rounded_int_1 = round(my_int_1)
rounded_int_2 = round(my_int_2, 1)

print(rounded_int_1) # 5
print(rounded_int_2) # 4.3
```
abs(): returns the absolute value of a number

pow(): raises a number to the power of another or performs modular exponentiation
```
result_1 = pow(2, 3)  # Equivalent to 2 ** 3
print(result_1)  # 8

result_2 = pow(2, 3, 5)  # (2 ** 3) % 5
print(result_2)  # 3
```

### Augmented Assignments
```
my_var = 10
my_var += 5

# instead of my_var = my_var + 5
```
multiplication assignment operator can be used to repeat a string
```
greet = 'Hello'
greet *= 3

print(greet) # HelloHelloHello
```

# Conditional Statements & Comparison Operators
### Comparison operators: used in conditional statements
compare two or more values, and return a boolean value
```
==
!=
>
<
>=
<=
```

## If statement
The body of the if statement constitutes a **code block**, which is a group of statements that belong together. In Python, the level of **indentation** is what defines a code block.

code within the body of the if statement runs only when the condition evaluates to **True**

IndentationError: when code is not indentated correctly

Python style guide recommends using **four spaces**
```
if condition:
    pass # Code to execute if condition is True
```
## Else statement
else clause runs when the if condition is **false**

## elif statement
extend your if statement with the elif (else if) keyword

## Pass statement
When a pass statement is executed, nothing happens

Used as a placeholder

# Boolean Operators / Logical Operators
allow you to combine multiple expressions to create more complex logic

**Short-circuiting** means Python checks values from left to right and stops as soon as it determines the final result

Python’s **and**, **or**, and **not** operators

## Truthy & Falsy values
Here are a few **falsy** values:

None

False

Integer 0

Float 0.0

Empty strings ""

Other values like non-zero numbers, and non-empty strings are **truthy**

# Function
**reusable** pieces of code that **run** when you **call** them

## input()
prompt the user for input
```
name = input('What is your name?') # User types "Kolade" and presses Enter  
print('Hello', name) # Output: Hello Kolade
```

## Writing custom functions
**def** keyword
```
def calculate_sum(a, b):
    print(a + b)
```
To **run** the function, you need to **call** it with its name()
```
calculate_sum() # result of a+b
```
*a* and *b* in this function are **parameters**: placeholder variables (so we know what inputs to pass to this function)

To use the parameters, you have to pass in **arguments**
```
calculate_sum(3, 1)
```
3 and 1 here are the arguments: values passed to the function

**return** keyword: Functions also use a special return keyword to **exit** the function and **return a value**. If you don't explicitly use return, Python will return None by default.

# Scope
scope determines the point at which you can **access a variable**

It's what controls the **lifetime** of a variable and how it is **resolved** in different parts of the code

Python follows the LEGB
```
Local scope (L): Variables defined in functions or classes.

Enclosing scope (E): Variables defined in enclosing or nested functions.

Global scope (G): Variables defined at the top level of the module or file.

Built-in scope (B): Reserved names in Python for predefined functions, modules, keywords, and objects.
```
### Local: calling a variable out side of a function will lead to NameError
```
def my_func():
    my_var = 10
    print(my_var)

my_func() # 10

print(my_var) # NameError: name 'my_var' is not defined
```
### Enclosing: a function that's nested inside another function can access the variables of the function it's nested within

inner_func() can freely access the msg variable defined in the outer_func(), but the reverse is not true
```
def outer_func():
    msg = 'Hello there!'

    def inner_func():
        print(msg)

    inner_func()

outer_func() # Hello there!
```
make res a **non-local variable** with the **nonlocal** keyword
```
def outer_func():
    msg = 'Hello there!'
    res = ""  # Declare res in the enclosing scope

    def inner_func():
        nonlocal res  # Allow modification of an enclosing variable
        res = 'How are you?'
        print(msg)  # Accessing msg from outer_func()

    inner_func()
    print(res)  # Now res is accessible and modified

outer_func()

# Output:
# Hello there!
# How are you?
```
### Global: refers to variables that are declared **outside** any functions or classes that can be accessed from anywhere in the program
if you want to make a locally scoped variable defined **inside a function globally** accessible, you can use the global keyword:
```
my_var_1 = 7

def show_vars():
    global my_var_2
    my_var_2 = 10
    print(my_var_1)
    print(my_var_2)

show_vars() # 7 10

# my_var_2 is now a global variable and can be accessed anywhere in the program
print(my_var_2) # 10
```
You can also use the global keyword to modify a global variable:
```
my_var = 10  # A global variable

def change_var():
    global my_var  # Allows modification of a global variable
    my_var = 20

change_var()

print(my_var)  # my_var is now modified globally to 20
```
### Built-in scope: refers to all of Python's built-in functions, modules, and keywords, and are available anywhere in your program