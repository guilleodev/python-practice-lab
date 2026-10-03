# ⚡ Python Comprehensions - Theory

Comprehensions provide a shorter way to create collections from other data.

They are commonly used to transform, filter and generate values using compact Python syntax.

## 📚 Contents

- [1. Understanding Comprehensions](#1-understanding-comprehensions)
- [2. List Comprehensions](#2-list-comprehensions)
- [3. Transforming Values](#3-transforming-values)
- [4. Filtering Values](#4-filtering-values)
- [5. If / Else in Comprehensions](#5-if--else-in-comprehensions)
- [6. Nested Loops](#6-nested-loops)
- [7. Dictionary Comprehensions](#7-dictionary-comprehensions)
- [8. Set Comprehensions](#8-set-comprehensions)
- [9. Generator Expressions](#9-generator-expressions)
- [10. When to Use Comprehensions](#10-when-to-use-comprehensions)
- [📌 Cheat Sheet: 06 Comprehensions](#-cheat-sheet-06-comprehensions)

## 1. Understanding Comprehensions

Imagine we have a list of numbers:

```python
numbers = [1, 2, 3, 4]
```

We want to create another list containing each number multiplied by `2`.

Using a traditional loop:

```python
numbers = [1, 2, 3, 4]

doubled_numbers = []

for number in numbers:
    doubled_numbers.append(number * 2)

print(doubled_numbers)
```

Output:

```text
[2, 4, 6, 8]
```

A **list comprehension** allows us to write the same operation in one expression:

```python
numbers = [1, 2, 3, 4]

doubled_numbers = [number * 2 for number in numbers]

print(doubled_numbers)
```

The result is exactly the same:

```text
[2, 4, 6, 8]
```

The comprehension is not doing something completely different.

It is simply a more compact way of expressing a common loop pattern.

## 2. List Comprehensions

The basic structure of a list comprehension is:

```python
new_list = [expression for element in collection]
```

For example:

```python
levels = [1, 2, 3, 4, 5]

new_levels = [level + 1 for level in levels]

print(new_levels)
```

Output:

```text
[2, 3, 4, 5, 6]
```

We can read:

```python
[level + 1 for level in levels]
```

as:

```text
For every level in levels,
take level + 1
and store the result in a new list.
```

The traditional version would be:

```python
new_levels = []

for level in levels:
    new_levels.append(level + 1)
```

Both versions produce the same result.

### 2.1 Using `range()`

Comprehensions can also work with `range()`.

```python
numbers = [number for number in range(1, 6)]

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

We can transform the values directly:

```python
squares = [number ** 2 for number in range(1, 6)]

print(squares)
```

Output:

```text
[1, 4, 9, 16, 25]
```

## 3. Transforming Values

One of the most common uses of comprehensions is transforming data.

For example:

```python
damage = [10, 20, 30, 40]

double_damage = [value * 2 for value in damage]

print(double_damage)
```

Output:

```text
[20, 40, 60, 80]
```

Another example:

```python
names = ["jaina", "valeera", "arthas"]

formatted_names = [name.upper() for name in names]

print(formatted_names)
```

Output:

```text
['JAINA', 'VALEERA', 'ARTHAS']
```

We are creating a **new list**.

The original list remains unchanged.

```python
print(names)
```

Output:

```text
['jaina', 'valeera', 'arthas']
```

## 4. Filtering Values

Comprehensions can include a condition.

Suppose we only want numbers greater than `20`.

Traditional version:

```python
damage_values = [10, 25, 15, 40, 30]

high_damage = []

for damage in damage_values:
    if damage > 20:
        high_damage.append(damage)
```

Using a comprehension:

```python
damage_values = [10, 25, 15, 40, 30]

high_damage = [
    damage
    for damage in damage_values
    if damage > 20
]
```

Output:

```text
[25, 40, 30]
```

The basic structure is:

```python
new_list = [
    expression
    for element in collection
    if condition
]
```

Another example:

```python
levels = [5, 10, 15, 20, 25]

high_levels = [level for level in levels if level >= 15]

print(high_levels)
```

Output:

```text
[15, 20, 25]
```

### 4.1 Filtering Even Numbers

The remainder operator `%` is useful for checking whether a number is even.

```python
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = [
    number
    for number in numbers
    if number % 2 == 0
]

print(even_numbers)
```

Output:

```text
[2, 4, 6]
```

## 5. If / Else in Comprehensions

A comprehension can also choose between two values.

Suppose we want to keep even numbers and replace odd numbers with `0`.

Traditional version:

```python
numbers = [1, 2, 3, 4, 5]

result = []

for number in numbers:
    if number % 2 == 0:
        result.append(number)
    else:
        result.append(0)
```

Using a comprehension:

```python
numbers = [1, 2, 3, 4, 5]

result = [
    number if number % 2 == 0 else 0
    for number in numbers
]

print(result)
```

Output:

```text
[0, 2, 0, 4, 0]
```

Notice that the position of the condition changes.

Filtering:

```python
[number for number in numbers if number % 2 == 0]
```

This means:

```text
Keep only the even numbers.
```

Using `if / else`:

```python
[number if number % 2 == 0 else 0 for number in numbers]
```

This means:

```text
Keep the number if it is even.
Otherwise use 0.
```

This distinction is important.

## 6. Nested Loops

Comprehensions can also contain more than one loop.

Suppose we want to generate combinations of character classes and roles.

Traditional version:

```python
classes = ["Mage", "Warrior"]
roles = ["DPS", "Support"]

combinations = []

for player_class in classes:
    for role in roles:
        combinations.append(
            f"{player_class} - {role}"
        )
```

Using a comprehension:

```python
combinations = [
    f"{player_class} - {role}"
    for player_class in classes
    for role in roles
]

print(combinations)
```

Output:

```text
[
    'Mage - DPS',
    'Mage - Support',
    'Warrior - DPS',
    'Warrior - Support'
]
```

The loops appear in the same order as the traditional version:

```python
for player_class in classes:
    for role in roles:
```

becomes:

```python
[
    ...
    for player_class in classes
    for role in roles
]
```

> [!NOTE]
> Nested comprehensions can quickly become difficult to read. A traditional loop is often better when the logic becomes complex.

## 7. Dictionary Comprehensions

Comprehensions can also create dictionaries.

The basic structure is:

```python
new_dictionary = {
    key: value
    for element in collection
}
```

For example:

```python
levels = [10, 20, 30]

experience = {
    level: level * 100
    for level in levels
}

print(experience)
```

Output:

```text
{10: 1000, 20: 2000, 30: 3000}
```

Each level becomes a key.

The calculated experience becomes its value.

Another example:

```python
players = ["Jaina", "Valeera", "Arthas"]

player_health = {
    player: 100
    for player in players
}

print(player_health)
```

Output:

```text
{
    'Jaina': 100,
    'Valeera': 100,
    'Arthas': 100
}
```

### 7.1 Filtering Dictionaries

Conditions can also be used:

```python
players = {
    "Jaina": 100,
    "Valeera": 70,
    "Arthas": 0
}

active_players = {
    name: health
    for name, health in players.items()
    if health > 0
}

print(active_players)
```

Output:

```text
{
    'Jaina': 100,
    'Valeera': 70
}
```

## 8. Set Comprehensions

Set comprehensions use `{}`.

```python
numbers = [1, 2, 2, 3, 3, 4]

unique_doubles = {
    number * 2
    for number in numbers
}

print(unique_doubles)
```

The result contains only unique values.

```text
{2, 4, 6, 8}
```

The basic structure is:

```python
new_set = {
    expression
    for element in collection
}
```

We can also filter values:

```python
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = {
    number
    for number in numbers
    if number % 2 == 0
}
```

Output:

```text
{2, 4, 6}
```

## 9. Generator Expressions

A **generator expression** looks similar to a list comprehension.

The main visual difference is:

```text
List comprehension   -> [ ]

Generator expression -> ( )
```

For example:

```python
numbers = [number for number in range(10)]
```

creates a list.

But:

```python
numbers = (number for number in range(10))
```

creates a generator.

### 9.1 What Is a Generator?

A list creates and stores all its elements in memory.

```python
numbers = [number for number in range(1_000_000)]
```

Python creates the entire list.

A generator works differently:

```python
numbers = (number for number in range(1_000_000))
```

It produces values **when they are needed** instead of storing the entire result at once.

A simple way to think about it:

```text
List

Create everything
↓
Store everything
↓
Use the values


Generator

Create one value
↓
Use it
↓
Create the next value
↓
Use it
↓
...
```

This can be useful when working with a large amount of data.

### 9.2 Using a Generator

A generator can be used in a loop:

```python
numbers = (number * 2 for number in range(5))

for number in numbers:
    print(number)
```

Output:

```text
0
2
4
6
8
```

Generators are especially useful when:

```text
There are many values
You do not need all values at the same time
You want to avoid storing a large collection in memory
```

> [!NOTE]
> For small collections, a normal list is often simpler. Generators become especially useful when the amount of data grows.

## 10. When to Use Comprehensions

Comprehensions are useful when the operation is simple and easy to understand.

Good example:

```python
squares = [number ** 2 for number in numbers]
```

Good example with filtering:

```python
active_players = [
    player
    for player in players
    if player["health"] > 0
]
```

But not every loop should become a comprehension.

If the logic contains many conditions or several actions, a normal loop is usually easier to read.

For example:

```python
for player in players:
    if player["health"] <= 0:
        print(f"{player['name']} is defeated.")
    else:
        player["health"] = player["health"] + 20
        print(f"{player['name']} recovered health.")
```

Trying to force everything into one comprehension would make the code harder to understand.

A useful rule is:

```text
Simple transformation -> comprehension

Simple filtering      -> comprehension

Complex logic         -> traditional loop
```

The goal is not to write the shortest code possible.

The goal is to write code that is clear and useful.

## 📌 Cheat Sheet: 06 Comprehensions

```python
# LIST COMPREHENSION
numbers = [1, 2, 3, 4]

doubled = [number * 2 for number in numbers]

# USING RANGE
numbers = [number for number in range(1, 6)]

squares = [number ** 2 for number in range(1, 6)]

# FILTERING
numbers = [1, 2, 3, 4, 5, 6]

even_numbers = [
    number
    for number in numbers
    if number % 2 == 0
]

# IF / ELSE
result = [
    number if number % 2 == 0 else 0
    for number in numbers
]

# NESTED LOOPS
classes = ["Mage", "Warrior"]
roles = ["DPS", "Support"]

combinations = [
    f"{player_class} - {role}"
    for player_class in classes
    for role in roles
]

# DICTIONARY COMPREHENSION
levels = [10, 20, 30]

experience = {
    level: level * 100
    for level in levels
}

# FILTERING A DICTIONARY
players = {
    "Jaina": 100,
    "Valeera": 70,
    "Arthas": 0
}

active_players = {
    name: health
    for name, health in players.items()
    if health > 0
}

# SET COMPREHENSION
numbers = [1, 2, 2, 3, 3, 4]

unique_doubles = {
    number * 2
    for number in numbers
}

# GENERATOR EXPRESSION
numbers = (
    number * 2
    for number in range(1_000_000)
)

for number in numbers:
    print(number)

# GENERAL STRUCTURES

# List
new_list = [
    expression
    for element in collection
]

# List with filter
new_list = [
    expression
    for element in collection
    if condition
]

# List with if / else
new_list = [
    value_if_true if condition else value_if_false
    for element in collection
]

# Dictionary
new_dictionary = {
    key: value
    for element in collection
}

# Set
new_set = {
    expression
    for element in collection
}

# Generator
generator = (
    expression
    for element in collection
)
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