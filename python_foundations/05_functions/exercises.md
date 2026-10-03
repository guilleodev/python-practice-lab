# 🧩 Python Functions: Exercises

Practice creating functions, using parameters and returning values with these exercises.

⬅️ [Back to Theory](theory.md)

## 📚 Contents

- [1. Basic Functions](#1-basic-functions)
  - [01: Welcome Message](#exercise-01)
  - [02: Greet Player](#exercise-02)
- [2. Parameters and Return](#2-parameters-and-return)
  - [03: Damage Calculator](#exercise-03)
  - [04: Quest Reward](#exercise-04)
  - [05: Character Status](#exercise-05)
- [3. Function Options](#3-function-options)
  - [06: Experience Calculator](#exercise-06)
  - [07: Battle Result](#exercise-07)
- [4. Flexible Functions](#4-flexible-functions)
  - [08: Average Damage](#exercise-08)
  - [09: Inventory Display](#exercise-09)
- [5. Mixed Practice](#5-mixed-practice)
  - [10: Character Report](#exercise-10)

**Difficulty:** ⚔️ Easy · ⚔️⚔️ Medium · ⚔️⚔️⚔️ Hard

## 1. Basic Functions

<a id="exercise-01"></a>

### [01] Exercise: Welcome Message · ⚔️ Easy

```text
Create a function called welcome().

The function should display:

Welcome to the adventure!

Call the function two times.
```

<details>
<summary>💡 Show solution</summary>

```python
def welcome():
    print("Welcome to the adventure!")


welcome()
welcome()
```

</details>

<a id="exercise-02"></a>

### [02] Exercise: Greet Player · ⚔️ Easy

```text
Create a function called greet_player().

The function should receive a player name as a parameter.

Display:

Welcome, NAME!

Call the function with two different names.
```

<details>
<summary>💡 Show solution</summary>

```python
def greet_player(name):
    print(f"Welcome, {name}!")


greet_player("Jaina")
greet_player("Valeera")
```

</details>

## 2. Parameters and Return

<a id="exercise-03"></a>

### [03] Exercise: Damage Calculator · ⚔️ Easy

```text
Create a function called calculate_health().

The function should receive:

health
damage

Return the remaining health.

Example:

Health: 100
Damage: 30

Result: 70
```

<details>
<summary>💡 Show solution</summary>

```python
def calculate_health(health, damage):
    return health - damage


remaining_health = calculate_health(100, 30)

print(remaining_health)
```

</details>

<a id="exercise-04"></a>

### [04] Exercise: Quest Reward · ⚔️ Easy

```text
Create a function called calculate_reward().

The function should receive:

enemies defeated
gold per enemy

Calculate and return the total gold earned.

Example:

Enemies: 5
Gold per enemy: 10

Result: 50
```

<details>
<summary>💡 Show solution</summary>

```python
def calculate_reward(enemies, gold_per_enemy):
    return enemies * gold_per_enemy


reward = calculate_reward(5, 10)

print(reward)
```

</details>

<a id="exercise-05"></a>

### [05] Exercise: Character Status · ⚔️⚔️ Medium

```text
Create a function called get_status().

The function should receive the character's health.

Return:

"Healthy" if health is greater than 50
"Injured" if health is greater than 0
"Defeated" if health is 0 or less

Test the function with different health values.
```

<details>
<summary>💡 Show solution</summary>

```python
def get_status(health):
    if health > 50:
        return "Healthy"
    elif health > 0:
        return "Injured"
    else:
        return "Defeated"


print(get_status(100))
print(get_status(30))
print(get_status(0))
```

</details>

## 3. Function Options

<a id="exercise-06"></a>

### [06] Exercise: Experience Calculator · ⚔️⚔️ Medium

```text
Create a function called calculate_experience().

The function should receive:

enemies defeated
experience per enemy

The experience per enemy should have a default value of 40.

Return the total experience.

Test the function:

Once using the default value.
Once using a different experience value.
```

<details>
<summary>💡 Show solution</summary>

```python
def calculate_experience(enemies, experience_per_enemy=40):
    return enemies * experience_per_enemy


print(calculate_experience(5))
print(calculate_experience(5, 100))
```

</details>

<a id="exercise-07"></a>

### [07] Exercise: Battle Result · ⚔️⚔️ Medium

```text
Create a function called battle_result().

The function should receive:

health
damage

Calculate the remaining health.

Return two values:

remaining health
whether the character was defeated

The defeated value should be True or False.

Make sure remaining health never goes below 0.
```

<details>
<summary>💡 Show solution</summary>

```python
def battle_result(health, damage):
    remaining_health = health - damage

    if remaining_health < 0:
        remaining_health = 0

    defeated = remaining_health == 0

    return remaining_health, defeated


health, defeated = battle_result(100, 120)

print(health)
print(defeated)
```

</details>

## 4. Flexible Functions

<a id="exercise-08"></a>

### [08] Exercise: Average Damage · ⚔️⚔️ Medium

```text
Create a function called calculate_average_damage().

Use *args so the function can receive any number of damage values.

Calculate and return the average damage.

Example:

10, 20, 30, 40

Average damage: 25
```

<details>
<summary>💡 Show solution</summary>

```python
def calculate_average_damage(*damage_values):
    total = 0

    for damage in damage_values:
        total = total + damage

    return total / len(damage_values)


average_damage = calculate_average_damage(10, 20, 30, 40)

print(average_damage)
```

</details>

<a id="exercise-09"></a>

### [09] Exercise: Inventory Display · ⚔️⚔️ Medium

```text
Create a function called show_inventory().

Use *args so the function can receive any number of items.

Display each item using a loop.

Example:

Potion
Sword
Shield
```

<details>
<summary>💡 Show solution</summary>

```python
def show_inventory(*items):
    for item in items:
        print(item)


show_inventory("Potion", "Sword", "Shield")
```

</details>

## 5. Mixed Practice

<a id="exercise-10"></a>

### [10] Exercise: Character Report · ⚔️⚔️⚔️ Hard

```text
Create three functions:

calculate_health()
calculate_experience()
show_character()

calculate_health() should receive:

health
damage

Return the remaining health.
Health should never go below 0.

calculate_experience() should receive:

enemies defeated

Each enemy gives 40 experience points.

Return the total experience.

show_character() should receive:

name
health
experience

Display the character information.

Ask the user for:

Character name
Starting health
Damage received
Enemies defeated

Use your functions to calculate and display the final character report.
```

### Example

```text
Character name: Jaina
Starting health: 100
Damage received: 30
Enemies defeated: 5

==========================
     CHARACTER REPORT
==========================

Character: Jaina
Health: 70
Experience: 200

==========================
```

<details>
<summary>💡 Show solution</summary>

```python
def calculate_health(health, damage):
    remaining_health = health - damage

    if remaining_health < 0:
        remaining_health = 0

    return remaining_health


def calculate_experience(enemies):
    return enemies * 40


def show_character(name, health, experience):
    print()
    print("==========================")
    print("     CHARACTER REPORT")
    print("==========================")
    print()
    print(f"Character: {name}")
    print(f"Health: {health}")
    print(f"Experience: {experience}")
    print()
    print("==========================")


player_name = input("Character name: ")
starting_health = int(input("Starting health: "))
damage_received = int(input("Damage received: "))
enemies_defeated = int(input("Enemies defeated: "))

final_health = calculate_health(starting_health, damage_received)
experience = calculate_experience(enemies_defeated)

show_character(player_name, final_health, experience)
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