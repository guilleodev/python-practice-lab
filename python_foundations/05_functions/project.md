# 🚀 Module Project: Battle Manager

Use everything you learned about **Python Functions** to create an organized battle program.

⬅️ [Back to Exercises](exercises.md)

## 📜 Project

Create a **Battle Manager**.

Start with a list containing at least **3 enemies**.

Each enemy should be a dictionary containing:

```text id="e17eqw"
name
health
damage
```

Ask the user for:

```text id="3ohm5s"
Character name
Starting health
Damage per attack
```

Create functions to organize the battle:

```text id="sv5w9a"
show_character()
attack_enemy()
enemy_attack()
battle()
```

### Function Requirements

`show_character()` should display the character's name and current health.

`attack_enemy()` should:

```text id="9uc46j"
Receive the enemy health and player damage
Calculate the remaining enemy health
Return the new health
```

`enemy_attack()` should:

```text id="56mdac"
Receive the player health and enemy damage
Calculate the remaining player health
Return the new health
```

Health should never go below `0`.

`battle()` should:

```text id="dqhzga"
Receive the player information and one enemy
Repeat attacks until someone is defeated
Count the number of rounds
Display the result of the battle
Return the player's remaining health
```

Fight the enemies one by one.

If the player is defeated, stop the adventure.

If the player defeats every enemy, display a victory message.

### Example

```text id="6dfqoy"
Character name: Jaina
Starting health: 150
Damage per attack: 40

==========================
       BATTLE MANAGER
==========================

Jaina
Health: 150

Enemy: Wolf
Health: 60

Round 1
Jaina attacks: Wolf health = 20
Wolf attacks: Jaina health = 140

Round 2
Jaina attacks: Wolf health = 0

Wolf defeated!

Enemy: Bandit
Health: 80

...

==========================
       FINAL RESULT
==========================

Jaina survived all battles!
Final health: 70

==========================
```

## 💡 Solution

<details>
<summary>Show solution</summary>

```python id="jwp35c"
def show_character(name, health):
    print(name)
    print(f"Health: {health}")


def attack_enemy(enemy_health, player_damage):
    enemy_health = enemy_health - player_damage

    if enemy_health < 0:
        enemy_health = 0

    return enemy_health


def enemy_attack(player_health, enemy_damage):
    player_health = player_health - enemy_damage

    if player_health < 0:
        player_health = 0

    return player_health


def battle(player_name, player_health, player_damage, enemy):
    enemy_health = enemy["health"]
    round_number = 1

    print()
    print(f"Enemy: {enemy['name']}")
    print(f"Health: {enemy_health}")
    print()

    while player_health > 0 and enemy_health > 0:
        print(f"Round {round_number}")

        enemy_health = attack_enemy(enemy_health, player_damage)

        print(
            f"{player_name} attacks: "
            f"{enemy['name']} health = {enemy_health}"
        )

        if enemy_health == 0:
            print()
            print(f"{enemy['name']} defeated!")
            break

        player_health = enemy_attack(
            player_health,
            enemy["damage"]
        )

        print(
            f"{enemy['name']} attacks: "
            f"{player_name} health = {player_health}"
        )

        print()

        round_number = round_number + 1

    return player_health


enemies = [
    {
        "name": "Wolf",
        "health": 60,
        "damage": 10
    },
    {
        "name": "Bandit",
        "health": 80,
        "damage": 15
    },
    {
        "name": "Ogre",
        "health": 120,
        "damage": 25
    }
]

player_name = input("Character name: ")
player_health = int(input("Starting health: "))
player_damage = int(input("Damage per attack: "))

print()
print("==========================")
print("       BATTLE MANAGER")
print("==========================")
print()

show_character(player_name, player_health)

for enemy in enemies:
    if player_health <= 0:
        break

    player_health = battle(
        player_name,
        player_health,
        player_damage,
        enemy
    )

print()
print("==========================")
print("       FINAL RESULT")
print("==========================")
print()

if player_health > 0:
    print(f"{player_name} survived all battles!")
    print(f"Final health: {player_health}")
else:
    print(f"{player_name} was defeated!")

print()
print("==========================")
```

</details>

## 🧩 End of 05: Python Functions

➡️ Next: `06_comprehensions`

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>