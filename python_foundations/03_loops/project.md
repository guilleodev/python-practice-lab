# 🚀 Module Project: Battle Simulator

Use everything you learned about **Python Loops** to create a simple battle simulation.

⬅️ [Back to Exercises](exercises.md)

## 📜 Project

Create a **Battle Simulator**.

Your program should ask the user for:

```text id="f4ed02"
Character name
Enemy health
Damage per attack
```

The character attacks the enemy repeatedly until its health reaches `0`.

Your program should:

```text id="832e0c"
Count each attack
Reduce the enemy's health
Display the result of each attack
Stop when the enemy is defeated
```

> [!NOTE]
> Enemy health should never be displayed below `0`.

Finally, display the total number of attacks needed to defeat the enemy.

### Example

```text id="t0f37e"
Character name: Jaina
Enemy health: 100
Damage per attack: 30

==========================
      BATTLE START
==========================

Attack 1: Enemy health = 70
Attack 2: Enemy health = 40
Attack 3: Enemy health = 10
Attack 4: Enemy health = 0

Jaina defeated the enemy in 4 attacks!

==========================
```

## 💡 Solution

<details>
<summary>Show solution</summary>

```python id="u54p17"
player_name = input("Character name: ")
enemy_health = int(input("Enemy health: "))
damage = int(input("Damage per attack: "))

attacks = 0

print()
print("==========================")
print("      BATTLE START")
print("==========================")
print()

while enemy_health > 0:
    attacks = attacks + 1
    enemy_health = enemy_health - damage

    if enemy_health < 0:
        enemy_health = 0

    print(f"Attack {attacks}: Enemy health = {enemy_health}")

print()
print(f"{player_name} defeated the enemy in {attacks} attacks!")
print()
print("==========================")
```

</details>

## 🔁 End of 03: Python Loops

➡️ Next: `04_data_structures`

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>