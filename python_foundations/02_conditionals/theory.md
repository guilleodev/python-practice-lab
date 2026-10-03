# 🔀 Python Conditionals - Theory

Conditionals allow a program to make decisions and execute different code depending on whether a condition is true or false.

## 📚 Contents

- [1. Understanding Conditions](#1-understanding-conditions)
- [2. Comparison Operators](#2-comparison-operators)
- [3. The if Statement](#3-the-if-statement)
- [4. The else Statement](#4-the-else-statement)
- [5. The elif Statement](#5-the-elif-statement)
- [6. Logical Operators](#6-logical-operators)
- [7. Combining Conditions](#7-combining-conditions)
- [8. Match / Case](#8-match--case)
- [📌 Cheat Sheet: 02 Conditionals](#-cheat-sheet-02-conditionals)

## 1. Understanding Conditions

A **condition** is an expression that Python evaluates as either `True` or `False`.

For example:

```python id="r5d9ch"
level = 15

print(level >= 10)
```

Output:

```text id="knqfxd"
True
```

Another example:

```python id="i9g1cb"
gold = 50

print(gold >= 100)
```

Output:

```text id="zg9sfq"
False
```

These Boolean values allow our programs to make decisions.

## 2. Comparison Operators

Comparison operators compare two values and return either `True` or `False`.

| Operator | Meaning |
|---|---|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

Example:

```python id="e4f00x"
level = 20

print(level == 20)
print(level != 10)
print(level > 15)
print(level < 30)
print(level >= 20)
print(level <= 20)
```

### `=` vs `==`

These two operators have different purposes.

`=` assigns a value to a variable:

```python id="69sv7x"
level = 20
```

`==` compares two values:

```python id="07hyc5"
level == 20
```

The comparison returns:

```text id="s4a4va"
True
```

## 3. The if Statement

The `if` statement executes code only when a condition is `True`.

```python id="qklk4b"
health = 75

if health > 0:
    print("The character is alive.")
```

Python checks:

```text id="lnmvgr"
Is health greater than 0?
```

If the answer is `True`, the indented code runs.

If the condition is `False`, Python skips it.

### Indentation

Indentation is important in Python.

The code that belongs to an `if` statement must be indented:

```python id="r1smp9"
gold = 150

if gold >= 100:
    print("You have enough gold.")
    print("You can buy the item.")

print("Game continues.")
```

The first two `print()` statements belong to the `if`.

The last one does not, so it will always run.

## 4. The else Statement

`else` allows us to execute different code when the condition is `False`.

```python id="cmfr5i"
gold = 75

if gold >= 100:
    print("You can buy the item.")
else:
    print("You don't have enough gold.")
```

Only one of these two paths will execute.

Another example:

```python id="8r4tgg"
health = 0

if health > 0:
    print("The character is alive.")
else:
    print("The character has been defeated.")
```

## 5. The elif Statement

Sometimes we need more than two possible paths.

`elif` means **else if** and allows us to check another condition.

```python id="wmq8np"
health = 60

if health > 75:
    print("Health is high.")
elif health > 25:
    print("Health is medium.")
else:
    print("Health is low.")
```

Python checks the conditions from top to bottom.

As soon as one condition is `True`, its code runs and the remaining conditions are skipped.

You can use multiple `elif` statements:

```python id="avk8bo"
level = 25

if level >= 30:
    print("High level.")
elif level >= 20:
    print("Medium level.")
elif level >= 10:
    print("Low level.")
else:
    print("Beginner level.")
```

## 6. Logical Operators

Logical operators allow us to combine or modify conditions.

The three basic logical operators are:

| Operator | Meaning |
|---|---|
| `and` | Both conditions must be `True` |
| `or` | At least one condition must be `True` |
| `not` | Reverses `True` and `False` |

### 6.1 `and`

`and` requires both conditions to be true.

```python id="7kfx13"
level = 15
gold = 120

if level >= 10 and gold >= 100:
    print("You can buy the item.")
```

Both requirements must be met.

### 6.2 `or`

`or` requires at least one condition to be true.

```python id="16irh9"
player_class = "Mage"
level = 20

if player_class == "Mage" or level >= 30:
    print("You can enter.")
```

Only one of the conditions needs to be `True`.

### 6.3 `not`

`not` reverses a Boolean value.

```python id="6x7ylq"
quest_completed = False

if not quest_completed:
    print("The quest is still active.")
```

Here:

```text id="v7i8zm"
quest_completed = False
not quest_completed = True
```

## 7. Combining Conditions

Conditions become more useful when combined with concepts from the previous module.

For example, we can ask the user for information and make a decision based on it:

```python id="6dwg2n"
player_name = input("Character name: ")
level = int(input("Level: "))
gold = float(input("Gold: "))

if level >= 10 and gold >= 100:
    print(f"{player_name} can buy the item.")
else:
    print(f"{player_name} cannot buy the item.")
```

We can also combine calculations with conditions:

```python id="8wwu24"
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

The program now does more than calculate a result.

It can **react differently depending on that result**.

## 8. Match / Case

`match` and `case` allow you to execute different code depending on the value of a variable.

It is useful when you want to compare the **same value against several possible options**.

```python id="pj7f06"
player_class = "Mage"

match player_class:
    case "Warrior":
        print("You chose Warrior.")
    case "Mage":
        print("You chose Mage.")
    case "Rogue":
        print("You chose Rogue.")
```

Python checks the value after `match` and executes the matching `case`.

In this example:

```text id="eb3b8f"
player_class = "Mage"
```

Python executes:

```python id="o9l3cm"
case "Mage":
    print("You chose Mage.")
```

### 8.1 Default Case

You can use `_` as a default case.

It runs when none of the previous cases match.

```python id="6qes4i"
player_class = "Druid"

match player_class:
    case "Warrior":
        print("You chose Warrior.")
    case "Mage":
        print("You chose Mage.")
    case "Rogue":
        print("You chose Rogue.")
    case _:
        print("Unknown class.")
```

### 8.2 When to Use Match

`match` can be useful when one variable can have several specific values.

For example:

```python id="i3e8oc"
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

A similar program could also be written using `if`, `elif` and `else`.

`match` simply provides another way to organize this type of decision.

## 📌 Cheat Sheet: 02 Conditionals

```python id="3p0qqz"
# Comparison operators
x == y    # Equal to
x != y    # Not equal to
x > y     # Greater than
x < y     # Less than
x >= y    # Greater than or equal to
x <= y    # Less than or equal to


# Basic if
if condition:
    print("The condition is true.")


# if / else
if condition:
    print("True")
else:
    print("False")


# if / elif / else
if condition_1:
    print("Option 1")
elif condition_2:
    print("Option 2")
else:
    print("Option 3")


# Logical operators
condition_1 and condition_2    # Both must be True
condition_1 or condition_2     # At least one must be True
not condition                  # Reverses True and False


# Combining conditions
level = 15
gold = 120

if level >= 10 and gold >= 100:
    print("Requirements met.")
else:
    print("Requirements not met.")


# match / case
match value:
    case "option_1":
        print("Option 1")
    case "option_2":
        print("Option 2")
    case _:
        print("Unknown option")
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