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

my_none_var = None
***
# type()
To get the data type of a variable