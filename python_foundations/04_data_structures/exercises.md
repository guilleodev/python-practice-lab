# 🗂️ Python Data Structures - Exercises

Practice lists, tuples, dictionaries and sets with these exercises.

⬅️ [Back to Theory](theory.md)

## 📚 Contents

- [1. Lists](#1-lists)
  - [01: Party Members](#exercise-01)
  - [02: Inventory Update](#exercise-02)
  - [03: Player Selection](#exercise-03)
- [2. Tuples](#2-tuples)
  - [04: Spawn Position](#exercise-04)
- [3. Dictionaries](#3-dictionaries)
  - [05: Character Profile](#exercise-05)
  - [06: Character Update](#exercise-06)
  - [07: Character Information](#exercise-07)
- [4. Sets](#4-sets)
  - [08: Unique Classes](#exercise-08)
  - [09: Shared Abilities](#exercise-09)
- [5. Mixed Practice](#5-mixed-practice)
  - [10: Party Manager](#exercise-10)

**Difficulty:** ⚔️ Easy · ⚔️⚔️ Medium · ⚔️⚔️⚔️ Hard

## 1. Lists

<a id="exercise-01"></a>

### [01] Exercise: Party Members · ⚔️ Easy

```text
Create a list with these character classes:

Mage
Warrior
Rogue

Print the first character class.
Print the last character class.
Print the number of classes in the list.
```

<details>
<summary>💡 Show solution</summary>

```python
classes = ["Mage", "Warrior", "Rogue"]

print(classes[0])
print(classes[-1])
print(len(classes))
```

</details>

<a id="exercise-02"></a>

### [02] Exercise: Inventory Update · ⚔️ Easy

```text
Create an inventory with:

Potion
Sword
Shield

Add "Scroll" to the inventory.

Remove "Sword".

Then print the final inventory.
```

<details>
<summary>💡 Show solution</summary>

```python
inventory = ["Potion", "Sword", "Shield"]

inventory.append("Scroll")
inventory.remove("Sword")

print(inventory)
```

</details>

<a id="exercise-03"></a>

### [03] Exercise: Player Selection · ⚔️⚔️ Medium

```text
Create a list with:

Mage
Warrior
Rogue
Paladin
Hunter

Print the first three classes using slicing.

Then use a loop to display every class in the list.
```

<details>
<summary>💡 Show solution</summary>

```python
classes = ["Mage", "Warrior", "Rogue", "Paladin", "Hunter"]

print(classes[:3])

for player_class in classes:
    print(player_class)
```

</details>

## 2. Tuples

<a id="exercise-04"></a>

### [04] Exercise: Spawn Position · ⚔️ Easy

```text
Create a tuple representing a position:

120
250

Print the X coordinate.
Print the Y coordinate.

Then use a loop to display both coordinates.
```

<details>
<summary>💡 Show solution</summary>

```python
spawn_position = (120, 250)

print(spawn_position[0])
print(spawn_position[1])

for coordinate in spawn_position:
    print(coordinate)
```

</details>

## 3. Dictionaries

<a id="exercise-05"></a>

### [05] Exercise: Character Profile · ⚔️ Easy

```text
Create a dictionary containing:

name: Jaina
class: Mage
level: 30

Print the character's name and level.
```

<details>
<summary>💡 Show solution</summary>

```python
player = {
    "name": "Jaina",
    "class": "Mage",
    "level": 30
}

print(player["name"])
print(player["level"])
```

</details>

<a id="exercise-06"></a>

### [06] Exercise: Character Update · ⚔️⚔️ Medium

```text
Create a dictionary containing:

name: Jaina
level: 30
health: 100

Increase the level to 31.

Add:

gold: 150

Remove the health value.

Print the final dictionary.
```

<details>
<summary>💡 Show solution</summary>

```python
player = {
    "name": "Jaina",
    "level": 30,
    "health": 100
}

player["level"] = 31
player["gold"] = 150
player.pop("health")

print(player)
```

</details>

<a id="exercise-07"></a>

### [07] Exercise: Character Information · ⚔️⚔️ Medium

```text
Create a dictionary with information about a character.

Include:

name
class
level
health

Use a loop to display every key and value.

Example:

name: Jaina
class: Mage
level: 30
health: 100
```

<details>
<summary>💡 Show solution</summary>

```python
player = {
    "name": "Jaina",
    "class": "Mage",
    "level": 30,
    "health": 100
}

for key, value in player.items():
    print(f"{key}: {value}")
```

</details>

## 4. Sets

<a id="exercise-08"></a>

### [08] Exercise: Unique Classes · ⚔️ Easy

```text
Create a set using these values:

Mage
Warrior
Mage
Rogue
Warrior

Print the set.

Then add "Paladin".
```

<details>
<summary>💡 Show solution</summary>

```python
classes = {"Mage", "Warrior", "Mage", "Rogue", "Warrior"}

print(classes)

classes.add("Paladin")

print(classes)
```

</details>

<a id="exercise-09"></a>

### [09] Exercise: Shared Abilities · ⚔️⚔️ Medium

```text
Two characters have these abilities:

Character A:
Attack
Heal
Dodge

Character B:
Attack
Block
Dodge

Create two sets.

Display:

All unique abilities from both characters.
Abilities shared by both characters.
Abilities that only Character A has.
```

<details>
<summary>💡 Show solution</summary>

```python
character_a = {"Attack", "Heal", "Dodge"}
character_b = {"Attack", "Block", "Dodge"}

print(character_a | character_b)
print(character_a & character_b)
print(character_a - character_b)
```

</details>

## 5. Mixed Practice

<a id="exercise-10"></a>

### [10] Exercise: Party Manager · ⚔️⚔️⚔️ Hard

```text
Create a list containing three characters.

Each character should be a dictionary containing:

name
class
level

Use a loop to display every character.

Example output:

Jaina - Mage - Level 30
Arthas - Paladin - Level 25
Valeera - Rogue - Level 20

Then display the total number of characters in the party.
```

<details>
<summary>💡 Show solution</summary>

```python
players = [
    {
        "name": "Jaina",
        "class": "Mage",
        "level": 30
    },
    {
        "name": "Arthas",
        "class": "Paladin",
        "level": 25
    },
    {
        "name": "Valeera",
        "class": "Rogue",
        "level": 20
    }
]

for player in players:
    print(f"{player['name']} - {player['class']} - Level {player['level']}")

print(f"Party members: {len(players)}")
```

</details>

## 🚀 Next Step

Completed all the exercises?

➡️ [Continue to the Module Project](project.md)

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>