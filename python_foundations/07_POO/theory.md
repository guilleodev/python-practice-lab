# 🧩 Python Object-Oriented Programming - Theory

Learn how to organize Python programs using classes, objects, attributes, methods and inheritance.

Object-Oriented Programming (OOP) allows us to create reusable structures that combine data and behavior.

## 📚 Contents

1. [Understanding OOP](#1-understanding-oop)
2. [Classes, Attributes and Constructors](#2-classes-attributes-and-constructors)
3. [Instance Methods and Object Interaction](#3-instance-methods-and-object-interaction)
4. [Class Attributes and Methods](#4-class-attributes-and-methods)
5. [Encapsulation](#5-encapsulation)
6. [Validation and Exceptions](#6-validation-and-exceptions)
7. [Inheritance](#7-inheritance)
8. [Method Overriding and Polymorphism](#8-method-overriding-and-polymorphism)
9. [Enumerations](#9-enumerations)
10. [Combining OOP Concepts](#10-combining-oop-concepts)
11. [Cheat Sheet](#cheat-sheet)

## 1. Understanding OOP

**Object-Oriented Programming (OOP)** is a programming approach that organizes code around objects.

An object combines two main elements:

- **Attributes:** Data that describes the object.
- **Methods:** Actions that the object can perform.

A **class** is a blueprint used to create objects. An **object** is an instance of that class.

For example, a game character can have attributes such as its name, health and level, and methods such as attacking or healing.

```python
class Character:
    pass

player1 = Character()
player2 = Character()

print(type(player1))
```

Both `player1` and `player2` are independent objects created from the same class.

## 2. Classes, Attributes and Constructors

A class is defined using the `class` keyword.

The `__init__()` method is the constructor initializer. It runs automatically when a new object is created.

The `self` parameter refers to the current instance and allows us to access its attributes and methods.

```python
class Character:
    def __init__(self, name, health, level):
        self.name = name
        self.health = health
        self.level = level

player1 = Character("Arthas", 100, 20)
player2 = Character("Jaina", 80, 30)

print(player1.name)
print(player2.level)
```

Each object stores its own attributes.

We can access or modify them using dot notation:

```python
player1.health = 75

print(player1.health)
```

### The `__str__()` method

The special method `__str__()` defines how an object is represented when printed.

```python
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def __str__(self):
        return f"{self.name} - {self.health} HP"

player = Character("Thrall", 100)

print(player)
```

Output:

```text
Thrall - 100 HP
```

Without `__str__()`, printing an object normally displays a representation containing its class and memory address.

## 3. Instance Methods and Object Interaction

An **instance method** is a function defined inside a class that operates on an object.

Instance methods receive `self` automatically when called through an instance.

### Methods with parameters

Methods can receive additional parameters to perform actions.

```python
class Pet:
    def __init__(self, name):
        self.name = name

    def eat(self, food):
        if food.lower() == "fish":
            print(f"{self.name} eats the fish.")
        else:
            print(f"{self.name} refuses the {food}.")

pet = Pet("Misha")

pet.eat("Fish")
pet.eat("Bread")
```

When we call `pet.eat("Fish")`:

- `self` refers to the object `pet`.
- `food` receives the string `"Fish"`.
- The method uses both values to perform its action.

We do not pass `self` manually when calling an instance method.

### Object interaction

A method can also receive **another object as a parameter**.

This allows different objects to interact with each other.

```python
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def attack(self, enemy, damage):
        enemy.health = max(0, enemy.health - damage)
        print(f"{self.name} attacks {enemy.name}!")

warrior = Character("Thrall", 100)
mage = Character("Jaina", 80)

warrior.attack(mage, 25)

print(mage.health)
```

Output:

```text
Thrall attacks Jaina!
55
```

Here, `enemy` represents the actual `mage` object.

The method modifies the health of that object directly.

This is an important concept in OOP: **objects can collaborate and change each other's state through methods**.

## 4. Class Attributes and Methods

Not every attribute belongs to an individual object.

Python distinguishes between instance attributes and class attributes.

### Class attributes

**Class attributes** belong to the class and can be shared by all its instances.

```python
class Character:
    total_characters = 0

    def __init__(self, name):
        self.name = name
        Character.total_characters += 1

player1 = Character("Jaina")
player2 = Character("Thrall")
player3 = Character("Arthas")

print(Character.total_characters)
```

Output:

```text
3
```

`name` is an instance attribute because each character has a different name.

`total_characters` is a class attribute because it tracks information shared by the class.

### Class methods

A **class method** operates on the class rather than on a particular instance.

It uses `@classmethod` and receives `cls` instead of `self`.

```python
class Character:
    total_characters = 0

    def __init__(self, name):
        self.name = name
        type(self).total_characters += 1

    @classmethod
    def show_total(cls):
        print(f"Total characters: {cls.total_characters}")

player1 = Character("Jaina")
player2 = Character("Thrall")

Character.show_total()
```

Output:

```text
Total characters: 2
```

`cls` refers to the class, while `self` refers to an instance.

Class methods are useful for accessing class-level information and creating alternative constructors.

### Static methods

A **static method** belongs to a class but does not automatically receive `self` or `cls`.

It is useful for functions logically related to the class that do not need access to its state.

```python
class Character:
    @staticmethod
    def calculate_damage(base_damage, multiplier):
        return base_damage * multiplier

damage = Character.calculate_damage(20, 3)

print(damage)
```

Output:

```text
60
```

Remember:

- **Instance method:** Uses `self`.
- **Class method:** Uses `cls`.
- **Static method:** Receives neither automatically.

## 5. Encapsulation

**Encapsulation** is the practice of controlling how an object's internal data is accessed or modified.

In Python, attribute naming conventions help communicate intended access.

### Public, protected and private attributes

```python
class Character:
    def __init__(self, name, health, gold):
        self.name = name
        self._health = health
        self.__gold = gold
```

- `name`: Public attribute.
- `_health`: Intended for internal or subclass use by convention.
- `__gold`: Uses name mangling to make accidental direct access more difficult.

Python does not enforce strict private access in the same way as some other languages.

### Properties with `@property`

A property allows us to read an internal attribute through a controlled interface.

A setter controls how its value can be changed.

```python
class Character:
    def __init__(self, name, health):
        self.name = name
        self._health = health

    @property
    def health(self):
        return self._health

    @health.setter
    def health(self, value):
        if value < 0:
            raise ValueError("Health cannot be negative.")

        self._health = value

player = Character("Jaina", 100)

print(player.health)

player.health = 80

print(player.health)
```

Although we use `player.health` like a normal attribute, Python executes the getter or setter behind the scenes.

This allows us to validate changes without requiring users of the class to call a separate method.

## 6. Validation and Exceptions

Validation ensures that an object receives acceptable values.

For example, a character should not have negative health, and a bank account should not allow negative deposits.

### Raising a ValueError

The `raise` keyword allows us to raise an exception when invalid data is provided.

```python
class Character:
    def __init__(self, name, level):
        if level < 1:
            raise ValueError("Level must be at least 1.")

        self.name = name
        self.level = level

player = Character("Thrall", 10)
```

If we attempt to create a character with level `-5`, Python raises a `ValueError`.

### Handling exceptions with try/except

We can use `try` and `except` to handle errors without immediately terminating the program.

```python
class Character:
    def __init__(self, name, level):
        if level < 1:
            raise ValueError("Level must be at least 1.")

        self.name = name
        self.level = level

try:
    player = Character("Thrall", -5)
    print(player.name)

except ValueError as error:
    print(f"Error: {error}")
```

Output:

```text
Error: Level must be at least 1.
```

### Else and finally

- `try`: Contains code that might raise an exception.
- `except`: Handles a matching exception.
- `else`: Runs if no exception occurs.
- `finally`: Runs whether an exception occurs or not.

```python
try:
    level = int(input("Character level: "))

    if level < 1:
        raise ValueError("Invalid level.")

except ValueError as error:
    print(f"Error: {error}")

else:
    print(f"Character level: {level}")

finally:
    print("Validation finished.")
```

A good practice is to catch specific exceptions rather than using a general `except` for everything.

## 7. Inheritance

**Inheritance** allows a class to reuse attributes and methods from another class.

The original class is called the **parent class** or **base class**.

The new class is called the **child class** or **subclass**.

```python
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def show_info(self):
        print(f"{self.name}: {self.health} HP")


class Warrior(Character):
    def __init__(self, name, health, armor):
        super().__init__(name, health)
        self.armor = armor

warrior = Warrior("Thrall", 100, 20)

warrior.show_info()
print(warrior.armor)
```

`Warrior` inherits from `Character`.

The `super().__init__()` call executes the parent's constructor, so we do not need to repeat the initialization of `name` and `health`.

The child class can also add its own attributes or methods.

### Multiple subclasses

One parent class can have several child classes.

```python
class Character:
    def __init__(self, name):
        self.name = name


class Warrior(Character):
    def use_ability(self):
        print(f"{self.name} uses Shield Bash!")


class Mage(Character):
    def use_ability(self):
        print(f"{self.name} casts Fireball!")

warrior = Warrior("Thrall")
mage = Mage("Jaina")

warrior.use_ability()
mage.use_ability()
```

Both objects inherit the `name` attribute but have different abilities.

## 8. Method Overriding and Polymorphism

### Method overriding

**Method overriding** occurs when a subclass provides its own version of a method defined in the parent class.

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

warrior = Warrior("Thrall", 100, 10)

warrior.receive_damage(30)

print(warrior.health)
```

Output:

```text
80
```

The warrior takes only 20 damage because its armor reduces the original attack.

The subclass overrides `receive_damage()`, then reuses the parent implementation with `super()`.

### Polymorphism

**Polymorphism** allows different objects to respond to the same method call with different behaviors.

```python
class Character:
    def __init__(self, name):
        self.name = name

    def attack(self):
        print(f"{self.name} performs a basic attack.")


class Warrior(Character):
    def attack(self):
        print(f"{self.name} attacks with a sword!")


class Mage(Character):
    def attack(self):
        print(f"{self.name} casts a fireball!")


characters = [
    Warrior("Thrall"),
    Mage("Jaina"),
    Character("Anduin")
]

for character in characters:
    character.attack()
```

Output:

```text
Thrall attacks with a sword!
Jaina casts a fireball!
Anduin performs a basic attack.
```

The same method, `attack()`, produces different results depending on the object's class.

This makes it possible to work with different objects through a common interface.

## 9. Enumerations

An **Enum** represents a fixed collection of named values.

Enums are useful when an attribute should only accept specific options, such as character classes, difficulty levels or item rarity.

Python provides `Enum` through the `enum` module.

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
        return f"{self.name} - {self.character_class.value}"


player = Character("Valeera", CharacterClass.ROGUE)

print(player)
```

Output:

```text
Valeera - Rogue
```

We access an enum member using:

```python
print(CharacterClass.MAGE)
print(CharacterClass.MAGE.name)
print(CharacterClass.MAGE.value)
```

Output:

```text
CharacterClass.MAGE
MAGE
Mage
```

Enums make code easier to read and reduce the need for repeated string values.

## 10. Combining OOP Concepts

The following example combines several concepts from this module into a small character system.

We will use classes, constructors, instance methods, class attributes, object interaction, encapsulation, validation, inheritance and method overriding.

```python
from enum import Enum

# ENUM
class CharacterClass(Enum):
    WARRIOR = "Warrior"
    MAGE = "Mage"

# PARENT CLASS
class Character:
    total_characters = 0

    def __init__(self, name, character_class, health):
        if health <= 0:
            raise ValueError("Health must be positive.")

        self.name = name
        self.character_class = character_class
        self._health = health

        Character.total_characters += 1

    @property
    def health(self):
        return self._health

    @health.setter
    def health(self, value):
        self._health = max(0, value)

    def receive_damage(self, damage):
        self.health -= damage

    def attack(self, enemy, damage):
        enemy.receive_damage(damage)
        print(f"{self.name} attacks {enemy.name}!")

    @classmethod
    def show_total(cls):
        print(f"Characters created: {cls.total_characters}")

    def __str__(self):
        return (
            f"{self.name} | {self.character_class.value} "
            f"| Health: {self.health}"
        )

# CHILD CLASS
class Warrior(Character):
    def __init__(self, name, health, armor):
        super().__init__(name, CharacterClass.WARRIOR, health)
        self.armor = armor

    def receive_damage(self, damage):
        real_damage = max(0, damage - self.armor)
        super().receive_damage(real_damage)

# CHILD CLASS
class Mage(Character):
    def __init__(self, name, health, mana):
        super().__init__(name, CharacterClass.MAGE, health)
        self.mana = mana

    def cast_spell(self, enemy):
        if self.mana >= 20:
            self.mana -= 20
            self.attack(enemy, 35)
        else:
            print("Not enough mana!")

# CREATE OBJECTS
warrior = Warrior("Thrall", 100, 10)
mage = Mage("Jaina", 80, 60)

# OBJECT INTERACTION
warrior.attack(mage, 20)
mage.cast_spell(warrior)

# DISPLAY RESULTS
print(warrior)
print(mage)

Character.show_total()
```

In this example:

- `Character` defines the shared structure.
- `Warrior` and `Mage` inherit from `Character`.
- `attack()` receives another object as a parameter.
- `receive_damage()` is overridden by `Warrior`.
- `@property` controls access to health.
- `ValueError` prevents invalid starting health.
- `Enum` defines the available character classes.
- `total_characters` and `show_total()` track class-level information.

This demonstrates how OOP concepts work together to create reusable and organized programs.

## 📌 Cheat Sheet

```python
# CLASS AND CONSTRUCTOR
class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

player = Character("Jaina", 100)

# INSTANCE ATTRIBUTES
print(player.name)
player.health = 80

# INSTANCE METHOD WITH PARAMETER
def eat(self, food):
    print(f"Eating {food}")

# OBJECT INTERACTION
def attack(self, enemy, damage):
    enemy.health = max(0, enemy.health - damage)

# __STR__
def __str__(self):
    return f"{self.name}: {self.health} HP"

# CLASS ATTRIBUTE
class Player:
    total_players = 0

# CLASS METHOD
class Player:
    total_players = 0

    @classmethod
    def show_total(cls):
        return cls.total_players

# STATIC METHOD
class Calculator:
    @staticmethod
    def double(number):
        return number * 2

# ENCAPSULATION
class Player:
    def __init__(self, health):
        self._health = health

    @property
    def health(self):
        return self._health

    @health.setter
    def health(self, value):
        if value < 0:
            raise ValueError("Invalid health.")
        self._health = value

# VALIDATION
if level < 1:
    raise ValueError("Invalid level.")

# TRY / EXCEPT
try:
    level = int("invalid")
except ValueError as error:
    print(error)

# INHERITANCE
class Character:
    def __init__(self, name):
        self.name = name

class Warrior(Character):
    def __init__(self, name, armor):
        super().__init__(name)
        self.armor = armor

# METHOD OVERRIDING
class Character:
    def attack(self):
        print("Basic attack")

class Mage(Character):
    def attack(self):
        print("Fireball")

# POLYMORPHISM
characters = [Character(), Mage()]

for character in characters:
    character.attack()

# ENUM
from enum import Enum

class CharacterClass(Enum):
    WARRIOR = "Warrior"
    MAGE = "Mage"

player_class = CharacterClass.MAGE
print(player_class.value)
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