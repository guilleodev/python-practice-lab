# ⚡ Python Comprehensions: Exercises

Practice transforming, filtering and generating data using comprehensions.

⬅️ [Back to Theory](theory.md)

## 📚 Contents

- [1. List Comprehensions](#1-list-comprehensions)
  - [01: Double Damage](#exercise-01)
  - [02: Experience Levels](#exercise-02)
  - [03: High Damage](#exercise-03)
- [2. Conditions](#2-conditions)
  - [04: Even Numbers](#exercise-04)
  - [05: Replace Odd Numbers](#exercise-05)
- [3. Combining Data](#3-combining-data)
  - [06: Character Combinations](#exercise-06)
- [4. Dictionary and Set Comprehensions](#4-dictionary-and-set-comprehensions)
  - [07: Player Health](#exercise-07)
  - [08: Active Players](#exercise-08)
  - [09: Unique Levels](#exercise-09)
- [5. Generator Expressions](#5-generator-expressions)
  - [10: Experience Generator](#exercise-10)

**Difficulty:** ⚔️ Easy · ⚔️⚔️ Medium · ⚔️⚔️⚔️ Hard

## 1. List Comprehensions

<a id="exercise-01"></a>

### [01] Exercise: Double Damage · ⚔️ Easy

```text
Create this list:

damage = [10, 20, 30, 40]

Use a list comprehension to create a new list
where every damage value is multiplied by 2.

Expected result:

[20, 40, 60, 80]
```

<details>
<summary>💡 Show solution</summary>

```python
damage = [10, 20, 30, 40]

double_damage = [
    value * 2
    for value in damage
]

print(double_damage)
```

</details>

<a id="exercise-02"></a>

### [02] Exercise: Experience Levels · ⚔️ Easy

```text
Use range() and a list comprehension to generate:

1
2
3
4
5

Each level should give 100 experience points.

Create a list containing the experience for every level.

Expected result:

[100, 200, 300, 400, 500]
```

<details>
<summary>💡 Show solution</summary>

```python
experience = [
    level * 100
    for level in range(1, 6)
]

print(experience)
```

</details>

<a id="exercise-03"></a>

### [03] Exercise: High Damage · ⚔️ Easy

```text
Create this list:

damage = [10, 45, 20, 70, 30, 90]

Use a list comprehension to create a new list
containing only values greater than 40.

Expected result:

[45, 70, 90]
```

<details>
<summary>💡 Show solution</summary>

```python
damage = [10, 45, 20, 70, 30, 90]

high_damage = [
    value
    for value in damage
    if value > 40
]

print(high_damage)
```

</details>

## 2. Conditions

<a id="exercise-04"></a>

### [04] Exercise: Even Numbers · ⚔️ Easy

```text
Create a list containing the numbers from 1 to 20.

Use a list comprehension to create another list
containing only the even numbers.

Expected result:

[2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```

<details>
<summary>💡 Show solution</summary>

```python
numbers = [
    number
    for number in range(1, 21)
]

even_numbers = [
    number
    for number in numbers
    if number % 2 == 0
]

print(even_numbers)
```

</details>

<a id="exercise-05"></a>

### [05] Exercise: Replace Odd Numbers · ⚔️⚔️ Medium

```text
Create this list:

numbers = [1, 2, 3, 4, 5, 6]

Create a new list using a comprehension.

Keep the even numbers unchanged.

Replace every odd number with 0.

Expected result:

[0, 2, 0, 4, 0, 6]
```

<details>
<summary>💡 Show solution</summary>

```python
numbers = [1, 2, 3, 4, 5, 6]

result = [
    number if number % 2 == 0 else 0
    for number in numbers
]

print(result)
```

</details>

## 3. Combining Data

<a id="exercise-06"></a>

### [06] Exercise: Character Combinations · ⚔️⚔️ Medium

```text
Create these two lists:

classes = ["Mage", "Warrior"]
roles = ["DPS", "Support", "Tank"]

Use a list comprehension with two loops
to generate every possible combination.

Expected result:

[
    "Mage - DPS",
    "Mage - Support",
    "Mage - Tank",
    "Warrior - DPS",
    "Warrior - Support",
    "Warrior - Tank"
]
```

<details>
<summary>💡 Show solution</summary>

```python
classes = ["Mage", "Warrior"]
roles = ["DPS", "Support", "Tank"]

combinations = [
    f"{player_class} - {role}"
    for player_class in classes
    for role in roles
]

print(combinations)
```

</details>

## 4. Dictionary and Set Comprehensions

<a id="exercise-07"></a>

### [07] Exercise: Player Health · ⚔️⚔️ Medium

```text
Create this list:

players = ["Jaina", "Valeera", "Arthas"]

Use a dictionary comprehension to create
a dictionary where every player starts with 100 health.

Expected result:

{
    "Jaina": 100,
    "Valeera": 100,
    "Arthas": 100
}
```

<details>
<summary>💡 Show solution</summary>

```python
players = ["Jaina", "Valeera", "Arthas"]

player_health = {
    player: 100
    for player in players
}

print(player_health)
```

</details>

<a id="exercise-08"></a>

### [08] Exercise: Active Players · ⚔️⚔️ Medium

```text
Create this dictionary:

players = {
    "Jaina": 100,
    "Valeera": 70,
    "Arthas": 0,
    "Thrall": 0
}

Use a dictionary comprehension to create
a new dictionary containing only players
with health greater than 0.

Expected result:

{
    "Jaina": 100,
    "Valeera": 70
}
```

<details>
<summary>💡 Show solution</summary>

```python
players = {
    "Jaina": 100,
    "Valeera": 70,
    "Arthas": 0,
    "Thrall": 0
}

active_players = {
    name: health
    for name, health in players.items()
    if health > 0
}

print(active_players)
```

</details>

<a id="exercise-09"></a>

### [09] Exercise: Unique Levels · ⚔️⚔️ Medium

```text
Create this list:

levels = [10, 20, 10, 30, 20, 40, 30]

Use a set comprehension to create a collection
containing each level multiplied by 2.

Duplicate results should disappear automatically.
```

<details>
<summary>💡 Show solution</summary>

```python
levels = [10, 20, 10, 30, 20, 40, 30]

unique_levels = {
    level * 2
    for level in levels
}

print(unique_levels)
```

</details>

## 5. Generator Expressions

<a id="exercise-10"></a>

### [10] Exercise: Experience Generator · ⚔️⚔️⚔️ Hard

```text
Create a generator expression for the numbers
from 1 to 1,000,000.

Each number represents a level.

Each level requires:

level * 100 experience points

Do not create a list with all the values.

Use a loop to display only the first 5
experience values.

Expected output:

100
200
300
400
500
```

> [!NOTE]
> The goal is to generate the values when they are needed instead of storing all 1,000,000 results in a list.

<details>
<summary>💡 Show solution</summary>

```python
experience_generator = (
    level * 100
    for level in range(1, 1_000_001)
)

count = 0

for experience in experience_generator:
    print(experience)

    count = count + 1

    if count == 5:
        break
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