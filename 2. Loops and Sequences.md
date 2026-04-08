# Chapter 2

## 3 Python basic sequence types: list, tuples, and ranges

## List
**Ordered sequence** of elements that can be comprised of strings, numbers, or even other lists

Lists are **mutable** and use **zero-based indexing**

To access an element from the cities list, you can **reference** its index number in the sequence.
```
cities = ['Los Angeles', 'London', 'Tokyo']
cities[0] # 'Los Angeles'
```
**Negative indexing** is used to access elements starting from the **end** of the list
```
cities = ['Los Angeles', 'London', 'Tokyo']
cities[-1] # 'Tokyo'
```
Another way to create a list is to use the **list() constructor**. The list() constructor is used to convert an **iterable** into a list like this:

An **iterable** is a special type of object that can be looped over one item at a time
```
developer = 'Jessica'
list(developer) # ['J', 'e', 's', 's', 'i', 'c', 'a']
```
Update a value at a particular index
```
programming_languages = ['Python', 'Java', 'C++', 'Rust']
programming_languages[0] = 'JavaScript'
print(programming_languages) # ['JavaScript', 'Java', 'C++', 'Rust']
```
**IndexError** : when an index that is out of bounds for the list is passed

**del** keyword: remove an element from a list
```
developer = ['Jane Doe', 23, 'Python Developer']
del developer[1]
print(developer) # ['Jane Doe', 'Python Developer']
```
**in** keyword: check if an element is inside the list
```
programming_languages = ['Python', 'Java', 'C++', 'Rust']

'Rust' in programming_languages # True
'JavaScript' in programming_languages # False
```
Accessing elements in a **Nested list**:
```
developer = ['Alice', 25, ['Python', 'Rust', 'C++']]
developer[2][1] # 'Rust'
```
**Unpacking values** from a list is a technique used to assign values from a list to new variables
```
developer = ['Alice', 34, 'Rust Developer']
name, age, job = developer

print(name) # 'Alice'
print(age) # 34
print(job) # 'Rust Developer'
```
collect any remaining elements from a list, you can use the **asterisk (*)** operator:
```
developer = ['Alice', 34, 'Rust Developer']
name, *rest = developer

print(name) # 'Alice'
print(rest) # [34, 'Rust Developer']
```
**ValueError**: numbers of variables on the left side of the assignment operator != the total numbers of items in the list
```
developer = ['Alice', 34, 'Rust Developer']
name, age, job, city = developer

# Traceback (most recent call last):
#  File "<stdin>", line 2, in <module>
# ValueError: not enough values to unpack (expected 4, got 3)
```
**Slice operator**: Similar to strings
```
desserts = ['Cake', 'Cookies', 'Ice Cream', 'Pie', 'Brownies']
desserts[1:4] # ['Cookies', 'Ice Cream', 'Pie']
```
Another thing you can do with the slice operator : is specify a **step interval** which determines how much to **increment** between the indices
```
numbers = [1, 2, 3, 4, 5, 6]
numbers[1::2] # [2, 4, 6]
```
**append()**: add an item to the end of the list
```
numbers = [1, 2, 3, 4, 5]
numbers.append(6)
print(numbers) # [1, 2, 3, 4, 5, 6]
```
adding a nested list to a listed
```
numbers = [1, 2, 3, 4, 5]
even_numbers = [6, 8, 10]

numbers.append(even_numbers)
print(numbers) # [1, 2, 3, 4, 5, [6, 8, 10]]
```
**extend()**: similar to the append() method, but adds multiple elements from one list to another
```
numbers = [1, 2, 3, 4, 5]
even_numbers = [6, 8, 10]

numbers.extend(even_numbers)
print(numbers) # [1, 2, 3, 4, 5, 6, 8, 10]
```
**insert()**: insert an element at a specific index in a list

1st argument: the index of insertion

2nd argument: element to insert
```
numbers = [1, 2, 3, 4, 5]
numbers.insert(2, 2.5)

print(numbers) # [1, 2, 2.5, 3, 4, 5]
```
**remove()**: remove an element from a list

Note: it only remove the **first occurrence** of an item. **Not all of them**
```
numbers = [10, 20, 30, 40, 50, 50]
numbers.remove(50)

print(numbers) # [10, 20, 30, 40, 50]
```
**pop()**: remove an element at a specific **index** in the list
```
numbers = [1, 2, 3, 4, 5]
numbers.pop(1) # The number 2 is removed/returned
```
last element is removed when no index is specify
```
numbers = [1, 2, 3, 4, 5]
numbers.pop() # The number 5 is removed/returned
```
**clear()**: empty the list
```
numbers = [1, 2, 3, 4, 5]
numbers.clear()

print(numbers) # []
```
**sort()**: sort the elements in place
```
numbers = [19, 2, 35, 1, 67, 41]
numbers.sort()

print(numbers) # [1, 2, 19, 35, 41, 67]
```
**sorted()**: returns a new sorted list without modifying the original list
```
numbers = [19, 2, 35, 1, 67, 41]
sorted_numbers = sorted(numbers)

print(numbers) # [19, 2, 35, 1, 67, 41]
print(sorted_numbers) # [1, 2, 19, 35, 41, 67]
```
**reverse()**: reverse a list of elements
```
numbers = [6, 5, 4, 3, 2, 1]
numbers.reverse()

print(numbers) # [1, 2, 3, 4, 5, 6]
```
**index ()**: find the first index where an element can be found in a list

If the element cannot be found, then Python throws a ValueError
```
programming_languages = ['Rust', 'Java', 'Python', 'C++']
programming_languages.index('Java') # 1

programming_languages.index('JavaScript')

"""
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: 'JavaScript' is not in list
"""
```
## Tuples
is a Python data type used to create an **ordered sequence** of values

can contain a **mixed** set of data types

similar to lists but tuples are **immutable**

This means that the elements in a tuple **cannot be changed** once it's created
```
programming_languages = ('Python', 'Java', 'C++', 'Rust')
programming_languages[0] = 'JavaScript'

"""
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
TypeError: 'tuple' object does not support item assignment
"""
```
Another way to create a tuple is by using the **tuple() constructor** like this:
```
developer = 'Jessica'
tuple(developer) # ('J', 'e', 's', 's', 'i', 'c', 'a')
```
Similar to list, can use the following methods/operations:

in keyword

unpack

asterisk (*) operator

slice operator

remove an item from a tuple, that isn't possible because tuples are immutable. So this example, will produce an error:
```
developer = ('Jane Doe', 23, 'Python Developer')
del developer[1]

"""
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
TypeError: "tuple" object doesn't support item deletion
"""
```
when to use **Tuple** over **list**?

If you need a dynamic collection of elements where you can add, remove and update elements, then you should use a list. If you know that you are working with a fixed and immutable collection of data, then you should use a tuple.

**count()**: determine how many times an item appears in a tuple

If the specified item in the count() function is not present at all in the tuple, then the return value is 0

If no arguments are passed into the count() function, then Python raises a TypeError

```
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust')
programming_languages.count('Rust') # 2

programming_languages.count('JavaScript') # 0

programming_languages.count()

"""
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
TypeError: tuple.count() takes exactly one argument (0 given)
"""
```
**index()**: similar to when use in a list, it finds the index of the element in the tuple

returns **ValueError** if item cannot be found
```
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust')
programming_languages.index('Java') # 1

programming_languages.index('JavaScript')

"""
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
ValueError: tuple.index(x): x not in tuple
"""
```
Another thing you can do with the index() method is to pass in **optional start and stop index** arguments

starts from index 3, hence return index 5
```
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust', 'Python')
programming_languages.index('Python', 3) # 5
```
starts from index 2 and stops before 5 (til 4, 5 not included), hence return index 2
```
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust', 'Python', 'JavaScript', 'Python')
programming_languages.index('Python', 2, 5) # 2
```
**sorted()**

always create a **new list** of the sorted values

default = alphabetical order

Customize the sorting behavior, you can use the **optional** **reverse** and **key** arguments

sorting a tuple by **length** of the element and returning a list
```
programming_languages = ('Rust', 'Java', 'Python', 'C++', 'Rust', 'Python')
sorted(programming_languages, key=len)

# Result
# ['C++', 'Rust', 'Java', 'Rust', 'Python', 'Python']


sorted(programming_languages, reverse=True)

# Result
# ['Rust', 'Rust', 'Python', 'Python', 'Java', 'C++']
```

## Loops
### For Loop
```
programming_languages = ['Rust', 'Java', 'Python', 'C++']

for language in programming_languages:
    print(language)
```
Result
```
Rust
Java
Python
C++
```
Notice that the print(language) is indented inside of the loop. Without that indentation, you would get an **IndentationError**

**Nested for loop**
```
categories = ['Fruit', 'Vegetable']
foods = ['Apple', 'Carrot', 'Banana']

for category in categories:
    for food in foods:
        print(category, food)
```
Result
```
Fruit Apple
Fruit Carrot
Fruit Banana
Vegetable Apple
Vegetable Carrot
Vegetable Banana
```
### While Loop
**repeat** a block of code until the condition is **False**
```
secret_number = 3
guess = 0

while guess != secret_number:
    guess = int(input('Guess the number (1-5): '))
    if guess != secret_number:
        print('Wrong! Try again.')

print('You got it!')
```

### Break and Continue statements
**Break** statement is used to **stop** the execution of a loop
```
developer_names = ['Jess', 'Naomi', 'Tom']

for developer in developer_names:
    if developer == 'Naomi':
        break
    print(developer)
```
In this example, we iterate through a list of developer_names and print each name to the console. If the name is equal to Naomi, then we break out of the loop. This results in only the name Jess being printed to the console

**Continue** statement is used to **skip the current iteration of a loop** and move onto the next iteration
```
developer_names = ['Jess', 'Naomi', 'Tom']

for developer in developer_names:
    if developer == 'Naomi':
        continue
    print(developer)
```
Only Jess and Tom are printed because the continue statement skips the second iteration of the loop when developer is equal to Naomi

### Range()
used to generate a sequence of integers

range(start, stop, step)

The **required stop argument** is an integer that represents the **end** point for the sequence of numbers being generated
```
for num in range(3):
    print(num)
```
Sequence of numbers between 0 and 2. The integer 3 is **not included** because the stop argument is non-inclusive

**If Start argument** is not specified, then the **default is 0**

**If Step argument** is not specified, then the **default is 1**
```
for num in range(2, 11, 2):
    print(num)
```
If you don't provide any arguments to range(), then you'll get a **TypeError**

only accepts **integers** as arguments, not floats

If you try to pass floats as arguments, you'll get a **TypeError**

If you want to generate a sequence of integers in **decrementing** order, then you can use a **negative** integer for the step argument
```
for num in range(40, 0, -10):
    print(num)
```
Using the list construct with the range(): the list constructor is used to convert an iterable into a list
```
numbers = list(range(2, 11, 2))
print(numbers) # [2, 4, 6, 8, 10]
```

### Enumerate
**keeps track of the index** for an iterable and returns an **enumerate object**
```
languages = ['Spanish', 'English', 'Russian', 'Chinese']

list(enumerate(languages))
# [(0, 'Spanish'), (1, 'English'), (2, 'Russian'), (3, 'Chinese')]
```
Each entry in the enumerate object (now a list) is a tuple containing a count, followed by a value from the iterable passed to the enumerate() function
```
languages = ['Spanish', 'English', 'Russian', 'Chinese']

for index, language in enumerate(languages):
    print(f'Index {index} and language {language}')
```
We **unpack** the count and value for each tuple in the enumerate object into variables named index and language, respectively. Finally, both those variables are used in an f-string that's printed to the console in each iteration of the loop
```
Index 0 and language Spanish
Index 1 and language English
Index 2 and language Russian
Index 3 and language Chinese
```

The enumerate() function also accepts an **optional start** argument that specifies the **starting** value for the count. If this argument is omitted, then the count will begin at 0
```
languages = ['Spanish', 'English', 'Russian', 'Chinese']

for index, language in enumerate(languages, 1):
    print(f'Index {index} and language {language}')
```
```
Index 1 and language Spanish
Index 2 and language English
Index 3 and language Russian
Index 4 and language Chinese
```
### Zip
**combines lists** into **pairs of elements** and returns an **iterator of tuples**
```
developers = ['Naomi', 'Dario', 'Jessica', 'Tom']
ids = [1, 2, 3, 4]

list(zip(developers, ids))
# [('Naomi', 1), ('Dario', 2), ('Jessica', 3), ('Tom', 4)]
```
zip() combines the two lists "developers" and "ids" into pairs of elements and returns an iterator of tuples

The for loop then **unpacks each tuple** into **name** and **id**
```
developers = ['Naomi', 'Dario', 'Jessica', 'Tom']
ids = [1, 2, 3, 4]

for name, id in zip(developers, ids):
    print(f'Name: {name}')
    print(f'ID: {id}')
```
```
Name: Naomi
ID: 1
Name: Dario
ID: 2
Name: Jessica
ID: 3
Name: Tom
ID: 4
```
### List Comprehensions
**Create a new list** in a single line by **combining a loop and condition** directly within square brackets
```
even_numbers = [num for num in range(21) if num % 2 == 0]
print(even_numbers)
```

In the next example, we have a list of numbers and want to create a new list of tuples indicating which numbers are even or odd. In the first part of the list comprehension, we use an if statement to check if the number is evenly divisible by 2. If so, then the result is a tuple of that number followed by the word Even. Otherwise, the result is a tuple with the number followed by the word Odd
```
numbers = [1, 2, 3, 4, 5]
result = [(num, 'Even') if num % 2 == 0 else (num, 'Odd') for num in numbers]
print(result)
```
```
[(1, 'Odd'), (2, 'Even'), (3, 'Odd'), (4, 'Even'), (5, 'Odd')]
```
### Filter()
The filter() function is used to **select elements** from an iterable that meet a **specific condition**. The filter() function accepts a **function** and an **iterable** for its arguments. In this example, we are passing in an is_long_word function into the filter() function to check if the current word count is greater than 4. All words that have a character count greater than 4 are added into a new list and assigned to the long_words variable.
```
words = ['tree', 'sky', 'mountain', 'river', 'cloud', 'sun']

def is_long_word(word):
    return len(word) > 4

long_words = list(filter(is_long_word, words))
print(long_words) # ['mountain', 'river', 'cloud']
```
### Map()
takes an **iterable** and **applies a function** to each of its elements
```
celsius = [0, 10, 20, 30, 40]

def to_fahrenheit(temp):
    return (temp * 9/5) + 32

fahrenheit = list(map(to_fahrenheit, celsius))
print(fahrenheit) # [32.0, 50.0, 68.0, 86.0, 104.0]
```
**Difference** between filter and map function is that the map() has a 1:1 input-output ratio and the filter() may contain a list that is **shorter** than the input list

### Sum()
is used to get the sum from an iterable like a list or tuple
```
numbers = [5, 10, 15, 20]
total = sum(numbers)
print(total) # Result: 50
```
pass in an **optional start argument** which sets the **initial value** for the summation
```
numbers = [5, 10, 15, 20]
total = sum(numbers, 10) # positional argument
# OR total = sum(numbers, start=10) # keyword argument (same result but clearer)
print(total) # 60
```

### Lambda()
it is an **anonymous inline function** (A function without a name that you write in one line)
```
# how a square () looks like when refactored into a lambda function

lambda num: num ** 2
```
Lambda functions are great when you need to use them in **higher order** functions
```
numbers = [1, 2, 3, 4, 5]

even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # [2, 4]
```

it is important to be aware of best practices: not a good practice to assign a lambda function to a **variable** as it defeats the purpose of using anonymous functions

avoid creating lambda functions that are **difficult to read** or unnecessarily complicated
