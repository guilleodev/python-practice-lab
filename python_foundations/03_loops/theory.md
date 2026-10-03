# 🔁 Python Loops - Theory

Loops allow a program to repeat code multiple times without writing the same instructions again and again.

## 📚 Contents

- [1. Understanding Loops](#1-understanding-loops)
- [2. The for Loop](#2-the-for-loop)
- [3. Using range()](#3-using-range)
- [4. The while Loop](#4-the-while-loop)
- [5. The break Statement](#5-the-break-statement)
- [6. The continue Statement](#6-the-continue-statement)
- [7. Nested Loops](#7-nested-loops)
- [8. Combining Loops with Conditionals](#8-combining-loops-with-conditionals)
- [📌 Cheat Sheet: 03 Loops](#-cheat-sheet-03-loops)

## 1. Understanding Loops

A **loop** allows us to execute the same block of code multiple times.

Without a loop:

```python
print("Attack!")
print("Attack!")
print("Attack!")
```

With a loop:

```python
for attack in range(3):
    print("Attack!")
```

Both examples print:

```text
Attack!
Attack!
Attack!
```

Loops are useful when we need to repeat an action without repeating the code manually.

Python has two main types of loops:

```text
for
while
```

## 2. The for Loop

A `for` loop repeats code a specific number of times or for each element in a sequence.

For now, we will use it mainly with `range()`.

```python
for attack in range(3):
    print("Attack!")
```

The variable `attack` changes its value during each iteration.

```python
for attack in range(3):
    print(attack)
```

Output:

```text
0
1
2
```

By default, counting starts at `0`.

### The Loop Variable

The variable after `for` represents the current iteration.

```python
for enemy in range(1, 4):
    print(f"Enemy {enemy}")
```

Output:

```text
Enemy 1
Enemy 2
Enemy 3
```

The variable name can be anything, but it should describe what it represents.

For example:

```python
for level in range(1, 6):
    print(f"Level {level}")
```

## 3. Using range()

`range()` generates a sequence of numbers that can be used by a `for` loop.

There are three common ways to use it.

### 3.1 `range(stop)`

```python
for number in range(5):
    print(number)
```

Output:

```text
0
1
2
3
4
```

The stop value is **not included**.

### 3.2 `range(start, stop)`

You can choose where the sequence starts.

```python
for level in range(1, 6):
    print(level)
```

Output:

```text
1
2
3
4
5
```

Python starts at `1` and stops before `6`.

### 3.3 `range(start, stop, step)`

The third value controls how much the number changes on each iteration.

```python
for number in range(0, 11, 2):
    print(number)
```

Output:

```text
0
2
4
6
8
10
```

The step can also be negative.

```python
for number in range(5, 0, -1):
    print(number)
```

Output:

```text
5
4
3
2
1
```

This can be useful for countdowns.

## 4. The while Loop

A `while` loop repeats code **while a condition remains `True`**.

```python
health = 100

while health > 0:
    print(f"Health: {health}")
    health = health - 25
```

Output:

```text
Health: 100
Health: 75
Health: 50
Health: 25
```

Unlike a `for` loop, a `while` loop does not necessarily have a fixed number of repetitions.

It continues until its condition becomes `False`.

### Updating the Condition

A `while` loop usually needs to change something inside the loop.

```python
enemy_health = 100

while enemy_health > 0:
    enemy_health = enemy_health - 20
    print(f"Enemy health: {enemy_health}")
```

Without changing `enemy_health`, the condition would always remain `True`.

This would create an **infinite loop**.

For example:

```python
health = 100

while health > 0:
    print("This never stops!")
```

Because `health` never changes, `health > 0` is always `True`.

## 5. The break Statement

`break` immediately stops a loop.

```python
for round_number in range(1, 11):
    print(f"Round {round_number}")

    if round_number == 5:
        break
```

Output:

```text
Round 1
Round 2
Round 3
Round 4
Round 5
```

Even though the loop could continue until round 10, `break` stops it when the round reaches 5.

It can also be useful inside a `while` loop:

```python
gold = 0

while True:
    gold = gold + 10
    print(f"Gold: {gold}")

    if gold >= 50:
        break
```

`while True` creates a loop that would continue forever, but `break` provides a way to stop it.

## 6. The continue Statement

`continue` skips the rest of the current iteration and moves to the next one.

```python
for level in range(1, 6):
    if level == 3:
        continue

    print(f"Level {level}")
```

Output:

```text
Level 1
Level 2
Level 4
Level 5
```

When `level` is `3`, Python executes `continue` and skips the `print()` for that iteration.

The loop itself does not stop.

This is the main difference:

```text
break       stops the entire loop
continue    skips only the current iteration
```

## 7. Nested Loops

A loop can exist inside another loop.

This is called a **nested loop**.

```python
for round_number in range(1, 4):
    print(f"Round {round_number}")

    for enemy in range(1, 3):
        print(f"Enemy {enemy}")
```

Output:

```text
Round 1
Enemy 1
Enemy 2
Round 2
Enemy 1
Enemy 2
Round 3
Enemy 1
Enemy 2
```

The inner loop completes all its iterations for every iteration of the outer loop.

In this example:

```text
Outer loop: 3 rounds
Inner loop: 2 enemies per round

Total enemy iterations: 3 × 2 = 6
```

Nested loops are useful when an action needs to be repeated inside another repeated action.

## 8. Combining Loops with Conditionals

Loops become especially useful when combined with the conditionals from the previous module.

For example:

```python
for level in range(1, 11):
    if level == 5:
        print("New ability unlocked!")

    print(f"Level: {level}")
```

A condition can make something special happen during a specific iteration.

We can also use several conditions:

```python
for round_number in range(1, 6):
    if round_number == 3:
        print("Boss appears!")
    elif round_number == 5:
        print("Final round!")

    print(f"Round {round_number}")
```

Another common example is combining a `while` loop with calculations:

```python
enemy_health = 100
damage = 30

while enemy_health > 0:
    enemy_health = enemy_health - damage

    if enemy_health <= 0:
        enemy_health = 0
        print("Enemy defeated!")
    else:
        print(f"Enemy health: {enemy_health}")
```

Now the program can repeat actions and make decisions during each repetition.

## 📌 Cheat Sheet: 03 Loops

```python
# for loop
for i in range(5):
    print(i)

# range(stop)
for i in range(5):
    print(i)
# 0, 1, 2, 3, 4

# range(start, stop)
for i in range(1, 6):
    print(i)
# 1, 2, 3, 4, 5

# range(start, stop, step)
for i in range(0, 11, 2):
    print(i)
# 0, 2, 4, 6, 8, 10

# Countdown
for i in range(5, 0, -1):
    print(i)

# while loop
health = 100

while health > 0:
    health = health - 20
    print(health)

# break
for i in range(10):
    if i == 5:
        break

    print(i)

# continue
for i in range(5):
    if i == 2:
        continue

    print(i)

# Nested loops
for i in range(3):
    for j in range(2):
        print(i, j)

# Loop + condition
for level in range(1, 6):
    if level == 3:
        print("New ability unlocked!")

    print(level)
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