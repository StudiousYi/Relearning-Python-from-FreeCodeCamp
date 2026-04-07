# Chapter 3
## Dictionary
Dictionaries are **built-in data structures** that store collections of **key-value pairs**

Use a key to find its corresponding value

Usage: 

when you need to associate values to unique keys

when you need to find a value fast based on the key

when you need to represent structured data
```
dictionary = {
    key1: value1,
    key2: value2
}
```
After each value, except the last one, there's a **comma to separate** the different key-value pairs

**Keys** must be **unique** in the dictionary, and they must be an **immutable** data type

However, the **values** can be **repeated**, and they can be of **any** data type
```
pizza = {
    'name': 'Margherita Pizza',
    'price': 8.9,
    'calories_per_slice': 250,
    'toppings': ['mozzarella', 'basil']
}
```
The dictionary is assigned to the **pizza variable**

It has **4 key-value pairs**: name, price, calories_per_slice, and toppings

Another alternative would be using the **dict() constructor** by passing a **list of tuples as argument** to the dict() constructor
```
pizza = dict([('name', 'Margherita Pizza'), ('price', 8.9), ('calories_per_slice', 250), ('toppings', ['mozzarella', 'basil'])])
```
To **access** the value of a key-value pair, you can use this syntax, known as **bracket notation**. It's the **name of the variable that holds the dictionary**, followed by **square brackets**, and the key you want to access within the square brackets:
```
dictionary[key]
```
```
pizza['name']

# 'Margherita Pizza'
```
To **update** a value, you just need to add the assignment operator, followed by the new value.

If the key **doesn't exist** in the dictionary, a **new key-value pair will be created**. In recent versions of Python, dictionaries preserve the order of insertion. This is helpful when you need to iterate over the dictionary:
```
pizza['name'] = 'Margherita'
```
## .get() method
similar to the bracket notation that we just used, but its **advantage** is that you can **set a default value**, so you won't get an error if the key doesn't exist:
```
dictionary.get(key, default)
```
if the toppings key doesn't exist, it will return an empty list, which is the default value that we are passing here as the second argument. But if toppings does exist, it will return that value
```
pizza.get('toppings', []) # ['mozzarella', 'basil']
```
The **.keys()** and **.values()** methods return a **view object** with all the keys and values in the dictionary, respectively

view object is just a way to see the content of a dictionary without creating a separate copy of the data
```
pizza.keys()
# dict_keys(['name', 'price', 'calories_per_slice'])

pizza.values()
# dict_values(['Margherita Pizza', 8.9, 250])
```
**.items()** method returns a view object with all the key-value pairs in the dictionary, including both the keys and the values
```
pizza.items()

# dict_items([('name', 'Margherita Pizza'), ('price', 8.9), ('calories_per_slice', 250)])
```
**.clear()** method removes all the key-value pairs from the dictionary
```
pizza.clear()
```
**.pop()** method removes the key-value pair with the key that you specify as the first argument and returns its value. If the key doesn't exist, it returns the default value that you specify as the second argument. If the key doesn't exist and you don't pass a default value, a KeyError is raised
```
pizza.pop('price', 10)
pizza.pop('total_price') # KeyError
```
In Python 3.7 and more recent versions, the **.popitem()** method removes the **last inserted** item
```
pizza.popitem()
```
**.update()** method updates the key-value pairs with the key-value pairs of **another dictionary**. If they have keys **in common**, their values are **overwritten**
```
pizza.update({ 'price': 15, 'total_time': 25 })

#{
#    'name': 'Margherita Pizza', 
#    'price': 15, 
#    'calories_per_slice': 250, 
#    'toppings': ['mozzarella', 'basil'], 
#    'total_time': 25
#}
```

