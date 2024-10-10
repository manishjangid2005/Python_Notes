# Python Notes

## Index

1. [Unit-1 Introduction to Python](#unit-1-introduction-to-python)
2. [Unit-2 Python Data Structures](#unit-2-python-data-structures)
3. [Unit-3 Introduction to Functions](#unit-3-introduction-to-functions)

# Unit-1 Introduction to Python

## Data Types
``` Python
a = 12
b = 2.3
c = complex(2,3)
d = "Hello"
isconnected = True

print(type(c))

list = [1, 2, 3, 4, 5]               # Sequence Type
tuple = ("Here", "There", "Where")   # Immutable
dict = {"name": "Mohit", "age": 20}  # Mapping Type
set = {1, 2, 3, 4}                   # Set Type
```
## String operations

```python
#Strings are immutable
a = ",,,Mohit,,,"
print(a.upper())            # ,,,MOHIT,,,
print(a.lower())            # ,,,mohit,,, 
print(a.strip(","))         # Mohit
print(a.replace(",","*"))   # ***Mohit***
print(a.split(" "))         # [',,,Mohit,,,']
```

* isalnum = A-Z, a-z, 0-9----> True

* isalpha = A-Z,a-z-----> True

* islower = All lower case -----> True

* isprintable = if all the values within the given string are printable ----> True

* isspace =  only and only if the string contains white spaces -----> True


* istitle = First letter of each word of the string is capitalized ------> True

* isupper = All upper case -----> True

* swapcase = Upper case are converted to lower case and lower case to upper case.

* title =  capitalizes each letter of the word within the string.

## Type Conversion

```python
int_value: int = 50
txt_value: str = "100"

print(int_value + int(txt_value))  # 150
print(str(int_value) + txt_value)  # 50100

# User input
num = int(input("Enter the number: "))
```

# Unit-2 Python Data Structures

## Lists in Python
* A List is a collection of items (called elements) which are ordered and changeable. 
* Lists are defined by square brackets [].

``` Python
list1 = [10, 30, 1, 2, 3, 2, 4, 5]

# Add
list1.append(7)
list1.insert(1,3)       # [10, 3, 30, 1, 2, 3, 2, 4, 5, 7]
# Sort                    
list1.sort()            # [1, 2, 2, 3, 3, 4, 5, 7, 10, 30]
# Delete
list1.remove(30)        # [1, 2, 2, 3, 3, 4, 5, 7, 10]
# Access
list1[3]                # 3
# Slicing
list1[2:6]              # [2, 3, 3, 4]
# Reverse
list1[::-1]             # [10, 7, 5, 4, 3, 3, 2, 2, 1]
# Occurence
list1.count(2)          # 2
# Length
len(list1)              # 9
# Minimum
min(list1)              # 1
# Maximum 
max(list1)              # 10
# Adidtion 
sum(list1)              # 37
```

### Passing Lists to a Function:

```python
# Passing Lists to a Function
def print_list(lst):
    for item in lst:
        print(item)
        
print_list(list1)          # 1 2 2 3 3 4 5 7 10

# Returning Lists from a Function:
def create_list():
    return [1, 2, 3, 4]

new_list = create_list()
print(new_list)           # Outputs: [1, 2, 3, 4]
```

## Tuples in Python

* A Tuple is similar to a list, but it is immutable (i.e., it cannot be changed after creation). 
* Tuples are defined using parentheses ().

```python
tuple1 = ()

tuple1 = tuple1 + (1, 2, 4, 7, 10)

# Sorting
list(tuple1).sort()

# Accesssing
tuple1[1]

# Slicing
tuple1[1:3]

# Length
len(tuple1)

# Maximum and minimum
max(tuple1)
min(tuple1)

# Sum 
sum(tuple1)

# Type
type(tuple1)                 # tuple
isinstance(tuple1, tuple)    # True

# Delete
del  tuple1
```

## Sets in Python

* A set is an unordered collection of unique items. 
* Sets are defined using curly braces {} or the set() function.

```python
my_set = {1, 2, 3, 'apple'}

print(2 in my_set)               # Outputs: True
print('banana' not in my_set)    # Outputs: True

element = {True, 1, 'Tim'}

element.add('Tom')               # Will add in any order
element.remove('Tim')
element.pop()                    # Random
element.clear()   
```

### Set Operations:
* union(): Combines sets.
* intersection(): Finds common elements.
* difference(): Finds elements present in one set but not in another.
* add(): Adds an element to the set.
* remove(): Removes an element (raises an error if not present).
* discard(): Removes an element (does not raise an error if not present).

```python
# Initial sets
set_a = {1, 2, 3}
set_b = {3, 4, 5}

# Union: Combines sets
print(set_a.union(set_b))          # Outputs: {1, 2, 3, 4, 5}

# Intersection: Finds common elements
print(set_a.intersection(set_b))   # Outputs: {3}

# Difference: Finds elements in set_a but not in set_b
print(set_a.difference(set_b))     # Outputs: {1, 2}

# Add: Adds an element to set_a
set_a.add(6)
print(set_a)                       # Outputs: {1, 2, 3, 6}

# Remove: Removes an element (raises an error if not present)
set_a.remove(6)
print(set_a)                       # Outputs: {1, 2, 3}

# Discard: Removes an element (no error if element is not present)
set_a.discard(7)                   # No error if 7 is not present
print(set_a)                       # Outputs: {1, 2, 3}
```

## Dictionaries in Python

* A dictionary is a collection of key-value pairs. 
* It is defined using curly braces {}.

```python
my_dict = {'name': 'John', 'age': 25}

my_dict['city'] = 'New York'  # Adding
my_dict['age'] = 30           # Updating

# You can format dictionaries to display or access data efficiently.
for key, value in my_dict.items():
    print(f"{key}: {value}")

# Deleting Items
del my_dict['city']
my_dict.pop('age')

student_marks = {'Alice': 85, 'Bob': 92, 'Charlie': 78}
print(student_marks['Bob'])  # Outputs: 92
```

``` python
my_dict = {'name': 'Alice', 'age': 25}

len(my_dict)                         # Outputs: 2
my_dict.keys()                       # Outputs: dict_keys(['name', 'age'])
my_dict.values()                     # Outputs: dict_values(['Alice', 25])
my_dict.items()                      # Outputs: dict_items([('name', 'Alice'), ('age', 25)])
my_dict.update({'city': 'New York'}) # Outputs: {'name': 'Alice', 'age': 25, 'city': 'New York'}
my_dict.clear()                      # Outputs: {}
my_dict_copy = my_dict.copy()
```
# Unit-3 Introduction to Functions

* A function in Python is a reusable block of code designed to perform a specific task. 
* Functions help in organizing code, making it more modular and reusable. 
* Python functions are defined using the def keyword.

## Parameters and Arguments in Functions
* Parameters are variables listed in a function's definition. They act as placeholders for the values the function will receive.

* Arguments are the actual values passed to the function when it is called.

```python
def add(a, b):      # a and b are parameters
    return a + b

result = add(5, 3)  # 5 and 3 are arguments
print(result)       # Outputs: 8
```

### Types of arguments:

* Positional arguments: Passed by position.
* Keyword arguments: Passed by name (key=value).
* Default arguments: Predefined values for parameters if no argument is passed.

### Local and Global Scope of a Variable
* Local Scope: Variables declared inside a function are in the local scope. They exist only within the function and cannot be accessed outside of it.

* Global Scope: Variables declared outside of any function have a global scope and can be accessed both inside and outside of functions.

### Recursive Functions 
* A recursive function is a function that calls itself to solve a smaller instance of the problem until it reaches a base case that stops recursion.
* Recursive functions are useful for solving problems that can be broken down into similar subproblems 

```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(5))  # Outputs: 120
```

### Lambda Functions:
* A lambda function is a small, anonymous function defined using the lambda keyword. 
* It can have any number of parameters but only one expression, which is evaluated and returned.
* Lambda functions are ideal for simple, one-time operations where defining a full function would be unnecessary.

```python
square = lambda x: x * x
print(square(5))    # Outputs: 25
```

## Pass And ...

```python
def dont_know:
    pass

def dont_know:
    ...

if num > 0:
    pass
else:
    pass

while True:
    pass
```

## *Args and **Kwargs

* Use *args when you're not sure how many positional arguments will be passed to your function.
* *args converts into the tuple.
* Use **kwargs when you're not sure how many keyword arguments will be passed to your function.
* **Kwargs converts into the dictionary.

```python
def example_function(*args, **kwargs):
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)

example_function(1, 2, 3, name="Alice", age=30)

# Positional arguments: (1, 2, 3)
# Keyword arguments: {'name': 'Alice', 'age': 30}
```

##  / and *

* | / Positional-Only Parameters
<br/> The / symbol in a function signature is used to indicate that all parameters before it must be passed as positional arguments, not as keyword arguments.

* | * Keyword-Only Parameters
<br/> The * symbol in a function signature is used to indicate that all parameters after it must be passed as keyword arguments, not as positional arguments.
