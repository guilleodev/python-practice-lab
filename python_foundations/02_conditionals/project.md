# 🚀 Module Project 02: Adventure Decision

Use everything you learned in **Python Conditionals** to create a program that makes decisions based on the character's situation.

⬅️ [Back to Exercises](exercises.md)

## 📜 Project

Create an **Adventure Decision** program.

Your program should ask the user for:

```text
Character name
Character class
Health
Gold
Difficulty
```

Determine the character's status:

```text
Health greater than 50: Healthy
Health greater than 0: Injured
Health 0 or less: Defeated
```

The character is ready to continue the adventure only if they have **more than 0 health** and **at least 50 gold**.

Use `match / case` to determine the enemy power:

```text
easy: 25
normal: 50
hard: 75
```

> [!NOTE]
> If the difficulty is not valid, set the enemy power to `0`.

Finally, display the character's information and whether they are ready to continue the adventure.

### Example

```text
Character name: Jaina
Character class: Mage
Health: 80
Gold: 120
Difficulty: hard

==========================
    ADVENTURE DECISION
==========================

Character: Jaina
Class: Mage
Status: Healthy
Difficulty: hard
Enemy power: 75

Ready to continue!

==========================
```

## 💡 Solution

<details>
<summary>Show solution</summary>

```python
player_name = input("Character name: ")
player_class = input("Character class: ")
health = int(input("Health: "))
gold = float(input("Gold: "))
difficulty = input("Difficulty: ")

if health > 50:
    status = "Healthy"
elif health > 0:
    status = "Injured"
else:
    status = "Defeated"

match difficulty:
    case "easy":
        enemy_power = 25
    case "normal":
        enemy_power = 50
    case "hard":
        enemy_power = 75
    case _:
        enemy_power = 0

if health > 0 and gold >= 50:
    adventure_result = "Ready to continue!"
else:
    adventure_result = "Return to town!"

print()
print("==========================")
print("    ADVENTURE DECISION")
print("==========================")
print()
print(f"Character: {player_name}")
print(f"Class: {player_class}")
print(f"Status: {status}")
print(f"Difficulty: {difficulty}")
print(f"Enemy power: {enemy_power}")
print()
print(adventure_result)
print()
print("==========================")
```

</details>

## 🔀 End of 02: Python Conditionals

➡️ Next: `03_loops`

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>