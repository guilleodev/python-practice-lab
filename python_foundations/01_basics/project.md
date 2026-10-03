# 🚀 Module Project 01: Adventure Report

Use everything you learned in **Python Basics** to create a small interactive program.

⬅️ [Back to Exercises](exercises.md)

## 📜 Project

Create an **Adventure Report**.

Your program should ask the user for:

```text
Character name
Character class
Starting health
Damage received
Starting gold
Quest reward
Enemies defeated
```

> [!NOTE]
> Each defeated enemy gives **40 experience points**.

Your program should calculate:

```text
Remaining health
Final gold
Experience earned
```

Then display a final report with the character's results.

### Example

```text
Character name: Jaina
Character class: Mage
Starting health: 100
Damage received: 35
Starting gold: 120
Quest reward: 50
Enemies defeated: 4

==========================
     ADVENTURE REPORT
==========================

Character: Jaina
Class: Mage

Health: 65
Gold: 170
Enemies defeated: 4
Experience earned: 160

==========================
```

You can customize the final report as long as it includes the required information and calculations.

## 💡 Solution

<details>
<summary>Show solution</summary>

```python
player_name = input("Character name: ")
player_class = input("Character class: ")

starting_health = int(input("Starting health: "))
damage_received = int(input("Damage received: "))

starting_gold = float(input("Starting gold: "))
quest_reward = float(input("Quest reward: "))

enemies_defeated = int(input("Enemies defeated: "))
experience_per_enemy = 40

remaining_health = starting_health - damage_received
final_gold = starting_gold + quest_reward
experience_earned = enemies_defeated * experience_per_enemy

print()
print("==========================")
print("     ADVENTURE REPORT")
print("==========================")
print()
print(f"Character: {player_name}")
print(f"Class: {player_class}")
print()
print(f"Health: {remaining_health}")
print(f"Gold: {final_gold}")
print(f"Enemies defeated: {enemies_defeated}")
print(f"Experience earned: {experience_earned}")
print()
print("==========================")
```

</details>

## 🐍 End of 01: Python Basics

➡️ Next: `02_conditionals`

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>