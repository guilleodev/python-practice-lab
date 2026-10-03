# 🐍 Python Basics - Theory

Python is a programming language known for its simple and readable syntax.

In this first module, you will learn the basic building blocks needed to create simple Python programs.

## 📚 Contents

- [1. Getting Started with Python](#1-getting-started-with-python)
- [2. Variables and Data Types](#2-variables-and-data-types)
- [3. Working with Numbers](#3-working-with-numbers)
- [4. Working with Text](#4-working-with-text)
- [5. User Input and Type Conversion](#5-user-input-and-type-conversion)
- [6. Putting It All Together](#6-putting-it-all-together)
- [📌 Cheat Sheet: 01 Basics](#-cheat-sheet-01-basics)

## 1. Getting Started with Python

### 1.1 Your First Python Program

The `print()` function displays information on the screen.

```python
print("Welcome to Python!")
```

Output:

```text
Welcome to Python!
```

You can print text, numbers and other values:

```python
print("Game started!")
print(100)
print(25 + 10)
```

### 1.2 Comments

Comments are notes inside your code that Python does not execute.

A single-line comment starts with `#`:

```python
# Player starting health
health = 100

# Show health on screen
print(health)
```

Comments are useful for explaining parts of your code and making it easier to understand.

## 2. Variables and Data Types

### 2.1 Variables

Variables are used to store values that can be used later in the program.

```python
health = 100
mana = 80
gold = 50
```

A variable has a **name** and a **value**:

```python
health = 100
```

Here:

- `health` → variable name
- `=` → assignment operator
- `100` → value

The `=` symbol assigns the value on the right to the variable on the left.

### 2.2 Changing Variables

The value stored in a variable can change while the program is running.

```python
health = 100
health = 75

print(health)
```

Output:

```text
75
```

The original value `100` has been replaced by `75`.

Variables can also be updated using their current value:

```python
gold = 50
quest_reward = 20

gold = gold + quest_reward

print(gold)
```

Output:

```text
70
```

### 2.3 Naming Variables

Variable names should describe the information they contain.

Python commonly uses **snake_case**, where words are separated with underscores:

```python
player_name = "Arthas"
enemy_health = 100
quest_reward = 25
```

Good variable names make code easier to understand.

```python
# Clear
enemy_health = 100

# Not very clear
x = 100
```

Variable names:

- Can contain letters, numbers and `_`
- Cannot start with a number
- Cannot contain spaces
- Are case-sensitive

For example, `health` and `Health` are different variables.

### 2.4 Basic Data Types

Values in Python have different **data types**.

| Type | Description | Example |
|---|---|---|
| `str` | Text | `"Mage"` |
| `int` | Integer number | `100` |
| `float` | Decimal number | `75.5` |
| `bool` | True or false | `True` |

Example:

```python
player_class = "Mage"       # str
level = 20                  # int
health = 87.5               # float
quest_completed = True      # bool
```

### 2.5 Checking Data Types

The `type()` function tells you the data type of a value.

```python
level = 20
health = 87.5

print(type(level))
print(type(health))
```

Output:

```text
<class 'int'>
<class 'float'>
```

## 3. Working with Numbers

### 3.1 Arithmetic Operators

Python can perform mathematical operations using arithmetic operators.

| Operator | Operation | Example | Result |
|---|---|---|---|
| `+` | Addition | `10 + 5` | `15` |
| `-` | Subtraction | `10 - 5` | `5` |
| `*` | Multiplication | `10 * 5` | `50` |
| `/` | Division | `10 / 5` | `2.0` |
| `//` | Floor division | `10 // 3` | `3` |
| `%` | Remainder | `10 % 3` | `1` |
| `**` | Power | `10 ** 2` | `100` |

These operators can be used with variables:

```python
enemy_health = 100
damage = 25

remaining_health = enemy_health - damage

print(remaining_health)
```

Output:

```text
75
```

### 3.2 Division and Remainder

The `/` operator performs normal division:

```python
gold = 100
players = 4

gold_per_player = gold / players

print(gold_per_player)
```

Output:

```text
25.0
```

The `//` operator performs **floor division**, removing the decimal part:

```python
print(10 // 3)
```

Output:

```text
3
```

The `%` operator returns the **remainder** of a division:

```python
print(10 % 3)
```

Output:

```text
1
```

### 3.3 Order of Operations

Python follows the normal mathematical order of operations.

```python
result = 10 + 5 * 2

print(result)
```

Output:

```text
20
```

Parentheses can be used to change the order:

```python
result = (10 + 5) * 2

print(result)
```

Output:

```text
30
```

Using parentheses can also make calculations easier to read.

## 4. Working with Text

### 4.1 Strings

Text in Python is represented using the `str` data type.

Strings can use double or single quotes:

```python
player_class = "Mage"
enemy = 'Dragon'
```

Both are valid.

### 4.2 Combining Strings

Strings can be combined using the `+` operator.

```python
player_name = "Arthas"
player_class = "Paladin"

character = player_name + " - " + player_class

print(character)
```

Output:

```text
Arthas - Paladin
```

This is called **string concatenation**.

### 4.3 F-Strings

F-strings provide an easier way to insert variables inside text.

Add `f` before the string and place variables inside `{}`:

```python
player_name = "Arthas"
level = 20

print(f"{player_name} is level {level}.")
```

Output:

```text
Arthas is level 20.
```

Expressions can also be used inside `{}`:

```python
gold = 50
quest_reward = 20

print(f"Gold after quest: {gold + quest_reward}")
```

Output:

```text
Gold after quest: 70
```

## 5. User Input and Type Conversion

### 5.1 Getting User Input

The `input()` function allows the user to enter information while the program is running.

```python
player_name = input("Enter your character name: ")

print(f"Welcome, {player_name}!")
```

The program waits until the user enters a value.

### 5.2 Understanding `input()`

`input()` always returns a **string**, even when the user enters a number.

```python
level = input("Enter your level: ")

print(type(level))
```

If the user enters `20`, Python still stores it as:

```text
"20"
```

not:

```text
20
```

This is important when we want to perform calculations.

### 5.3 Type Conversion

Python allows values to be converted from one data type to another.

Common conversions are:

| Function | Converts to |
|---|---|
| `int()` | Integer |
| `float()` | Decimal number |
| `str()` | String |
| `bool()` | Boolean |

For example:

```python
level = int(input("Enter your level: "))
```

The process is:

```text
User enters "20"
        ↓
input() returns "20"
        ↓
int("20")
        ↓
20
```

The same idea works with decimal numbers:

```python
gold = float(input("Enter your gold: "))
```

Now the value can be used in calculations.

## 6. Putting It All Together

The concepts from this module can already be combined to create simple interactive programs.

```python
player_name = input("Character name: ")
level = int(input("Character level: "))
gold = float(input("Current gold: "))
quest_reward = float(input("Quest reward: "))

total_gold = gold + quest_reward

print(f"{player_name} - Level {level}")
print(f"Gold after completing the quest: {total_gold}")
```

This small program uses:

- Variables
- Strings
- Integers and floats
- `input()`
- Type conversion
- Arithmetic operators
- F-strings
- `print()`

## 📌 Cheat Sheet: 01 Basics

```python
# Variables
health = 100
mana = 80
level = 20

# Basic data types
player_class = "Mage"       # str
level = 20                  # int
health = 87.5               # float
quest_completed = True      # bool

# Check data type
print(type(level))

# Output
print("Game started!")

# User input
player_name = input("Character name: ")

# Type conversion
level = int(input("Level: "))
gold = float(input("Gold: "))

# Arithmetic
total_gold = 50 + 20
remaining_health = 100 - 25
total_damage = 10 * 3
shared_gold = 100 / 4
floor_division = 10 // 3
remainder = 10 % 3
power = 10 ** 2

# Strings
player_name = "Arthas"
player_class = "Paladin"
character = player_name + " - " + player_class

# F-string
print(f"{player_name} is level {level}.")
```

## 🧩 Next Step

➡️ [Continue with the exercises](exercises.md)

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>