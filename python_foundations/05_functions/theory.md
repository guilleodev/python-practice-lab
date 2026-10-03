# 🧩 Python Functions - Theory

Functions allow us to organize code into reusable blocks that perform a specific task.

Instead of writing the same code multiple times, we can create a function once and call it whenever we need it.

## 📚 Contents

- [1. Understanding Functions](#1-understanding-functions)
- [2. Creating and Calling Functions](#2-creating-and-calling-functions)
- [3. Parameters and Arguments](#3-parameters-and-arguments)
- [4. Returning Values](#4-returning-values)
- [5. Multiple Parameters](#5-multiple-parameters)
- [6. Default Parameters](#6-default-parameters)
- [7. Local Variables](#7-local-variables)
- [8. Multiple Return Values](#8-multiple-return-values)
- [9. Using *args](#9-using-args)
- [10. Type Hints](#10-type-hints)
- [11. Combining Functions](#11-combining-functions)
- [📌 Cheat Sheet: 05 Functions](#-cheat-sheet-05-functions)

## 1. Understanding Functions

Imagine that we want to display the same message several times:

```python
print("Quest completed!")
print("Quest completed!")
print("Quest completed!")
```

We could create a function instead:

```python
def complete_quest():
    print("Quest completed!")
```

Now we can use it whenever we need it:

```python
complete_quest()
complete_quest()
complete_quest()
```

A function allows us to:

```text
Organize code
Reuse code
Avoid repetition
Divide a program into smaller tasks
```

Python already provides many built-in functions that we have been using:

```python
print()
input()
len()
type()
int()
float()
```

We can also create our own functions.

## 2. Creating and Calling Functions

Functions are created using `def`.

```python
def show_message():
    print("Welcome to the adventure!")
```

Creating the function does not execute its code.

To execute it, we **call the function**:

```python
show_message()
```

Output:

```text
Welcome to the adventure!
```

The basic structure is:

```python
def function_name():
    # code
```

And we execute it with:

```python
function_name()
```

> [!NOTE]
> Function names usually follow the same `snake_case` convention as variables.

For example:

```python
def show_player_info():
    print("Player information")
```

## 3. Parameters and Arguments

Functions become more useful when we can give them information.

```python
def greet_player(name):
    print(f"Welcome, {name}!")
```

Now we can call the function with different values:

```python
greet_player("Jaina")
greet_player("Valeera")
```

Output:

```text
Welcome, Jaina!
Welcome, Valeera!
```

In this example:

```python
def greet_player(name):
```

`name` is a **parameter**.

When we call:

```python
greet_player("Jaina")
```

`"Jaina"` is an **argument**.

A simple way to remember it:

```text
Parameter -> variable defined by the function

Argument  -> actual value sent to the function
```

## 4. Returning Values

Functions can calculate something and send the result back using `return`.

```python
def calculate_damage(health, damage):
    remaining_health = health - damage
    return remaining_health
```

Now we can store the returned value:

```python
health = calculate_damage(100, 30)

print(health)
```

Output:

```text
70
```

The important idea is:

```text
print()  -> displays a value

return   -> sends a value back
```

For example:

```python
def add_gold(gold, reward):
    return gold + reward
```

Then:

```python
final_gold = add_gold(100, 50)

print(final_gold)
```

Output:

```text
150
```

### 4.1 Returning Directly

Sometimes we do not need an extra variable inside the function.

Instead of:

```python
def add_gold(gold, reward):
    final_gold = gold + reward
    return final_gold
```

We can write:

```python
def add_gold(gold, reward):
    return gold + reward
```

Both versions do the same thing.

## 5. Multiple Parameters

A function can receive several parameters.

```python
def show_player(name, player_class, level):
    print(f"{name} - {player_class} - Level {level}")
```

Call it with:

```python
show_player("Jaina", "Mage", 30)
```

Output:

```text
Jaina - Mage - Level 30
```

The arguments are normally assigned according to their position:

```text
name          -> "Jaina"
player_class  -> "Mage"
level         -> 30
```

You can also specify the parameter names:

```python
show_player(
    name="Jaina",
    player_class="Mage",
    level=30
)
```

These are called **keyword arguments**.

## 6. Default Parameters

Parameters can have default values.

```python
def greet_player(name, message="Welcome"):
    print(f"{message}, {name}!")
```

Now this works:

```python
greet_player("Jaina")
```

Output:

```text
Welcome, Jaina!
```

But we can also replace the default value:

```python
greet_player("Jaina", "Good luck")
```

Output:

```text
Good luck, Jaina!
```

Default parameters are useful when a value is usually the same but can sometimes change.

Another example:

```python
def calculate_experience(enemies, experience_per_enemy=40):
    return enemies * experience_per_enemy
```

```python
print(calculate_experience(5))
print(calculate_experience(5, 100))
```

Output:

```text
200
500
```

## 7. Local Variables

Variables created inside a function are normally **local variables**.

```python
def calculate_reward():
    reward = 100
    print(reward)
```

`reward` exists inside the function.

```python
calculate_reward()
```

Output:

```text
100
```

But this would produce an error:

```python
print(reward)
```

because `reward` was created inside the function.

This is called **scope**.

```text
Inside the function  -> local scope
Outside the function -> global scope
```

For now, the important idea is:

> [!NOTE]
> Variables created inside a function should normally be used inside that function or returned with `return`.

For example:

```python
def calculate_reward(enemies):
    reward = enemies * 25
    return reward

total_reward = calculate_reward(4)

print(total_reward)
```

## 8. Multiple Return Values

A function can return more than one value.

```python
def battle_result(health, damage):
    remaining_health = health - damage
    defeated = remaining_health <= 0

    return remaining_health, defeated
```

We can receive both values:

```python
health, defeated = battle_result(100, 30)

print(health)
print(defeated)
```

Output:

```text
70
False
```

Python returns these values together.

This is useful when a function calculates several related results.

Another example:

```python
def calculate_quest(enemies, gold_per_enemy):
    experience = enemies * 40
    gold = enemies * gold_per_enemy

    return experience, gold
```

```python
experience, gold = calculate_quest(5, 10)

print(experience)
print(gold)
```

## 9. Using `*args`

Sometimes we do not know how many arguments a function will receive.

For this situation, Python provides `*args`.

```python
def calculate_average(*numbers):
    total = 0

    for number in numbers:
        total = total + number

    return total / len(numbers)
```

Now we can call the same function with different numbers of arguments:

```python
print(calculate_average(10, 20))
print(calculate_average(10, 20, 30))
print(calculate_average(10, 20, 30, 40))
```

Inside the function, `numbers` behaves like a tuple.

For example:

```python
def show_items(*items):
    print(items)
```

```python
show_items("Potion", "Sword", "Shield")
```

Output:

```text
('Potion', 'Sword', 'Shield')
```

We can therefore loop through the values:

```python
def show_items(*items):
    for item in items:
        print(item)
```

> [!NOTE]
> The name `args` is a convention. The `*` is the important part.

This would also work:

```python
def show_items(*inventory):
    for item in inventory:
        print(item)
```

## 10. Type Hints

Python allows us to indicate what type of data a function expects.

```python
def calculate_damage(health: int, damage: int):
    return health - damage
```

We can also indicate the type returned by the function:

```python
def calculate_damage(health: int, damage: int) -> int:
    return health - damage
```

Another example:

```python
def greet_player(name: str) -> str:
    return f"Welcome, {name}!"
```

Type hints make the function easier to understand:

```text
name: str  -> name should be a string

-> str     -> the function returns a string
```

They are especially useful when programs become larger.

> [!NOTE]
> Type hints do not automatically prevent you from passing another type. They mainly help document and understand the code.

For example:

```python
def add_gold(gold: float, reward: float) -> float:
    return gold + reward
```

## 11. Combining Functions

A program can contain multiple functions, each responsible for a different task.

```python
def calculate_health(health, damage):
    remaining_health = health - damage

    if remaining_health < 0:
        remaining_health = 0

    return remaining_health


def calculate_experience(enemies):
    return enemies * 40


def show_report(name, health, experience):
    print("==========================")
    print("      PLAYER REPORT")
    print("==========================")
    print(f"Character: {name}")
    print(f"Health: {health}")
    print(f"Experience: {experience}")
```

Now we can use them together:

```python
player_name = input("Character name: ")
health = int(input("Health: "))
damage = int(input("Damage received: "))
enemies = int(input("Enemies defeated: "))

final_health = calculate_health(health, damage)
experience = calculate_experience(enemies)

show_report(player_name, final_health, experience)
```

Instead of having one large block of code, each function has a clear responsibility:

```text
calculate_health()      -> calculates health

calculate_experience()  -> calculates experience

show_report()           -> displays information
```

This makes programs easier to organize, understand and reuse.

## 📌 Cheat Sheet: 05 Functions

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

## 🧩 Next Step

➡️ [Continue with the exercises](exercises.md)

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>