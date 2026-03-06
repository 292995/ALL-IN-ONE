# Python Notes for Beginners: Project-Based Learning

Welcome to Python! This guide is designed for absolute beginners and uses a project-based approach to learn Python. Each section introduces new concepts through hands-on projects.

## Table of Contents
1. [Introduction to Python](#introduction-to-python)
2. [Setting Up Python](#setting-up-python)
3. [Project 1: Hello World](#project-1-hello-world)
4. [Project 2: Simple Calculator](#project-2-simple-calculator)
5. [Project 3: Number Guessing Game](#project-3-number-guessing-game)
6. [Project 4: To-Do List Application](#project-4-to-do-list-application)
7. [Project 5: Contact Book with File Handling](#project-5-contact-book-with-file-handling)
8. [Project 6: Weather App with API](#project-6-weather-app-with-api)
9. [Next Steps](#next-steps)

## Introduction to Python

Python is a high-level, interpreted programming language known for its simplicity and readability. It's widely used for:
- Web development
- Data analysis
- Machine learning
- Automation
- Game development
- And much more!

### Why Python for Beginners?
- Easy to learn syntax
- Large community and resources
- Versatile applications
- High demand in job market

## Setting Up Python

### Installation
1. Download Python from [python.org](https://python.org)
2. Follow the installation instructions for your operating system
3. Verify installation by opening terminal/command prompt and typing:
   ```bash
   python --version
   ```

### IDE/Editor
You can use:
- IDLE (comes with Python)
- Visual Studio Code
- PyCharm
- Jupyter Notebook

For this guide, we'll use simple text files and run them from command line.

## Project 1: Hello World

**Objective:** Learn basic Python syntax, print statements, and user input.

**Concepts Covered:**
- Comments
- Print function
- Input function
- Variables
- String concatenation

**Code:**
```python
# This is a comment - Python ignores lines starting with #

# Print a simple message
print("Hello, World!")

# Get user input
name = input("What's your name? ")
print("Hello, " + name + "!")

# Alternative way using f-strings (Python 3.6+)
print(f"Hello, {name}!")
```

**How to Run:**
1. Create a file called `hello.py`
2. Copy the code above
3. Open terminal in the same directory
4. Run: `python hello.py`

**Exercises:**
1. Modify the program to ask for age and print a birthday message
2. Add more questions and personalize the greeting

## Project 2: Simple Calculator

**Objective:** Learn arithmetic operations, data types, and basic logic.

**Concepts Covered:**
- Numbers (int, float)
- Arithmetic operators (+, -, *, /, //, %, **)
- Type conversion
- Basic error handling

**Code:**
```python
print("Simple Calculator")
print("Operations: +, -, *, /, //, %, **")

# Get user input
num1 = float(input("Enter first number: "))
operation = input("Enter operation: ")
num2 = float(input("Enter second number: "))

# Perform calculation
if operation == "+":
    result = num1 + num2
elif operation == "-":
    result = num1 - num2
elif operation == "*":
    result = num1 * num2
elif operation == "/":
    if num2 != 0:
        result = num1 / num2
    else:
        result = "Error: Division by zero"
elif operation == "//":
    if num2 != 0:
        result = num1 // num2
    else:
        result = "Error: Division by zero"
elif operation == "%":
    if num2 != 0:
        result = num1 % num2
    else:
        result = "Error: Division by zero"
elif operation == "**":
    result = num1 ** num2
else:
    result = "Invalid operation"

print(f"Result: {result}")
```

**How to Run:**
1. Save as `calculator.py`
2. Run: `python calculator.py`

**Exercises:**
1. Add square root operation using `** 0.5`
2. Add memory function (store result for next calculation)
3. Handle more edge cases

## Project 3: Number Guessing Game

**Objective:** Learn loops, conditionals, and random numbers.

**Concepts Covered:**
- While loops
- If/elif/else statements
- Random module
- Break and continue statements
- Boolean logic

**Code:**
```python
import random

print("Number Guessing Game!")
print("I'm thinking of a number between 1 and 100")

# Generate random number
secret_number = random.randint(1, 100)
attempts = 0
max_attempts = 10

while attempts < max_attempts:
    try:
        guess = int(input("Enter your guess: "))
        attempts += 1
        
        if guess < secret_number:
            print("Too low! Try again.")
        elif guess > secret_number:
            print("Too high! Try again.")
        else:
            print(f"Congratulations! You guessed it in {attempts} attempts!")
            break
    except ValueError:
        print("Please enter a valid number!")

if attempts == max_attempts and guess != secret_number:
    print(f"Sorry, you've used all {max_attempts} attempts. The number was {secret_number}.")
```

**How to Run:**
1. Save as `guessing_game.py`
2. Run: `python guessing_game.py`

**Exercises:**
1. Add difficulty levels (easy: 1-50, hard: 1-200)
2. Keep track of high scores
3. Add hints (even/odd, range narrowing)

## Project 4: To-Do List Application

**Objective:** Learn lists, dictionaries, and basic data structures.

**Concepts Covered:**
- Lists
- Dictionaries
- List methods (append, remove, etc.)
- Dictionary operations
- Loops with lists
- String formatting

**Code:**
```python
# To-Do List Application

todo_list = []

def show_menu():
    print("\n=== To-Do List Menu ===")
    print("1. Add task")
    print("2. View tasks")
    print("3. Mark task as complete")
    print("4. Delete task")
    print("5. Exit")

def add_task():
    task = input("Enter task description: ")
    priority = input("Enter priority (high/medium/low): ").lower()
    todo_list.append({
        "task": task,
        "priority": priority,
        "completed": False
    })
    print("Task added successfully!")

def view_tasks():
    if not todo_list:
        print("No tasks in your list!")
        return
    
    print("\n=== Your Tasks ===")
    for i, task in enumerate(todo_list, 1):
        status = "✓" if task["completed"] else "○"
        print(f"{i}. [{status}] {task['task']} (Priority: {task['priority']})")

def mark_complete():
    view_tasks()
    try:
        task_num = int(input("Enter task number to mark complete: ")) - 1
        if 0 <= task_num < len(todo_list):
            todo_list[task_num]["completed"] = True
            print("Task marked as complete!")
        else:
            print("Invalid task number!")
    except ValueError:
        print("Please enter a valid number!")

def delete_task():
    view_tasks()
    try:
        task_num = int(input("Enter task number to delete: ")) - 1
        if 0 <= task_num < len(todo_list):
            deleted_task = todo_list.pop(task_num)
            print(f"Deleted task: {deleted_task['task']}")
        else:
            print("Invalid task number!")
    except ValueError:
        print("Please enter a valid number!")

# Main program loop
while True:
    show_menu()
    choice = input("Enter your choice (1-5): ")
    
    if choice == "1":
        add_task()
    elif choice == "2":
        view_tasks()
    elif choice == "3":
        mark_complete()
    elif choice == "4":
        delete_task()
    elif choice == "5":
        print("Goodbye!")
        break
    else:
        print("Invalid choice! Please try again.")
```

**How to Run:**
1. Save as `todo_list.py`
2. Run: `python todo_list.py`

**Exercises:**
1. Add due dates to tasks
2. Sort tasks by priority
3. Save/load tasks from file

## Project 5: Contact Book with File Handling

**Objective:** Learn file operations and data persistence.

**Concepts Covered:**
- File reading/writing
- JSON data format
- Exception handling
- Data validation
- os module for file operations

**Code:**
```python
import json
import os

CONTACTS_FILE = "contacts.json"

def load_contacts():
    if os.path.exists(CONTACTS_FILE):
        try:
            with open(CONTACTS_FILE, 'r') as file:
                return json.load(file)
        except json.JSONDecodeError:
            print("Error loading contacts file. Starting with empty contacts.")
            return {}
    return {}

def save_contacts(contacts):
    try:
        with open(CONTACTS_FILE, 'w') as file:
            json.dump(contacts, file, indent=4)
        print("Contacts saved successfully!")
    except Exception as e:
        print(f"Error saving contacts: {e}")

def add_contact(contacts):
    name = input("Enter name: ").strip()
    if not name:
        print("Name cannot be empty!")
        return
    
    phone = input("Enter phone number: ").strip()
    email = input("Enter email: ").strip()
    
    contacts[name] = {
        "phone": phone,
        "email": email
    }
    print(f"Contact {name} added!")

def view_contacts(contacts):
    if not contacts:
        print("No contacts found!")
        return
    
    print("\n=== Contacts ===")
    for name, info in contacts.items():
        print(f"Name: {name}")
        print(f"Phone: {info['phone']}")
        print(f"Email: {info['email']}")
        print("-" * 20)

def search_contact(contacts):
    search_term = input("Enter name to search: ").lower()
    found = False
    
    for name, info in contacts.items():
        if search_term in name.lower():
            print(f"Name: {name}")
            print(f"Phone: {info['phone']}")
            print(f"Email: {info['email']}")
            print("-" * 20)
            found = True
    
    if not found:
        print("No contacts found matching your search.")

def delete_contact(contacts):
    name = input("Enter name to delete: ").strip()
    if name in contacts:
        del contacts[name]
        print(f"Contact {name} deleted!")
    else:
        print("Contact not found!")

# Main program
contacts = load_contacts()

while True:
    print("\n=== Contact Book ===")
    print("1. Add contact")
    print("2. View all contacts")
    print("3. Search contact")
    print("4. Delete contact")
    print("5. Save and exit")
    
    choice = input("Enter your choice (1-5): ")
    
    if choice == "1":
        add_contact(contacts)
    elif choice == "2":
        view_contacts(contacts)
    elif choice == "3":
        search_contact(contacts)
    elif choice == "4":
        delete_contact(contacts)
    elif choice == "5":
        save_contacts(contacts)
        print("Goodbye!")
        break
    else:
        print("Invalid choice!")
```

**How to Run:**
1. Save as `contact_book.py`
2. Run: `python contact_book.py`

**Exercises:**
1. Add contact categories/groups
2. Export contacts to CSV format
3. Add contact editing functionality

## Project 6: Weather App with API

**Objective:** Learn API calls, JSON parsing, and external libraries.

**Concepts Covered:**
- HTTP requests
- API integration
- Environment variables
- Error handling
- External libraries (requests)

**Setup:**
First, install the requests library:
```bash
pip install requests
```

**Code:**
```python
import requests
import json

# You'll need to get a free API key from https://openweathermap.org/api
# For this example, we'll use a demo API that doesn't require a key
API_KEY = "your_api_key_here"  # Replace with your actual API key
BASE_URL = "http://api.openweathermap.org/data/2.5/weather"

def get_weather(city_name):
    """Get weather information for a city"""
    try:
        # Make API request
        params = {
            'q': city_name,
            'appid': API_KEY,
            'units': 'metric'  # Use Celsius
        }
        
        response = requests.get(BASE_URL, params=params)
        response.raise_for_status()  # Raise exception for bad status codes
        
        data = response.json()
        
        # Extract relevant information
        city = data['name']
        country = data['sys']['country']
        temp = data['main']['temp']
        humidity = data['main']['humidity']
        description = data['weather'][0]['description']
        wind_speed = data['wind']['speed']
        
        # Display weather information
        print(f"\nWeather in {city}, {country}:")
        print(f"Temperature: {temp}°C")
        print(f"Humidity: {humidity}%")
        print(f"Description: {description.capitalize()}")
        print(f"Wind Speed: {wind_speed} m/s")
        
    except requests.exceptions.RequestException as e:
        print(f"Error fetching weather data: {e}")
    except KeyError as e:
        print(f"Error parsing weather data: {e}")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

def main():
    print("Weather App")
    print("Get current weather information for any city!")
    
    while True:
        city = input("\nEnter city name (or 'quit' to exit): ").strip()
        
        if city.lower() == 'quit':
            break
        
        if city:
            get_weather(city)
        else:
            print("Please enter a valid city name.")

if __name__ == "__main__":
    main()
```

**Note:** To use this app, you'll need to:
1. Sign up at [OpenWeatherMap](https://openweathermap.org/api)
2. Get a free API key
3. Replace `"your_api_key_here"` with your actual key

**How to Run:**
1. Save as `weather_app.py`
2. Install requests: `pip install requests`
3. Run: `python weather_app.py`

**Exercises:**
1. Add 5-day forecast functionality
2. Save favorite cities
3. Add weather icons/emojis based on conditions

## Next Steps

Congratulations! You've completed the basic projects. Here are some next steps:

### Advanced Topics to Explore:
- Object-Oriented Programming (classes, objects, inheritance)
- List comprehensions and generators
- Regular expressions
- Database integration (SQLite, MongoDB)
- Web frameworks (Flask, Django)
- GUI development (Tkinter, PyQt)
- Testing (unittest, pytest)

### Recommended Resources:
- [Python Official Documentation](https://docs.python.org/3/)
- [Automate the Boring Stuff with Python](https://automatetheboringstuff.com/)
- [Python Crash Course](https://nostarch.com/pythoncrashcourse)
- [Codecademy Python Course](https://www.codecademy.com/learn/learn-python-3)
- [freeCodeCamp Python Tutorial](https://www.freecodecamp.org/learn/scientific-computing-with-python/)

### Practice Platforms:
- [LeetCode](https://leetcode.com/)
- [HackerRank](https://www.hackerrank.com/)
- [CodeWars](https://www.codewars.com/)
- [Exercism](https://exercism.org/tracks/python)

### Build More Projects:
- Web scraper
- Simple blog
- Chat application
- Data visualization dashboard
- Game development with Pygame

Remember: The best way to learn is by doing. Keep building projects and don't be afraid to experiment!
