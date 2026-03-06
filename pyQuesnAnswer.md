# Python Question & Answer Guide

## String Operations

**Q: How can we change a string from lower to upper case?**
A: By using the `.upper()` function.
```python
text = "hello"
print(text.upper())  # Output: HELLO
```

**Q: How do we convert a string to lowercase?**
A: By using the `.lower()` function.
```python
text = "HELLO"
print(text.lower())  # Output: hello
```

**Q: How do we check if a string contains a specific word?**
A: By using the `in` operator.
```python
text = "Hello World"
print("World" in text)  # Output: True
print("Python" in text)  # Output: False
```

**Q: How do we find the length of a string?**
A: By using the `len()` function.
```python
text = "Python"
print(len(text))  # Output: 6
```

**Q: How do we replace a word in a string?**
A: By using the `.replace()` method.
```python
text = "Hello World"
new_text = text.replace("World", "Python")
print(new_text)  # Output: Hello Python
```

**Q: How do we split a string into a list?**
A: By using the `.split()` method.
```python
text = "Hello World Python"
words = text.split()
print(words)  # Output: ['Hello', 'World', 'Python']
```

**Q: How do we join a list of strings into one string?**
A: By using the `.join()` method.
```python
words = ['Hello', 'World', 'Python']
text = " ".join(words)
print(text)  # Output: Hello World Python
```

**Q: How do we remove spaces from the beginning and end of a string?**
A: By using the `.strip()` method.
```python
text = "  Hello World  "
print(text.strip())  # Output: Hello World
```

---

## Lists and Collections

**Q: How do we create a list in Python?**
A: By using square brackets `[]`.
```python
my_list = [1, 2, 3, 4, 5]
print(my_list)  # Output: [1, 2, 3, 4, 5]
```

**Q: How do we access an element from a list?**
A: By using the index inside square brackets.
```python
my_list = ['a', 'b', 'c', 'd']
print(my_list[0])  # Output: a (first element)
print(my_list[-1])  # Output: d (last element)
```

**Q: How do we add an element to a list?**
A: By using the `.append()` method.
```python
my_list = [1, 2, 3]
my_list.append(4)
print(my_list)  # Output: [1, 2, 3, 4]
```

**Q: How do we remove an element from a list?**
A: By using the `.remove()` method or `pop()` method.
```python
my_list = [1, 2, 3, 4]
my_list.remove(2)  # Remove by value
print(my_list)  # Output: [1, 3, 4]

my_list.pop(1)  # Remove by index
print(my_list)  # Output: [1, 4]
```

**Q: How do we find the length of a list?**
A: By using the `len()` function.
```python
my_list = [1, 2, 3, 4, 5]
print(len(my_list))  # Output: 5
```

**Q: How do we sort a list?**
A: By using the `.sort()` method or `sorted()` function.
```python
my_list = [3, 1, 4, 1, 5]
my_list.sort()
print(my_list)  # Output: [1, 1, 3, 4, 5]

# Or use sorted() to create a new sorted list without modifying original
new_list = sorted([3, 1, 4, 1, 5])
print(new_list)  # Output: [1, 1, 3, 4, 5]
```

**Q: How do we reverse a list?**
A: By using the `.reverse()` method or slicing.
```python
my_list = [1, 2, 3, 4, 5]
my_list.reverse()
print(my_list)  # Output: [5, 4, 3, 2, 1]

# Or use slicing
my_list = [1, 2, 3, 4, 5]
reversed_list = my_list[::-1]
print(reversed_list)  # Output: [5, 4, 3, 2, 1]
```

**Q: How do we create a dictionary in Python?**
A: By using curly braces `{}` with key-value pairs.
```python
my_dict = {'name': 'John', 'age': 25, 'city': 'New York'}
print(my_dict)
```

**Q: How do we access a value from a dictionary?**
A: By using the key inside square brackets.
```python
my_dict = {'name': 'John', 'age': 25}
print(my_dict['name'])  # Output: John
print(my_dict.get('age'))  # Output: 25
```

**Q: How do we add a new key-value pair to a dictionary?**
A: By assigning a value to a new key.
```python
my_dict = {'name': 'John'}
my_dict['age'] = 25
print(my_dict)  # Output: {'name': 'John', 'age': 25}
```

**Q: How do we remove a key from a dictionary?**
A: By using the `del` keyword or `.pop()` method.
```python
my_dict = {'name': 'John', 'age': 25, 'city': 'New York'}
del my_dict['city']
print(my_dict)  # Output: {'name': 'John', 'age': 25}
```

---

## Loops and Conditions

**Q: How do we create a for loop in Python?**
A: By using the `for` keyword with an iterable.
```python
for i in range(5):
    print(i)  # Output: 0 1 2 3 4

for item in ['a', 'b', 'c']:
    print(item)  # Output: a b c
```

**Q: How do we create a while loop in Python?**
A: By using the `while` keyword with a condition.
```python
i = 0
while i < 5:
    print(i)
    i += 1  # Output: 0 1 2 3 4
```

**Q: How do we break out of a loop?**
A: By using the `break` keyword.
```python
for i in range(10):
    if i == 5:
        break
    print(i)  # Output: 0 1 2 3 4
```

**Q: How do we skip an iteration in a loop?**
A: By using the `continue` keyword.
```python
for i in range(5):
    if i == 2:
        continue
    print(i)  # Output: 0 1 3 4
```

**Q: How do we create an if-else statement?**
A: By using the `if`, `elif`, and `else` keywords.
```python
age = 18
if age < 13:
    print("Child")
elif age < 18:
    print("Teenager")
else:
    print("Adult")  # Output: Adult
```

**Q: How do we check multiple conditions?**
A: By using `and`, `or`, and `not` operators.
```python
age = 25
income = 50000

if age >= 18 and income >= 30000:
    print("Eligible for loan")  # Output: Eligible for loan

if age < 18 or income < 30000:
    print("Not eligible")

if not age < 18:
    print("Adult")  # Output: Adult
```

---

## Functions

**Q: How do we define a function in Python?**
A: By using the `def` keyword.
```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")  # Output: Hello, Alice!
```

**Q: How do we return a value from a function?**
A: By using the `return` keyword.
```python
def add(a, b):
    return a + b

result = add(5, 3)
print(result)  # Output: 8
```

**Q: How do we define a function with default parameters?**
A: By providing a default value in the function definition.
```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()  # Output: Hello, Guest!
greet("Bob")  # Output: Hello, Bob!
```

**Q: How do we define a function that accepts multiple arguments?**
A: By using `*args` or `**kwargs`.
```python
def add_numbers(*args):
    return sum(args)

print(add_numbers(1, 2, 3, 4, 5))  # Output: 15
```

**Q: How do we use keyword arguments in a function?**
A: By passing arguments with their parameter names.
```python
def student_info(name, age, city):
    print(f"Name: {name}, Age: {age}, City: {city}")

student_info(name="John", age=25, city="New York")
# Output: Name: John, Age: 25, City: New York
```

---

## File Operations

**Q: How do we read from a file in Python?**
A: By using the `open()` function with mode 'r'.
```python
with open('file.txt', 'r') as file:
    content = file.read()
    print(content)
```

**Q: How do we write to a file in Python?**
A: By using the `open()` function with mode 'w'.
```python
with open('file.txt', 'w') as file:
    file.write("Hello, World!")
```

**Q: How do we append to a file in Python?**
A: By using the `open()` function with mode 'a'.
```python
with open('file.txt', 'a') as file:
    file.write("\nNew line added")
```

**Q: How do we read a file line by line?**
A: By using a for loop with the file object.
```python
with open('file.txt', 'r') as file:
    for line in file:
        print(line.strip())
```

**Q: How do we work with JSON files?**
A: By using the `json` module.
```python
import json

# Writing to JSON
data = {'name': 'John', 'age': 25}
with open('data.json', 'w') as file:
    json.dump(data, file)

# Reading from JSON
with open('data.json', 'r') as file:
    data = json.load(file)
    print(data)
```

---

## Exception Handling

**Q: How do we handle errors in Python?**
A: By using try-except blocks.
```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ValueError:
    print("Please enter a valid number")
except ZeroDivisionError:
    print("Cannot divide by zero")
```

**Q: How do we catch all exceptions?**
A: By using a bare `except` clause or catching `Exception`.
```python
try:
    # code that might raise an exception
    pass
except Exception as e:
    print(f"An error occurred: {e}")
```

**Q: How do we use finally in exception handling?**
A: By using the `finally` block which always executes.
```python
try:
    file = open('file.txt', 'r')
    data = file.read()
except FileNotFoundError:
    print("File not found")
finally:
    file.close()  # Always executes
```

---

## Data Types and Conversion

**Q: How do we check the type of a variable?**
A: By using the `type()` function.
```python
x = 5
print(type(x))  # Output: <class 'int'>

y = "hello"
print(type(y))  # Output: <class 'str'>
```

**Q: How do we convert a string to an integer?**
A: By using the `int()` function.
```python
num_str = "42"
num = int(num_str)
print(num)  # Output: 42
print(type(num))  # Output: <class 'int'>
```

**Q: How do we convert a string to a float?**
A: By using the `float()` function.
```python
num_str = "3.14"
num = float(num_str)
print(num)  # Output: 3.14
```

**Q: How do we convert a number to a string?**
A: By using the `str()` function.
```python
num = 42
text = str(num)
print(text)  # Output: 42
print(type(text))  # Output: <class 'str'>
```

**Q: How do we convert a list to a tuple?**
A: By using the `tuple()` function.
```python
my_list = [1, 2, 3]
my_tuple = tuple(my_list)
print(my_tuple)  # Output: (1, 2, 3)
```

---

## Operators

**Q: What are the arithmetic operators in Python?**
A: `+` (addition), `-` (subtraction), `*` (multiplication), `/` (division), `//` (floor division), `%` (modulus), `**` (exponentiation).
```python
print(10 + 5)    # Output: 15
print(10 - 5)    # Output: 5
print(10 * 5)    # Output: 50
print(10 / 5)    # Output: 2.0
print(10 // 3)   # Output: 3
print(10 % 3)    # Output: 1
print(2 ** 3)    # Output: 8
```

**Q: What are the comparison operators in Python?**
A: `==` (equal), `!=` (not equal), `>` (greater), `<` (less), `>=` (greater or equal), `<=` (less or equal).
```python
print(5 == 5)    # Output: True
print(5 != 3)    # Output: True
print(5 > 3)     # Output: True
print(5 < 10)    # Output: True
```

**Q: What are the logical operators in Python?**
A: `and`, `or`, `not`.
```python
print(True and True)   # Output: True
print(True or False)   # Output: True
print(not True)        # Output: False
```

---

## Useful Built-in Functions

**Q: How do we generate a range of numbers?**
A: By using the `range()` function.
```python
for i in range(5):
    print(i)  # Output: 0 1 2 3 4

for i in range(1, 6):
    print(i)  # Output: 1 2 3 4 5

for i in range(0, 10, 2):
    print(i)  # Output: 0 2 4 6 8
```

**Q: How do we find the minimum and maximum values in a list?**
A: By using the `min()` and `max()` functions.
```python
numbers = [3, 1, 4, 1, 5, 9]
print(min(numbers))  # Output: 1
print(max(numbers))  # Output: 9
```

**Q: How do we sum all elements in a list?**
A: By using the `sum()` function.
```python
numbers = [1, 2, 3, 4, 5]
print(sum(numbers))  # Output: 15
```

**Q: How do we find the absolute value of a number?**
A: By using the `abs()` function.
```python
print(abs(-5))  # Output: 5
print(abs(3.14))  # Output: 3.14
```

**Q: How do we round a number?**
A: By using the `round()` function.
```python
print(round(3.14159))  # Output: 3
print(round(3.14159, 2))  # Output: 3.14
```

**Q: How do we enumerate through a list with indices?**
A: By using the `enumerate()` function.
```python
fruits = ['apple', 'banana', 'cherry']
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
# Output: 0: apple, 1: banana, 2: cherry
```

**Q: How do we zip two lists together?**
A: By using the `zip()` function.
```python
names = ['Alice', 'Bob', 'Charlie']
ages = [25, 30, 35]

for name, age in zip(names, ages):
    print(f"{name}: {age}")
# Output: Alice: 25, Bob: 30, Charlie: 35
```

---

## Object-Oriented Programming (OOP)

**Q: How do we create a class in Python?**
A: By using the `class` keyword.
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def greet(self):
        print(f"Hello, my name is {self.name}")

person = Person("John", 25)
person.greet()  # Output: Hello, my name is John
```

**Q: What is the `__init__` method?**
A: It's a constructor that initializes object attributes when creating an instance.
```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

my_car = Car("Toyota", "Camry")
print(my_car.brand)  # Output: Toyota
```

**Q: How do we create a method in a class?**
A: By defining a function inside the class with `self` as the first parameter.
```python
class Calculator:
    def add(self, a, b):
        return a + b
    
    def subtract(self, a, b):
        return a - b

calc = Calculator()
print(calc.add(5, 3))  # Output: 8
```

**Q: What is inheritance in a class?**
A: It's when a class inherits properties and methods from another class.
```python
class Animal:
    def sound(self):
        print("Some sound")

class Dog(Animal):
    def sound(self):
        print("Woof!")

dog = Dog()
dog.sound()  # Output: Woof!
```

---

## Regular Expressions

**Q: How do we use regular expressions in Python?**
A: By using the `re` module.
```python
import re

text = "My email is john@example.com"
pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
result = re.search(pattern, text)
print(result.group())  # Output: john@example.com
```

**Q: How do we find all matches of a pattern?**
A: By using the `re.findall()` function.
```python
import re

text = "apple banana apple cherry apple"
pattern = "apple"
matches = re.findall(pattern, text)
print(matches)  # Output: ['apple', 'apple', 'apple']
```

**Q: How do we replace text using regex?**
A: By using the `re.sub()` function.
```python
import re

text = "Hello 123 World 456"
new_text = re.sub(r'\d+', 'X', text)
print(new_text)  # Output: Hello X World X
```

---

## Frequently Asked Questions

**Q: How do we get user input in Python?**
A: By using the `input()` function.
```python
name = input("Enter your name: ")
print(f"Hello, {name}")
```

**Q: How do we create a comment in Python?**
A: By using the `#` symbol for single-line comments or triple quotes for multi-line comments.
```python
# Single line comment
print("Hello")  # Comment here

"""
Multi-line comment
This is a longer explanation
"""
```

**Q: How do we import a module in Python?**
A: By using the `import` keyword.
```python
import math
print(math.sqrt(16))  # Output: 4.0

from math import pi
print(pi)  # Output: 3.141592653589793
```

**Q: How do we check if a file exists?**
A: By using the `os.path` module.
```python
import os

if os.path.exists('file.txt'):
    print("File exists")
else:
    print("File does not exist")
```

**Q: How do we get the current date and time?**
A: By using the `datetime` module.
```python
from datetime import datetime

now = datetime.now()
print(now)  # Output: 2024-01-15 14:30:45.123456
print(now.year)  # Output: 2024
print(now.month)  # Output: 1
print(now.day)  # Output: 15
```

**Q: How do we create a list comprehension?**
A: By using square brackets with a for loop inside.
```python
numbers = [1, 2, 3, 4, 5]
squared = [x**2 for x in numbers]
print(squared)  # Output: [1, 4, 9, 16, 25]

# With condition
evens = [x for x in numbers if x % 2 == 0]
print(evens)  # Output: [2, 4]
```

**Q: How do we use lambda functions?**
A: Lambda functions are small anonymous functions using the `lambda` keyword.
```python
square = lambda x: x**2
print(square(5))  # Output: 25

numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x**2, numbers))
print(squared)  # Output: [1, 4, 9, 16, 25]
```

---

*Keep practicing and exploring Python. The more you code, the better you'll become!*


