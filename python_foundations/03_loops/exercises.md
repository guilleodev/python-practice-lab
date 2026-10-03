# 🔁 Python Loops - Exercises

Practice loops, ranges and repeated actions with these exercises.

> Try to solve each exercise by yourself before checking the solution.



⬅️ [Back to Theory](theory.md)

## 📚 Contents

- [1. For Loops and Range](#1-for-loops-and-range)
  - [01: Training Repetitions](#exercise-01)
  - [02: Level Progression](#exercise-02)
  - [03: Battle Countdown](#exercise-03)
- [2. While Loops](#2-while-loops)
  - [04: Enemy Health](#exercise-04)
  - [05: Collecting Gold](#exercise-05)
- [3. Controlling Loops](#3-controlling-loops)
  - [06: Stop the Training](#exercise-06)
  - [07: Skip a Round](#exercise-07)
- [4. Nested Loops](#4-nested-loops)
  - [08: Battle Rounds](#exercise-08)
- [5. Mixed Practice](#5-mixed-practice)
  - [09: Ability Unlock](#exercise-09)
  - [10: Battle Simulator](#exercise-10)

**Difficulty:** ⚔️ Easy · ⚔️⚔️ Medium · ⚔️⚔️⚔️ Hard

## 1. For Loops and Range

<a id="exercise-01"></a>

### [01] Exercise: Training Repetitions · ⚔️ Easy

```text
Use a for loop to print:

Attack!

5 times.
```

<details>
<summary>💡 Show solution</summary>

```python
for attack in range(5):
    print("Attack!")
```

</details>

<a id="exercise-02"></a>

### [02] Exercise: Level Progression · ⚔️ Easy

```text
Use range() to display the levels from 1 to 10.

Expected output:

Level 1
Level 2
...
Level 10
```

<details>
<summary>💡 Show solution</summary>

```python
for level in range(1, 11):
    print(f"Level {level}")
```

</details>

<a id="exercise-03"></a>

### [03] Exercise: Battle Countdown · ⚔️ Easy

```text
Create a countdown from 5 to 1 using range().

After the countdown, print:

Battle starts!
```

<details>
<summary>💡 Show solution</summary>

```python
for number in range(5, 0, -1):
    print(number)

print("Battle starts!")
```

</details>

## 2. While Loops

<a id="exercise-04"></a>

### [04] Exercise: Enemy Health · ⚔️⚔️ Medium

```text
An enemy starts with 100 health.

Each attack deals 20 damage.

Use a while loop to reduce and display the enemy's health until it reaches 0.
```

<details>
<summary>💡 Show solution</summary>

```python
enemy_health = 100
damage = 20

while enemy_health > 0:
    enemy_health = enemy_health - damage
    print(f"Enemy health: {enemy_health}")
```

</details>

<a id="exercise-05"></a>

### [05] Exercise: Collecting Gold · ⚔️⚔️ Medium

```text
The character starts with 0 gold.

Each completed quest gives 25 gold.

Use a while loop to complete quests until the character has at least 100 gold.

Display the current gold after each quest.
```

<details>
<summary>💡 Show solution</summary>

```python
gold = 0
quest_reward = 25

while gold < 100:
    gold = gold + quest_reward
    print(f"Gold: {gold}")
```

</details>

## 3. Controlling Loops

<a id="exercise-06"></a>

### [06] Exercise: Stop the Training · ⚔️⚔️ Medium

```text
Create a for loop with training rounds from 1 to 10.

Print each round.

When round 6 is reached, stop the loop using break.
```

<details>
<summary>💡 Show solution</summary>

```python
for round_number in range(1, 11):
    print(f"Round {round_number}")

    if round_number == 6:
        break
```

</details>

<a id="exercise-07"></a>

### [07] Exercise: Skip a Round · ⚔️⚔️ Medium

```text
Create a loop with rounds from 1 to 5.

Round 3 is a rest round.

Use continue so that round 3 is not displayed.
```

<details>
<summary>💡 Show solution</summary>

```python
for round_number in range(1, 6):
    if round_number == 3:
        continue

    print(f"Round {round_number}")
```

</details>

## 4. Nested Loops

<a id="exercise-08"></a>

### [08] Exercise: Battle Rounds · ⚔️⚔️ Medium

```text
Create 3 battle rounds.

Each round contains 2 enemies.

Use nested loops to display the round and the enemies inside it.

Example:

Round 1
Enemy 1
Enemy 2
Round 2
Enemy 1
Enemy 2
...
```

<details>
<summary>💡 Show solution</summary>

```python
for round_number in range(1, 4):
    print(f"Round {round_number}")

    for enemy in range(1, 3):
        print(f"Enemy {enemy}")
```

</details>

## 5. Mixed Practice

<a id="exercise-09"></a>

### [09] Exercise: Ability Unlock · ⚔️⚔️ Medium

```text
Display the levels from 1 to 10.

When the character reaches level 5, also display:

New ability unlocked!

The loop should continue until level 10.
```

<details>
<summary>💡 Show solution</summary>

```python
for level in range(1, 11):
    print(f"Level {level}")

    if level == 5:
        print("New ability unlocked!")
```

</details>

<a id="exercise-10"></a>

### [10] Exercise: Battle Simulator · ⚔️⚔️⚔️ Hard

```text
Ask the user for:

Enemy health
Damage per attack

Use a while loop to attack the enemy until its health reaches 0.

Count the number of attacks.

After each attack, display the remaining health.

When the enemy is defeated, display the total number of attacks.
```

<details>
<summary>💡 Show solution</summary>

```python
enemy_health = int(input("Enemy health: "))
damage = int(input("Damage per attack: "))

attacks = 0

while enemy_health > 0:
    enemy_health = enemy_health - damage
    attacks = attacks + 1

    if enemy_health < 0:
        enemy_health = 0

    print(f"Enemy health: {enemy_health}")

print(f"Enemy defeated in {attacks} attacks!")
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