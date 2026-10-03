# 🧩 Python Basics: Exercises

Practice the concepts from **01: Python Basics**.

> Try to solve each exercise by yourself before checking the solution.

⬅️ [Back to Theory](theory.md)

## 📚 Contents

- [1. Variables and Data Types](#1-variables-and-data-types)
  - [01: Character Stats](#exercise-01)
  - [02: Taking Damage](#exercise-02)
  - [03: Quest Reward](#exercise-03)
- [2. Working with Numbers](#2-working-with-numbers)
  - [04: Sharing Gold](#exercise-04)
  - [05: Experience Calculator](#exercise-05)
- [3. Working with Text](#3-working-with-text)
  - [06: Character Card](#exercise-06)
- [4. User Input and Type Conversion](#4-user-input-and-type-conversion)
  - [07: Create Your Character](#exercise-07)
  - [08: Damage Calculator](#exercise-08)
  - [09: Quest Calculator](#exercise-09)
- [5. Mixed Practice](#5-mixed-practice)
  - [10: Adventure Summary](#exercise-10)

**Difficulty:** ⚔️ Easy · ⚔️⚔️ Medium · ⚔️⚔️⚔️ Hard

## 1. Variables and Data Types

<a id="exercise-01"></a>

### [01] Exercise: Character Stats · ⚔️ Easy

```text id="2m6wwx"
Create variables to store:

- Character name
- Character class
- Level
- Health
- Whether a quest has been completed

Use appropriate data types for each value.

Print all the variables.
```

<details>
<summary>💡 Show solution</summary>

```python id="jn3zoa"
player_name = "Jaina"
player_class = "Mage"
level = 20
health = 100
quest_completed = False

print(player_name)
print(player_class)
print(level)
print(health)
print(quest_completed)
```

</details>

<a id="exercise-02"></a>

### [02] Exercise: Taking Damage · ⚔️ Easy

```text id="fd7f2k"
A player starts with 100 health and receives 27 damage.

Calculate the remaining health and print the result.
```

**Expected output:**

```text id="xezqme"
Remaining health: 73
```

<details>
<summary>💡 Show solution</summary>

```python id="wqjnhz"
health = 100
damage = 27

remaining_health = health - damage

print(f"Remaining health: {remaining_health}")
```

</details>

<a id="exercise-03"></a>

### [03] Exercise: Quest Reward · ⚔️ Easy

```text id="e8f84h"
A player has 75 gold and completes a quest that rewards 30 gold.

Update the gold variable with the new amount and print it.
```

**Expected output:**

```text id="trhglb"
Gold: 105
```

<details>
<summary>💡 Show solution</summary>

```python id="5l1pcy"
gold = 75
quest_reward = 30

gold = gold + quest_reward

print(f"Gold: {gold}")
```

</details>

## 2. Working with Numbers

<a id="exercise-04"></a>

### [04] Exercise: Sharing Gold · ⚔️⚔️ Medium

```text id="g2asuy"
A group of 4 players finds 103 gold.

Divide the gold equally between the players and calculate how much gold remains.
```

**Expected output:**

```text id="54mjdp"
Gold per player: 25
Gold remaining: 3
```

<details>
<summary>💡 Show solution</summary>

```python id="44qzqe"
gold = 103
players = 4

gold_per_player = gold // players
gold_remaining = gold % players

print(f"Gold per player: {gold_per_player}")
print(f"Gold remaining: {gold_remaining}")
```

</details>

<a id="exercise-05"></a>

### [05] Exercise: Experience Calculator · ⚔️⚔️ Medium

```text id="id3dc8"
A player currently has 450 experience points.

They complete a quest that gives 175 experience and defeat 3 enemies.
Each enemy gives 40 experience.

Calculate the final amount of experience.
```

**Expected output:**

```text id="56xf4n"
Final experience: 745
```

<details>
<summary>💡 Show solution</summary>

```python id="t53t3y"
experience = 450
quest_experience = 175
enemy_experience = 40
enemies_defeated = 3

final_experience = experience + quest_experience + (enemy_experience * enemies_defeated)

print(f"Final experience: {final_experience}")
```

</details>

## 3. Working with Text

<a id="exercise-06"></a>

### [06] Exercise: Character Card · ⚔️ Easy

```text id="46yvy8"
Given these variables:

player_name = "Jaina"
player_class = "Mage"
level = 30

Use an f-string to display the character information.
```

**Expected output:**

```text id="ykb14m"
Jaina | Mage | Level 30
```

<details>
<summary>💡 Show solution</summary>

```python id="cb65a1"
player_name = "Jaina"
player_class = "Mage"
level = 30

print(f"{player_name} | {player_class} | Level {level}")
```

</details>

## 4. User Input and Type Conversion

<a id="exercise-07"></a>

### [07] Exercise: Create Your Character · ⚔️ Easy

```text id="ihxky3"
Ask the user to enter:

- Character name
- Character class
- Level

Then display a simple character card.
```

**Example input:**

```text id="h4j4e3"
Character name: Jaina
Character class: Mage
Level: 30
```

**Expected output:**

```text id="25pq4h"
=== Character ===
Name: Jaina
Class: Mage
Level: 30
```

<details>
<summary>💡 Show solution</summary>

```python id="zvgdmz"
player_name = input("Character name: ")
player_class = input("Character class: ")
level = int(input("Level: "))

print("=== Character ===")
print(f"Name: {player_name}")
print(f"Class: {player_class}")
print(f"Level: {level}")
```

</details>

<a id="exercise-08"></a>

### [08] Exercise: Damage Calculator · ⚔️⚔️ Medium

```text id="f7f6z6"
Ask the user for:

- Enemy health
- Damage dealt

Calculate the enemy's remaining health.

Remember that values received with input() are strings.
```

**Example input:**

```text id="b1vjtl"
Enemy health: 120
Damage: 35
```

**Expected output:**

```text id="cdnsz2"
Enemy remaining health: 85
```

<details>
<summary>💡 Show solution</summary>

```python id="13h9se"
enemy_health = int(input("Enemy health: "))
damage = int(input("Damage: "))

remaining_health = enemy_health - damage

print(f"Enemy remaining health: {remaining_health}")
```

</details>

<a id="exercise-09"></a>

### [09] Exercise: Quest Calculator · ⚔️⚔️ Medium

```text id="xx4irw"
Ask the user for:

- Current gold
- Quest reward
- Repair cost

Calculate the final amount of gold after receiving the quest reward
and paying the repair cost.
```

**Example input:**

```text id="hynqgi"
Current gold: 100
Quest reward: 50
Repair cost: 20
```

**Expected output:**

```text id="y3w9y3"
Final gold: 130
```

<details>
<summary>💡 Show solution</summary>

```python id="dnbil4"
gold = float(input("Current gold: "))
quest_reward = float(input("Quest reward: "))
repair_cost = float(input("Repair cost: "))

final_gold = gold + quest_reward - repair_cost

print(f"Final gold: {final_gold}")
```

</details>

## 5. Mixed Practice

<a id="exercise-10"></a>

### [10] Exercise: Adventure Summary · ⚔️⚔️⚔️ Hard

```text id="v7mz3e"
Create a small program that asks the user for:

- Character name
- Level
- Current health
- Damage received
- Current gold
- Quest reward

Calculate:

- Remaining health after receiving damage
- Final gold after receiving the quest reward

Then display an adventure summary.
```

**Example input:**

```text id="3o79di"
Character name: Jaina
Level: 30
Current health: 100
Damage received: 25
Current gold: 115
Quest reward: 30
```

**Expected output:**

```text id="w81p8v"
=== Adventure Summary ===

Character: Jaina
Level: 30

Health: 75
Gold: 145
```

<details>
<summary>💡 Show solution</summary>

```python id="s11yp6"
player_name = input("Character name: ")
level = int(input("Level: "))
health = int(input("Current health: "))
damage = int(input("Damage received: "))
gold = int(input("Current gold: "))
quest_reward = int(input("Quest reward: "))

remaining_health = health - damage
final_gold = gold + quest_reward

print("=== Adventure Summary ===")
print()
print(f"Character: {player_name}")
print(f"Level: {level}")
print()
print(f"Health: {remaining_health}")
print(f"Gold: {final_gold}")
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