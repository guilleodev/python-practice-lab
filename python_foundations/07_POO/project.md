# 🚀 Module Project: RPG Adventure System

Use everything you learned about **Object-Oriented Programming (OOP)** to create a small RPG adventure system with characters, abilities, inheritance and object interactions.

⬅️ [Back to Exercises](exercises.md)

## 📜 Project

Create an **RPG Adventure System**.

Start by creating an `Enum` called `CharacterClass` with three values:

```text
WARRIOR
MAGE
ENEMY
```

Create a parent class called `Character` with the following attributes:

```text
name
character_class
health
damage
```

The class must include:

```text
__init__()          -> Initialize the character attributes
__str__()           -> Display character information
attack(enemy)       -> Attack another character
receive_damage()    -> Reduce health without going below 0
```

Add a **class attribute** called `total_characters` to count how many characters have been created.

Use a **class method** called `show_total()` to display the counter.

### Character Validation

Use a protected attribute `_health` and `@property` to control access to health.

The following rules must be respected:

```text
Starting health must be greater than 0
Damage cannot be negative
Invalid starting values raise ValueError
Health cannot go below 0
```

### Character Inheritance

Create two subclasses that inherit from `Character`.

**Warrior**

```text
Additional attribute: armor

Override receive_damage():
- Armor reduces incoming damage
- Health cannot go below 0
```

**Mage**

```text
Additional attribute: mana

cast_spell(enemy):
- Deals 35 damage
- Consumes 20 mana
- Cannot be used without enough mana
```

Both subclasses must override a method called `use_ability(enemy)`:

```text
Warrior -> Performs a normal attack
Mage    -> Casts a spell
```

### Pet System

Create a separate class called `Pet` with:

```text
name
hunger
```

Add an `eat(food)` method:

```text
If food is "meat":
    Reduce hunger by 20

Otherwise:
    Refuse the food

Hunger cannot go below 0
```

### Adventure Simulation

Create the following objects:

```text
Warrior: Thrall
Health: 120
Damage: 25
Armor: 10

Mage: Jaina
Health: 90
Damage: 15
Mana: 60

Enemy: Ogre
Health: 110
Damage: 18

Pet: Misha
Hunger: 50
```

Store the Warrior and Mage in a list called `party`.

Then simulate the following actions:

```text
1. Both party members use their abilities against the Ogre
2. The Ogre attacks the Warrior
3. Both party members use their abilities again
4. The Pet eats meat
5. Display all character information
6. Display the Mage's remaining mana
7. Display the Pet's remaining hunger
8. Display the total number of characters created
```

Use a loop to execute each party member's `use_ability()` method and demonstrate **polymorphism**.

### Example

```text
==========================
     RPG ADVENTURE
==========================

Thrall attacks Ogre for 25 damage!
Jaina casts a spell on Ogre for 35 damage!
Ogre attacks Thrall for 18 damage!
Thrall attacks Ogre for 25 damage!
Jaina casts a spell on Ogre for 35 damage!

Misha eats the meat!

=== FINAL STATUS ===

Thrall | Warrior | Health: 112
Jaina | Mage | Health: 90
Ogre | Enemy | Health: 0

Mage mana: 20
Pet hunger: 30

Characters created: 3

==========================
```

> [!NOTE]
> The Warrior's armor reduces incoming damage. In this example, the Ogre deals 18 damage, but the Warrior only loses 8 health.

## 💡 Solution

<details>
<summary>Show solution</summary>

```python
from enum import Enum

# ENUM
class CharacterClass(Enum):
    WARRIOR = "Warrior"
    MAGE = "Mage"
    ENEMY = "Enemy"

# PARENT CLASS
class Character:
    total_characters = 0

    def __init__(self, name, character_class, health, damage):
        if health <= 0:
            raise ValueError("Health must be positive.")

        if damage < 0:
            raise ValueError("Damage cannot be negative.")

        self.name = name
        self.character_class = character_class
        self._health = health
        self.damage = damage

        Character.total_characters += 1

    @property
    def health(self):
        return self._health

    @health.setter
    def health(self, value):
        self._health = max(0, value)

    def receive_damage(self, damage):
        self.health -= damage

    def attack(self, enemy):
        enemy.receive_damage(self.damage)
        print(f"{self.name} attacks {enemy.name} for {self.damage} damage!")

    def use_ability(self, enemy):
        self.attack(enemy)

    @classmethod
    def show_total(cls):
        print(f"Characters created: {cls.total_characters}")

    def __str__(self):
        return f"{self.name} | {self.character_class.value} | Health: {self.health}"

# WARRIOR
class Warrior(Character):
    def __init__(self, name, health, damage, armor):
        if armor < 0:
            raise ValueError("Armor cannot be negative.")

        super().__init__(name, CharacterClass.WARRIOR, health, damage)
        self.armor = armor

    def receive_damage(self, damage):
        real_damage = max(0, damage - self.armor)
        super().receive_damage(real_damage)

    def use_ability(self, enemy):
        self.attack(enemy)

# MAGE
class Mage(Character):
    def __init__(self, name, health, damage, mana):
        if mana < 0:
            raise ValueError("Mana cannot be negative.")

        super().__init__(name, CharacterClass.MAGE, health, damage)
        self.mana = mana

    def cast_spell(self, enemy):
        if self.mana >= 20:
            self.mana -= 20
            enemy.receive_damage(35)
            print(f"{self.name} casts a spell on {enemy.name} for 35 damage!")
        else:
            print(f"{self.name} does not have enough mana!")

    def use_ability(self, enemy):
        self.cast_spell(enemy)

# PET
class Pet:
    def __init__(self, name, hunger):
        if hunger < 0:
            raise ValueError("Hunger cannot be negative.")

        self.name = name
        self.hunger = hunger

    def eat(self, food):
        if food.lower() == "meat":
            self.hunger = max(0, self.hunger - 20)
            print(f"{self.name} eats the meat!")
        else:
            print(f"{self.name} refuses the {food}!")

# CREATE OBJECTS
warrior = Warrior("Thrall", 120, 25, 10)
mage = Mage("Jaina", 90, 15, 60)
enemy = Character("Ogre", CharacterClass.ENEMY, 110, 18)
pet = Pet("Misha", 50)

party = [warrior, mage]

# ADVENTURE
print("==========================")
print("     RPG ADVENTURE")
print("==========================")
print()

for character in party:
    character.use_ability(enemy)

enemy.attack(warrior)

for character in party:
    if enemy.health > 0:
        character.use_ability(enemy)

print()
pet.eat("meat")

# FINAL STATUS
print()
print("=== FINAL STATUS ===")
print()

for character in party:
    print(character)

print(enemy)
print()

print(f"Mage mana: {mage.mana}")
print(f"Pet hunger: {pet.hunger}")
print()

Character.show_total()

print()
print("==========================")
```

</details>

## ⚡ Work in progress...

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>