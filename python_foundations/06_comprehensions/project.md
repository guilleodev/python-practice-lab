# 🚀 Module Project: Player Data Analyzer

Use everything you learned about **Python Comprehensions** to analyze and transform a collection of players.

⬅️ [Back to Exercises](exercises.md)

## 📜 Project

Create a **Player Data Analyzer**.

Start with this list of players:

```python
players = [
    {"name": "Jaina", "level": 30, "health": 100, "class": "Mage"},
    {"name": "Valeera", "level": 20, "health": 70, "class": "Rogue"},
    {"name": "Arthas", "level": 35, "health": 0, "class": "Paladin"},
    {"name": "Thrall", "level": 25, "health": 90, "class": "Warrior"},
    {"name": "Anduin", "level": 15, "health": 60, "class": "Priest"},
    {"name": "Khadgar", "level": 40, "health": 80, "class": "Mage"}
]
```

Use comprehensions to create:

```text
A list containing only active players
A list containing the names of players level 25 or higher
A dictionary with each player's name and health
A set containing the unique character classes
A list containing each player's name in uppercase
```

A player is considered **active** when their health is greater than `0`.

Then create a new list containing the active players and add a new key called `status`.

The status should be:

```text
Healthy  -> health greater than 70
Injured  -> health 70 or lower
```

Finally, use a generator expression to calculate the experience values for levels from `1` to `1,000,000`.

Each level requires:

```text
level * 100 experience points
```

Display only the first **5 values** from the generator.

### Example

```text
==========================
    PLAYER DATA ANALYZER
==========================

Active players:
['Jaina', 'Valeera', 'Thrall', 'Anduin', 'Khadgar']

Level 25+:
['Jaina', 'Thrall', 'Khadgar']

Player health:
{'Jaina': 100, 'Valeera': 70, 'Arthas': 0, 'Thrall': 90, 'Anduin': 60, 'Khadgar': 80}

Classes:
{'Mage', 'Rogue', 'Paladin', 'Warrior', 'Priest'}

Uppercase names:
['JAINA', 'VALEERA', 'ARTHAS', 'THRALL', 'ANDUIN', 'KHADGAR']

Active player status:
Jaina: Healthy
Valeera: Injured
Thrall: Healthy
Anduin: Injured
Khadgar: Healthy

First experience values:
100
200
300
400
500

==========================
```

> [!NOTE]
> Sets are unordered, so the classes may appear in a different order.

## 💡 Solution

<details>
<summary>Show solution</summary>

```python
players = [
    {"name": "Jaina", "level": 30, "health": 100, "class": "Mage"},
    {"name": "Valeera", "level": 20, "health": 70, "class": "Rogue"},
    {"name": "Arthas", "level": 35, "health": 0, "class": "Paladin"},
    {"name": "Thrall", "level": 25, "health": 90, "class": "Warrior"},
    {"name": "Anduin", "level": 15, "health": 60, "class": "Priest"},
    {"name": "Khadgar", "level": 40, "health": 80, "class": "Mage"}
]

active_players = [
    player
    for player in players
    if player["health"] > 0
]

active_names = [
    player["name"]
    for player in active_players
]

high_level_players = [
    player["name"]
    for player in players
    if player["level"] >= 25
]

player_health = {
    player["name"]: player["health"]
    for player in players
}

classes = {
    player["class"]
    for player in players
}

uppercase_names = [
    player["name"].upper()
    for player in players
]

players_with_status = [
    {
        "name": player["name"],
        "health": player["health"],
        "status": "Healthy" if player["health"] > 70 else "Injured"
    }
    for player in active_players
]

experience_generator = (
    level * 100
    for level in range(1, 1_000_001)
)

print("==========================")
print("    PLAYER DATA ANALYZER")
print("==========================")
print()

print("Active players:")
print(active_names)
print()

print("Level 25+:")
print(high_level_players)
print()

print("Player health:")
print(player_health)
print()

print("Classes:")
print(classes)
print()

print("Uppercase names:")
print(uppercase_names)
print()

print("Active player status:")

for player in players_with_status:
    print(f"{player['name']}: {player['status']}")

print()
print("First experience values:")

count = 0

for experience in experience_generator:
    print(experience)

    count = count + 1

    if count == 5:
        break

print()
print("==========================")
```

</details>

## ⚡ Work in progress...

➡️ Next: `08_POO`

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>