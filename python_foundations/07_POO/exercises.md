# 🧩 Python Object-Oriented Programming - Exercises

Practice creating classes, working with objects, managing attributes and methods, and applying inheritance, encapsulation and polymorphism.

These exercises are ordered by difficulty and cover the concepts introduced in [Theory](theory.md).

## 📚 Contents

1. [Character Creation](#exercise-01)
2. [Character Information](#exercise-02)
3. [Hungry Pet](#exercise-03)
4. [Character Combat](#exercise-04)
5. [Character Counter](#exercise-05)
6. [Character Roles](#exercise-06)
7. [Protected Health](#exercise-07)
8. [Warrior Inheritance](#exercise-08)
9. [Special Abilities](#exercise-09)
10. [Battle Party](#exercise-10)

**Difficulty:** ⚔️ Easy · ⚔️⚔️ Medium · ⚔️⚔️⚔️ Hard

### [01] Exercise: Character Creation · ⚔️ Easy

<a id="exercise-01"></a>

```text
Create a Character class with:
- name
- health
- level

Use __init__ to initialize the attributes.

Create two different characters and display their attributes.
```

<details>
<summary>💡 Show solution</summary>

```python
class Character:
    def __init__(self, name, health, level):
        self.name = name
        self.health = health
        self.level = level


player1 = Character("Jaina", 100, 30)
player2 = Character("Thrall", 120, 25)

print(player1.name, player1.health, player1.level)
print(player2.name, player2.health, player2.level)
```

</details>

<a id="exercise-02"></a>

### [02] Exercise: Character Information · ⚔️ Easy

```text
Create a Character class with name, class_name and health.

Implement __str__ to display the character's information.

Create a character and display it using print().
```

<details>
<summary>💡 Show solution</summary>

```python
class Character:
    def __init__(self, name, class_name, health):
        self.name = name
        self.class_name = class_name
        self.health = health

    def __str__(self):
        return f"{self.name} | {self.class_name} | {self.health} HP"


player = Character("Valeera", "Rogue", 90)

print(player)
```

</details>

<a id="exercise-03"></a>

### [03] Exercise: Hungry Pet · ⚔️ Easy

```text
Create a Pet class with a name and a hunger attribute.

Add an eat(food) method:
- If the food is "meat", reduce hunger by 20.
- Otherwise, the pet refuses the food.
- Hunger cannot go below 0.

Test the method with different foods.
```

<details>
<summary>💡 Show solution</summary>

```python
class Pet:
    def __init__(self, name, hunger):
        self.name = name
        self.hunger = hunger

    def eat(self, food):
        if food.lower() == "meat":
            self.hunger = max(0, self.hunger - 20)
            print(f"{self.name} eats the meat!")
        else:
            print(f"{self.name} refuses the {food}.")


pet = Pet("Misha", 50)

pet.eat("Meat")
pet.eat("Bread")

print(f"Hunger: {pet.hunger}")
```

</details>

<a id="exercise-04"></a>

### [04] Exercise: Character Combat · ⚔️⚔️ Medium

```text
Create a Character class with name and health.

Add an attack(enemy, damage) method that:
- Receives another Character object.
- Reduces the enemy's health.
- Prevents health from becoming negative.

Create two characters and make them attack each other.
```

<details>
<summary>💡 Show solution</summary>

```python
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def attack(self, enemy, damage):
        enemy.health = max(0, enemy.health - damage)
        print(f"{self.name} attacks {enemy.name} for {damage} damage!")


warrior = Character("Thrall", 100)
mage = Character("Jaina", 80)

warrior.attack(mage, 30)
mage.attack(warrior, 20)

print(f"{warrior.name}: {warrior.health} HP")
print(f"{mage.name}: {mage.health} HP")
```

</details>

<a id="exercise-05"></a>

### [05] Exercise: Character Counter · ⚔️⚔️ Medium

```text
Create a Character class with:
- A class attribute total_characters starting at 0.
- An instance attribute name.

Every time a character is created, increase the counter.

Add:
- A class method show_total().
- A static method is_valid_level(level) that returns True if level >= 1.

Create three characters and test both methods.
```

<details>
<summary>💡 Show solution</summary>

```python
class Character:
    total_characters = 0

    def __init__(self, name):
        self.name = name
        Character.total_characters += 1

    @classmethod
    def show_total(cls):
        print(f"Total characters: {cls.total_characters}")

    @staticmethod
    def is_valid_level(level):
        return level >= 1


player1 = Character("Jaina")
player2 = Character("Thrall")
player3 = Character("Valeera")

Character.show_total()

print(Character.is_valid_level(10))
print(Character.is_valid_level(-5))
```

</details>

<a id="exercise-06"></a>

### [06] Exercise: Character Roles · ⚔️⚔️ Medium

```text
Create a CharacterClass Enum with:
- WARRIOR
- MAGE
- ROGUE

Create a Character class with name and character_class.

Use __str__ to display the character's name and class value.

Create one character of each class.
```

<details>
<summary>💡 Show solution</summary>

```python
from enum import Enum

class CharacterClass(Enum):
    WARRIOR = "Warrior"
    MAGE = "Mage"
    ROGUE = "Rogue"


class Character:
    def __init__(self, name, character_class):
        self.name = name
        self.character_class = character_class

    def __str__(self):
        return f"{self.name} | {self.character_class.value}"


players = [
    Character("Thrall", CharacterClass.WARRIOR),
    Character("Jaina", CharacterClass.MAGE),
    Character("Valeera", CharacterClass.ROGUE)
]

for player in players:
    print(player)
```

</details>

<a id="exercise-07"></a>

### [07] Exercise: Protected Health · ⚔️⚔️ Medium

```text
Create a Character class with:
- name
- a private __health attribute

Use @property to read health.

Use a setter to update health:
- Raise ValueError if health is negative.

Create a character and test valid and invalid values.

Handle the error using try/except.
```

<details>
<summary>💡 Show solution</summary>

```python
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    @property
    def health(self):
        return self.__health

    @health.setter
    def health(self, value):
        if value < 0:
            raise ValueError("Health cannot be negative.")

        self.__health = value


player = Character("Jaina", 100)

print(player.health)

player.health = 75

print(player.health)

try:
    player.health = -20

except ValueError as error:
    print(f"Error: {error}")
```

</details>

<a id="exercise-08"></a>

### [08] Exercise: Warrior Inheritance · ⚔️⚔️ Medium

```text
Create a Character class with name and health.

Add a receive_damage(damage) method.

Create a Warrior subclass with an additional armor attribute.

Override receive_damage():
- Armor reduces incoming damage.
- Damage cannot be negative.
- Health cannot go below 0.

Use super() to reuse the parent method.
```

<details>
<summary>💡 Show solution</summary>

```python
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def receive_damage(self, damage):
        self.health = max(0, self.health - damage)


class Warrior(Character):
    def __init__(self, name, health, armor):
        super().__init__(name, health)
        self.armor = armor

    def receive_damage(self, damage):
        real_damage = max(0, damage - self.armor)
        super().receive_damage(real_damage)


warrior = Warrior("Thrall", 100, 15)

warrior.receive_damage(40)

print(warrior.health)
```

</details>

<a id="exercise-09"></a>

### [09] Exercise: Special Abilities · ⚔️⚔️⚔️ Hard

```text
Create a Character parent class with name.

Add a use_ability() method.

Create three subclasses:
- Warrior: "Shield Bash"
- Mage: "Fireball"
- Rogue: "Backstab"

Override use_ability() in each subclass.

Store different characters in a list and execute
their abilities using a single loop.
```

<details>
<summary>💡 Show solution</summary>

```python
class Character:
    def __init__(self, name):
        self.name = name

    def use_ability(self):
        print(f"{self.name} uses a basic ability.")


class Warrior(Character):
    def use_ability(self):
        print(f"{self.name} uses Shield Bash!")


class Mage(Character):
    def use_ability(self):
        print(f"{self.name} casts Fireball!")


class Rogue(Character):
    def use_ability(self):
        print(f"{self.name} uses Backstab!")


party = [
    Warrior("Thrall"),
    Mage("Jaina"),
    Rogue("Valeera")
]

for character in party:
    character.use_ability()
```

</details>

<a id="exercise-10"></a>

### [10] Exercise: Battle Party · ⚔️⚔️⚔️ Hard

```text
Create a small party system using OOP.

Requirements:
- A Character class with name, health and damage.
- A class attribute that counts created characters.
- A receive_damage() method.
- An attack(enemy) method that affects another object.
- A Warrior subclass with armor.
- A Mage subclass with a spell_attack(enemy) method
  that deals double its normal damage.

Create a Warrior and a Mage.

Make them attack each other and display:
- Their remaining health.
- The total number of created characters.
```

<details>
<summary>💡 Show solution</summary>

```python
class Character:
    total_characters = 0

    def __init__(self, name, health, damage):
        self.name = name
        self.health = health
        self.damage = damage

        Character.total_characters += 1

    def receive_damage(self, damage):
        self.health = max(0, self.health - damage)

    def attack(self, enemy):
        enemy.receive_damage(self.damage)
        print(f"{self.name} attacks {enemy.name}!")

    def __str__(self):
        return f"{self.name}: {self.health} HP"

    @classmethod
    def show_total(cls):
        print(f"Total characters: {cls.total_characters}")


class Warrior(Character):
    def __init__(self, name, health, damage, armor):
        super().__init__(name, health, damage)
        self.armor = armor

    def receive_damage(self, damage):
        real_damage = max(0, damage - self.armor)
        super().receive_damage(real_damage)


class Mage(Character):
    def spell_attack(self, enemy):
        enemy.receive_damage(self.damage * 2)
        print(f"{self.name} casts a powerful spell on {enemy.name}!")


warrior = Warrior("Thrall", 120, 25, 10)
mage = Mage("Jaina", 80, 20)

warrior.attack(mage)
mage.spell_attack(warrior)

print(warrior)
print(mage)

Character.show_total()
```

</details>

## 🚀 Next Step

You have practiced creating objects, defining methods, controlling attributes, applying inheritance and using polymorphism.

Now it's time to combine these concepts in a larger practical challenge.

➡️ [Continue with the Module project](project.md)

<div align="center">
  <i>Made by</i>
  <br>
  <a href="https://github.com/guilleodev">
    <img src="https://raw.githubusercontent.com/guilleodev/guilleodev/main/guilleODEVWhite-transparent.png" alt="guilleODEV" width="125">
  </a>
</div>