# 🔀 Python Conditionals: Exercises

Practice conditionals, comparisons and logical operators with these exercises.

⬅️ [Back to Theory](theory.md)

## 📚 Contents

- [1. Basic Conditions](#1-basic-conditions)
  - [01: Check Health](#exercise-01)
  - [02: Level Requirement](#exercise-02)
  - [03: Enough Gold?](#exercise-03)
- [2. Multiple Conditions](#2-multiple-conditions)
  - [04: Health Status](#exercise-04)
  - [05: Character Level](#exercise-05)
- [3. Logical Operators and Match](#3-logical-operators-and-match)
  - [06: Quest Requirements](#exercise-06)
  - [07: Choose a Difficulty](#exercise-07)
- [4. User Input and Decisions](#4-user-input-and-decisions)
  - [08: Battle Result](#exercise-08)
  - [09: Item Requirement](#exercise-09)
- [5. Mixed Practice](#5-mixed-practice)
  - [10: Adventure Decision](#exercise-10)

**Difficulty:** ⚔️ Easy · ⚔️⚔️ Medium · ⚔️⚔️⚔️ Hard

## 1. Basic Conditions

<a id="exercise-01"></a>

### [01] Exercise: Check Health · ⚔️ Easy

```text
Create a variable called health with a value of 80.

If health is greater than 0, print:

The character is alive.
```

<details>
<summary>💡 Show solution</summary>

```python
health = 80

if health > 0:
    print("The character is alive.")
```

</details>

<a id="exercise-02"></a>

### [02] Exercise: Level Requirement · ⚔️ Easy

```text
Create a variable called level.

If the level is 10 or higher, print:

Level requirement met.
```

<details>
<summary>💡 Show solution</summary>

```python
level = 15

if level >= 10:
    print("Level requirement met.")
```

</details>

<a id="exercise-03"></a>

### [03] Exercise: Enough Gold? · ⚔️ Easy

```text
Create a variable called gold with a value of 75.

An item costs 100 gold.

Print whether the character can buy the item or does not have enough gold.
```

<details>
<summary>💡 Show solution</summary>

```python
gold = 75
item_price = 100

if gold >= item_price:
    print("You can buy the item.")
else:
    print("You don't have enough gold.")
```

</details>

## 2. Multiple Conditions

<a id="exercise-04"></a>

### [04] Exercise: Health Status · ⚔️⚔️ Medium

```text
Create a variable called health.

Display:

"Health is high." if health is greater than 75.
"Health is medium." if health is greater than 25.
"Health is low." otherwise.
```

<details>
<summary>💡 Show solution</summary>

```python
health = 60

if health > 75:
    print("Health is high.")
elif health > 25:
    print("Health is medium.")
else:
    print("Health is low.")
```

</details>

<a id="exercise-05"></a>

### [05] Exercise: Character Level · ⚔️⚔️ Medium

```text
Create a variable called level.

Display:

"High level." if level is 30 or higher.
"Medium level." if level is 20 or higher.
"Low level." if level is 10 or higher.
"Beginner level." otherwise.
```

<details>
<summary>💡 Show solution</summary>

```python
level = 24

if level >= 30:
    print("High level.")
elif level >= 20:
    print("Medium level.")
elif level >= 10:
    print("Low level.")
else:
    print("Beginner level.")
```

</details>

## 3. Logical Operators and Match

<a id="exercise-06"></a>

### [06] Exercise: Quest Requirements · ⚔️⚔️ Medium

```text
A quest requires:

Level 10 or higher
At least 50 gold

Create variables for level and gold.

The character can start the quest only if both requirements are met.
```

<details>
<summary>💡 Show solution</summary>

```python
level = 15
gold = 80

if level >= 10 and gold >= 50:
    print("You can start the quest.")
else:
    print("Quest requirements not met.")
```

</details>

<a id="exercise-07"></a>

### [07] Exercise: Choose a Difficulty · ⚔️⚔️ Medium

```text
Ask the user to choose a difficulty:

easy
normal
hard

Use match / case to display:

"Easy mode selected."
"Normal mode selected."
"Hard mode selected."

If the user enters another value, display:

"Invalid difficulty."
```

<details>
<summary>💡 Show solution</summary>

```python
difficulty = input("Choose difficulty: ")

match difficulty:
    case "easy":
        print("Easy mode selected.")
    case "normal":
        print("Normal mode selected.")
    case "hard":
        print("Hard mode selected.")
    case _:
        print("Invalid difficulty.")
```

</details>

## 4. User Input and Decisions

<a id="exercise-08"></a>

### [08] Exercise: Battle Result · ⚔️⚔️ Medium

```text
Ask the user for:

Starting health
Damage received

Calculate the remaining health.

Display:

"Defeated!" if the remaining health is 0 or less.
"Critical health!" if the remaining health is 25 or less.
"Ready to continue!" otherwise.
```

<details>
<summary>💡 Show solution</summary>

```python
health = int(input("Starting health: "))
damage = int(input("Damage received: "))

remaining_health = health - damage

if remaining_health <= 0:
    print("Defeated!")
elif remaining_health <= 25:
    print("Critical health!")
else:
    print("Ready to continue!")
```

</details>

<a id="exercise-09"></a>

### [09] Exercise: Item Requirement · ⚔️⚔️ Medium

```text
Ask the user for:

Character level
Current gold

An item requires level 15 and costs 100 gold.

Display whether the character can buy and use the item.
```

<details>
<summary>💡 Show solution</summary>

```python
level = int(input("Character level: "))
gold = float(input("Current gold: "))

required_level = 15
item_price = 100

if level >= required_level and gold >= item_price:
    print("You can buy and use the item.")
else:
    print("Requirements not met.")
```

</details>

## 5. Mixed Practice

<a id="exercise-10"></a>

### [10] Exercise: Adventure Decision · ⚔️⚔️⚔️ Hard

```text
Ask the user for:

Character name
Starting health
Damage received
Current gold

Calculate the remaining health.

The adventure can continue only if:

The character has more than 0 health
AND
The character has at least 50 gold

If both requirements are met, display:

"[name] is ready to continue the adventure."

Otherwise, display:

"[name] should return to town."
```

<details>
<summary>💡 Show solution</summary>

```python
player_name = input("Character name: ")
health = int(input("Starting health: "))
damage = int(input("Damage received: "))
gold = float(input("Current gold: "))

remaining_health = health - damage

if remaining_health > 0 and gold >= 50:
    print(f"{player_name} is ready to continue the adventure.")
else:
    print(f"{player_name} should return to town.")
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