# 🚀 Module Project: Party Manager

Use everything you learned about **Python Data Structures** to organize and analyze a small group of characters.

⬅️ [Back to Exercises](exercises.md)

## 📜 Project

Create a **Party Manager**.

Your party should contain at least **3 characters**.

Each character should be a dictionary containing:

```text id="2k5rqc"
name
class
level
health
inventory
```

The `inventory` should be a list with at least two items.

Store all the characters inside a list.

Your program should:

```text id="xaxw1e"
Display each character and their information
Display whether each character is Ready or Defeated
Count how many characters are Ready
Count how many characters are Defeated
Find the highest level in the party
Store the unique character classes in a set
Display the party summary
```

A character is **Ready** if their health is greater than `0`.

### Example

```text id="qxd7qf"
==========================
       PARTY MANAGER
==========================

Jaina - Mage - Level 30
Health: 100
Status: Ready
Inventory: ['Potion', 'Staff']

Arthas - Paladin - Level 25
Health: 0
Status: Defeated
Inventory: ['Sword', 'Shield']

Valeera - Rogue - Level 20
Health: 75
Status: Ready
Inventory: ['Dagger', 'Potion']

==========================
       PARTY SUMMARY
==========================

Party members: 3
Ready: 2
Defeated: 1
Highest level: 30
Classes: {'Mage', 'Paladin', 'Rogue'}

==========================
```

> [!NOTE]
> Sets are unordered, so the classes may appear in a different order.

## 💡 Solution

<details>
<summary>Show solution</summary>

```python id="shp3m2"
players = [
    {
        "name": "Jaina",
        "class": "Mage",
        "level": 30,
        "health": 100,
        "inventory": ["Potion", "Staff"]
    },
    {
        "name": "Arthas",
        "class": "Paladin",
        "level": 25,
        "health": 0,
        "inventory": ["Sword", "Shield"]
    },
    {
        "name": "Valeera",
        "class": "Rogue",
        "level": 20,
        "health": 75,
        "inventory": ["Dagger", "Potion"]
    }
]

ready_players = 0
defeated_players = 0
highest_level = 0
classes = set()

print("==========================")
print("       PARTY MANAGER")
print("==========================")
print()

for player in players:
    print(f"{player['name']} - {player['class']} - Level {player['level']}")
    print(f"Health: {player['health']}")

    if player["health"] > 0:
        print("Status: Ready")
        ready_players = ready_players + 1
    else:
        print("Status: Defeated")
        defeated_players = defeated_players + 1

    if player["level"] > highest_level:
        highest_level = player["level"]

    classes.add(player["class"])

    print(f"Inventory: {player['inventory']}")
    print()

print("==========================")
print("       PARTY SUMMARY")
print("==========================")
print()

print(f"Party members: {len(players)}")
print(f"Ready: {ready_players}")
print(f"Defeated: {defeated_players}")
print(f"Highest level: {highest_level}")
print(f"Classes: {classes}")

print()
print("==========================")
```

</details>

## 🗂️ End of 04: Python Data Structures

➡️ Next: `05_functions`

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>