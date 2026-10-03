# ⚡ Python Foundations Cheatsheets

Quick reference for the Python concepts covered in **Python Practice Lab**.

This document collects the essential syntax and examples from each Python Foundations module in one place.

> [!NOTE]
> This cheatsheet grows alongside the repository and is updated as new topics are added.

## 📚 Contents

- [01: Python Basics](#01-python-basics)
- [02: Conditionals](#02-conditionals)
- [03: Loops](#03-loops)
- [04: Data Structures](#04-data-structures)
- [05: Functions](#05-functions)
- [06: Comprehensions](#06-comprehensions)

## 01: Python Basics

```python
# VARIABLES
health = 100
mana = 80
level = 20

# BASIC DATA TYPES
player_class = "Mage"       # str
level = 20                  # int
health = 87.5               # float
quest_completed = True      # bool

# CHECK DATA TYPE
print(type(level))

# OUTPUT
print("Game started!")

# USER INPUT
player_name = input("Character name: ")

# TYPE CONVERSION
level = int(input("Level: "))
gold = float(input("Gold: "))

# ARITHMETIC
total_gold = 50 + 20
remaining_health = 100 - 25
total_damage = 10 * 3
shared_gold = 100 / 4
floor_division = 10 // 3
remainder = 10 % 3
power = 10 ** 2

# STRINGS
player_name = "Arthas"
player_class = "Paladin"
character = player_name + " - " + player_class

# F-STRINGS
print(f"{player_name} is level {level}.")
```

⬆️ [Back to Contents](#contents)

## 02: Conditionals

```python
# COMPARISON OPERATORS
x == y    # Equal to
x != y    # Not equal to
x > y     # Greater than
x < y     # Less than
x >= y    # Greater than or equal to
x <= y    # Less than or equal to

# BASIC IF
if condition:
    print("The condition is true.")

# IF / ELSE
if condition:
    print("True")
else:
    print("False")

# IF / ELIF / ELSE
if condition_1:
    print("Option 1")
elif condition_2:
    print("Option 2")
else:
    print("Option 3")

# LOGICAL OPERATORS
condition_1 and condition_2    # Both must be True
condition_1 or condition_2     # At least one must be True
not condition                  # Reverses True and False

# COMBINING CONDITIONS
level = 15
gold = 120

if level >= 10 and gold >= 100:
    print("Requirements met.")
else:
    print("Requirements not met.")

# MATCH / CASE
match value:
    case "option_1":
        print("Option 1")
    case "option_2":
        print("Option 2")
    case _:
        print("Unknown option")
```

⬆️ [Back to Contents](#contents)

## 03: Loops

```python
# FOR LOOP
for i in range(5):
    print(i)

# RANGE(STOP)
for i in range(5):
    print(i)
# 0, 1, 2, 3, 4

# RANGE(START, STOP)
for i in range(1, 6):
    print(i)
# 1, 2, 3, 4, 5

# RANGE(START, STOP, STEP)
for i in range(0, 11, 2):
    print(i)
# 0, 2, 4, 6, 8, 10

# COUNTDOWN
for i in range(5, 0, -1):
    print(i)

# WHILE LOOP
health = 100

while health > 0:
    health = health - 20
    print(health)

# BREAK
for i in range(10):
    if i == 5:
        break

    print(i)

# CONTINUE
for i in range(5):
    if i == 2:
        continue

    print(i)

# NESTED LOOPS
for i in range(3):
    for j in range(2):
        print(i, j)

# LOOP + CONDITION
for level in range(1, 6):
    if level == 3:
        print("New ability unlocked!")

    print(level)
```

⬆️ [Back to Contents](#contents)

## 04: Data Structures

```python
# LISTS
players = ["Mage", "Warrior", "Rogue"]

players[0]                 # First element
players[-1]                # Last element
players[1:3]               # Slice

players[0] = "Paladin"     # Modify
players.append("Hunter")   # Add at the end
players.insert(1, "Mage")  # Add at an index
players.remove("Rogue")    # Remove by value
players.pop()              # Remove last element
players.pop(0)             # Remove by index

len(players)

"Mage" in players
"Mage" not in players

for player in players:
    print(player)

# TUPLES
position = (10, 25)

position[0]
position[-1]

for coordinate in position:
    print(coordinate)

# DICTIONARIES
player = {
    "name": "Jaina",
    "level": 30
}

player["name"]             # Access
player.get("level")        # Access with get()
player.get("mana", 0)      # Default value

player["health"] = 100     # Add
player["level"] = 31       # Modify

player.pop("health")       # Remove
del player["level"]        # Remove

player.keys()
player.values()
player.items()

for key, value in player.items():
    print(f"{key}: {value}")

# SETS
classes = {"Mage", "Warrior", "Rogue"}

classes.add("Paladin")
classes.remove("Warrior")
classes.discard("Hunter")

"Mage" in classes

group_a | group_b          # Union
group_a & group_b          # Intersection
group_a - group_b          # Difference

# COMBINING DATA STRUCTURES
players = [
    {"name": "Jaina", "level": 30},
    {"name": "Arthas", "level": 25}
]

for player in players:
    print(f"{player['name']} - Level {player['level']}")
```

⬆️ [Back to Contents](#contents)

## 05: Functions

```python
# BASIC FUNCTION
def show_message():
    print("Hello!")

show_message()

# PARAMETER
def greet_player(name):
    print(f"Welcome, {name}!")

greet_player("Jaina")

# RETURN
def add_gold(gold, reward):
    return gold + reward

final_gold = add_gold(100, 50)

# MULTIPLE PARAMETERS
def show_player(name, player_class, level):
    print(f"{name} - {player_class} - Level {level}")

show_player("Jaina", "Mage", 30)

# KEYWORD ARGUMENTS
show_player(
    name="Jaina",
    player_class="Mage",
    level=30
)

# DEFAULT PARAMETER
def calculate_experience(enemies, experience_per_enemy=40):
    return enemies * experience_per_enemy

experience = calculate_experience(5)

# LOCAL VARIABLE
def calculate_reward(enemies):
    reward = enemies * 25
    return reward

# MULTIPLE RETURN VALUES
def calculate_quest(enemies):
    experience = enemies * 40
    gold = enemies * 10

    return experience, gold

experience, gold = calculate_quest(5)

# *ARGS
def calculate_average(*numbers):
    total = 0

    for number in numbers:
        total = total + number

    return total / len(numbers)

average = calculate_average(10, 20, 30)

# TYPE HINTS
def calculate_damage(health: int, damage: int) -> int:
    return health - damage

# COMBINING FUNCTIONS
def calculate_health(health, damage):
    remaining_health = health - damage

    if remaining_health < 0:
        remaining_health = 0

    return remaining_health

def show_health(name, health):
    print(f"{name}: {health} HP")

final_health = calculate_health(100, 30)
show_health("Jaina", final_health)
```

⬆️ [Back to Contents](#contents)

## 06: Comprehensions

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

⬆️ [Back to Contents](#contents)

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>