# 🗂️ Python Data Structures - Theory

Data structures allow us to store and organize multiple values in different ways.

Python provides several built-in data structures. The most common are **lists, tuples, dictionaries and sets**.

## 📚 Contents

- [1. Lists](#1-lists)
- [2. Tuples](#2-tuples)
- [3. Dictionaries](#3-dictionaries)
- [4. Sets](#4-sets)
- [5. Choosing a Data Structure](#5-choosing-a-data-structure)
- [6. Combining Data Structures](#6-combining-data-structures)
- [📌 Cheat Sheet: 04 Data Structures](#-cheat-sheet-04-data-structures)

## 1. Lists

A **list** stores multiple values in a specific order.

Lists are created using square brackets `[]`.

```python
players = ["Mage", "Warrior", "Rogue"]
```

A list can contain different data types:

```python
character = ["Mage", 20, 100, True]
```

However, lists usually contain values that are related to each other.

### 1.1 Accessing Elements

Each element in a list has an **index**.

Python starts counting from `0`.

```python
players = ["Mage", "Warrior", "Rogue"]

print(players[0])
print(players[1])
print(players[2])
```

Output:

```text
Mage
Warrior
Rogue
```

You can also use negative indexes.

```python
print(players[-1])
```

Output:

```text
Rogue
```

`-1` represents the last element.

### 1.2 Slicing

Slicing allows you to obtain part of a list.

```python
players = ["Mage", "Warrior", "Rogue", "Hunter"]

print(players[1:3])
```

Output:

```text
['Warrior', 'Rogue']
```

The first index is included and the last one is not.

```python
players[start:stop]
```

You can also omit one of the values:

```python
print(players[:2])
print(players[2:])
```

Output:

```text
['Mage', 'Warrior']
['Rogue', 'Hunter']
```

A third value can be used as a step:

```python
numbers = [1, 2, 3, 4, 5, 6]

print(numbers[::2])
```

Output:

```text
[1, 3, 5]
```

### 1.3 Modifying Lists

Lists are **mutable**, which means their elements can be changed.

```python
players = ["Mage", "Warrior", "Rogue"]

players[1] = "Paladin"

print(players)
```

Output:

```text
['Mage', 'Paladin', 'Rogue']
```

### 1.4 Adding Elements

`append()` adds an element to the end of the list.

```python
players = ["Mage", "Warrior"]

players.append("Rogue")

print(players)
```

Output:

```text
['Mage', 'Warrior', 'Rogue']
```

`insert()` adds an element at a specific position.

```python
players.insert(1, "Paladin")
```

Now the list becomes:

```text
['Mage', 'Paladin', 'Warrior', 'Rogue']
```

### 1.5 Removing Elements

`remove()` removes an element by its value.

```python
players.remove("Warrior")
```

`pop()` removes an element by its index and returns it.

```python
removed_player = players.pop(0)

print(removed_player)
```

If no index is provided, `pop()` removes the last element.

```python
players.pop()
```

### 1.6 List Length

`len()` returns the number of elements.

```python
players = ["Mage", "Warrior", "Rogue"]

print(len(players))
```

Output:

```text
3
```

### 1.7 Checking if an Element Exists

Use `in` to check whether a value exists in a list.

```python
players = ["Mage", "Warrior", "Rogue"]

if "Mage" in players:
    print("Mage found.")
```

You can use `not in` for the opposite:

```python
if "Paladin" not in players:
    print("Paladin not found.")
```

### 1.8 Looping Through Lists

A `for` loop can go through every element in a list.

```python
players = ["Mage", "Warrior", "Rogue"]

for player in players:
    print(player)
```

Output:

```text
Mage
Warrior
Rogue
```

This is one of the most common ways to work with lists.

## 2. Tuples

A **tuple** is similar to a list, but it cannot be modified after it is created.

Tuples are usually created using parentheses `()`.

```python
position = (10, 25)
```

### 2.1 Accessing Elements

Tuple elements also use indexes.

```python
position = (10, 25)

print(position[0])
print(position[1])
```

Output:

```text
10
25
```

Negative indexes also work:

```python
print(position[-1])
```

### 2.2 Tuples Are Immutable

Tuples are **immutable**.

This means you cannot change their elements after creating them.

This would produce an error:

```python
position = (10, 25)

position[0] = 50
```

Lists can change.

Tuples cannot.

### 2.3 When to Use a Tuple

Tuples are useful when the values should stay together and should not change.

For example:

```python
spawn_position = (100, 250)
screen_resolution = (1920, 1080)
```

You can also loop through a tuple:

```python
coordinates = (10, 20, 30)

for coordinate in coordinates:
    print(coordinate)
```

## 3. Dictionaries

A **dictionary** stores information using **key-value pairs**.

Dictionaries are created using curly braces `{}`.

```python
player = {
    "name": "Jaina",
    "class": "Mage",
    "level": 30
}
```

Instead of accessing information using a numeric index, dictionaries use keys.

### 3.1 Accessing Values

```python
print(player["name"])
print(player["level"])
```

Output:

```text
Jaina
30
```

### 3.2 Adding and Modifying Values

You can add a new key-value pair:

```python
player["health"] = 100
```

You can also modify an existing value:

```python
player["level"] = 31
```

The dictionary now contains:

```python
{
    "name": "Jaina",
    "class": "Mage",
    "level": 31,
    "health": 100
}
```

### 3.3 Using `get()`

`get()` is another way to access a value.

```python
print(player.get("name"))
```

One advantage is that it does not produce an error if the key does not exist.

```python
print(player.get("mana"))
```

Output:

```text
None
```

You can also provide a default value:

```python
print(player.get("mana", 0))
```

Output:

```text
0
```

### 3.4 Removing Values

`pop()` removes a key and returns its value.

```python
health = player.pop("health")

print(health)
```

You can also use `del`:

```python
del player["level"]
```

### 3.5 Keys, Values and Items

`keys()` returns the dictionary keys.

```python
print(player.keys())
```

`values()` returns the values.

```python
print(player.values())
```

`items()` returns both keys and values.

```python
print(player.items())
```

### 3.6 Looping Through Dictionaries

You can loop through the keys:

```python
for key in player:
    print(key)
```

You can loop through the values:

```python
for value in player.values():
    print(value)
```

Or both at the same time:

```python
for key, value in player.items():
    print(f"{key}: {value}")
```

This is a very common way to work with dictionaries.

## 4. Sets

A **set** stores unique values.

Sets are created using curly braces `{}`.

```python
classes = {"Mage", "Warrior", "Rogue"}
```

### 4.1 Unique Values

A set automatically removes duplicates.

```python
classes = {"Mage", "Warrior", "Mage", "Rogue"}

print(classes)
```

The set contains only one `"Mage"`.

```text
{'Mage', 'Warrior', 'Rogue'}
```

> [!NOTE]
> Sets are unordered, so the elements may appear in a different order.

### 4.2 Adding Elements

Use `add()`:

```python
classes.add("Paladin")
```

### 4.3 Removing Elements

Use `remove()`:

```python
classes.remove("Warrior")
```

You can also use `discard()`:

```python
classes.discard("Hunter")
```

The difference is that `discard()` does not produce an error if the element does not exist.

### 4.4 Checking Values

You can use `in` and `not in`:

```python
if "Mage" in classes:
    print("Mage found.")
```

### 4.5 Set Operations

Sets are useful for comparing groups of unique values.

```python
group_a = {"Mage", "Warrior", "Rogue"}
group_b = {"Mage", "Paladin", "Rogue"}
```

**Union** combines all unique values:

```python
print(group_a | group_b)
```

**Intersection** finds values present in both sets:

```python
print(group_a & group_b)
```

**Difference** finds values present in one set but not the other:

```python
print(group_a - group_b)
```

These operations can also be written as:

```python
group_a.union(group_b)
group_a.intersection(group_b)
group_a.difference(group_b)
```

## 5. Choosing a Data Structure

Each data structure is useful for a different situation.

| Structure | Ordered | Mutable | Duplicates | Main Use |
|---|---|---|---|---|
| List | Yes | Yes | Yes | Collection of values |
| Tuple | Yes | No | Yes | Values that should not change |
| Dictionary | Yes | Yes | Keys must be unique | Key-value information |
| Set | No | Yes | No | Unique values |

For example:

```python
players = ["Jaina", "Arthas", "Valeera"]

position = (100, 250)

player = {
    "name": "Jaina",
    "level": 30
}

classes = {"Mage", "Warrior", "Rogue"}
```

A simple way to think about them:

```text
List        -> ordered collection
Tuple       -> fixed collection
Dictionary  -> information with labels
Set         -> unique values
```

## 6. Combining Data Structures

Data structures can also contain other data structures.

For example, a list can contain dictionaries:

```python
players = [
    {"name": "Jaina", "level": 30},
    {"name": "Arthas", "level": 25},
    {"name": "Valeera", "level": 20}
]
```

Now we can combine data structures with loops:

```python
for player in players:
    print(f"{player['name']} - Level {player['level']}")
```

Output:

```text
Jaina - Level 30
Arthas - Level 25
Valeera - Level 20
```

A dictionary can also contain lists:

```python
player = {
    "name": "Jaina",
    "inventory": ["Potion", "Staff", "Scroll"]
}
```

We can access the list using its key:

```python
print(player["inventory"])
```

Or loop through it:

```python
for item in player["inventory"]:
    print(item)
```

Combining data structures allows us to represent more complex information while still using the same concepts we already know.

## 📌 Cheat Sheet: 04 Data Structures

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

## 🧩 Next Step

➡️ [Continue with the exercises](exercises.md)

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>