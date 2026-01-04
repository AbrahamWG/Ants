# Ants vs. SomeBees 🐜🐝

A Python-based tower defense game inspired by *Plants vs. Zombies*, demonstrating advanced object-oriented programming concepts through strategic gameplay.

![Game Demo](ants_vs_somebees_demo.gif)

## 🎮 Game Overview

In Ants vs. SomeBees, players strategically deploy different ant types to defend their colony from waves of invading bees. Each ant type has unique abilities and costs, requiring careful resource management and tactical positioning to succeed.

## 🚀 How to Play

### Running the Game
```bash
python3 gui.py
```

The game will be available at `http://127.0.0.1:31415/`

### Game Options
- **Different Difficulty Levels**: `-d [test/easy/normal/hard/extra-hard]`
- **Water Layout**: `--water` or `-w` (adds water terrain)
- **Custom Food**: `--food [amount]` (set starting food)

Example:
```bash
python3 gui.py -d hard --water
```

## 🐜 Ant Types

| Ant Type | Cost | Health | Ability |
|----------|------|--------|---------|
| **Harvester** | 2 | 1 | Generates 1 food per turn |
| **Thrower** | 3 | 1 | Throws leaves at nearest bee |
| **Short** | 2 | 1 | Attacks bees 0-3 places away |
| **Long** | 2 | 1 | Attacks bees 5+ places away |
| **Wall** | 4 | 4 | High health defensive barrier |
| **Fire** | 5 | 3 | Deals reflective damage when hurt |
| **Hungry** | 4 | 1 | Eats one bee, then chews for 3 turns |
| **Scuba** | 6 | 1 | Waterproof thrower for water places |
| **Protector** | 4 | 2 | Contains another ant, taking damage first |
| **Tank** | 6 | 2 | Container that also damages all nearby bees |
| **Queen** | 7 | 1 | Doubles damage of ants behind her (game over if she dies) |

## 💻 Technical Implementation

### Object-Oriented Design Patterns

**Inheritance Hierarchy**
- Base `Insect` class with `Ant` and `Bee` subclasses
- 10+ specialized ant types inheriting from `Ant` or intermediate classes
- Demonstrates proper use of inheritance and method overriding

**Polymorphism**
- All insects share common interface (`action`, `reduce_health`)
- Each ant type implements unique behavior through method overriding
- Enables consistent game loop regardless of insect type

**Composition Over Inheritance**
- `ContainerAnt` pattern allows ant stacking
- Flexible design: any ant can be protected by container ants
- Demonstrates delegation and object composition

**Key Features**
- Type hints throughout for better code clarity
- Encapsulation of game state and logic
- Clean separation of concerns (game logic, UI, configuration)

### Core Classes

- **`GameState`**: Manages colony state, food, time, and game flow
- **`Place`**: Represents locations in tunnels with entrance/exit chain
- **`Insect`**: Base class for all game entities
- **`Ant`**: Player-controlled units with unique abilities
- **`Bee`**: Enemy units that advance through tunnels
- **`Water`**: Special terrain requiring waterproof units

## 🛠️ Technology Stack

- **Python 3**: Core game logic
- **Flask**: Web server for GUI
- **SocketIO**: Real-time communication
- **HTML/CSS/JavaScript**: Interactive game interface

## 📁 Project Structure

```
ants/
├── ants.py              # Main game logic (primary implementation file)
├── ants_plans.py        # Difficulty level configurations
├── gui.py               # Flask-based web interface
├── ucb.py               # Utility functions
├── static/              # Game assets (images, sounds, CSS, JS)
├── templates/           # HTML templates
└── libs/                # Dependencies (Flask, SocketIO, etc.)
```

## 🎓 Learning Outcomes

This project demonstrates proficiency in:
- **Object-Oriented Programming**: Classes, inheritance, polymorphism, encapsulation
- **Software Design Patterns**: Container pattern, strategy pattern
- **Python**: Type hints, list comprehensions, class/instance attributes
- **Problem Solving**: Complex game logic, state management
- **Code Organization**: Clean, maintainable, well-documented code

## 🏆 Project Completion

This project was completed as part of UC Berkeley's **CS 61A: Structure and Interpretation of Computer Programs**.

**Implemented Features:**
- ✅ Phase 1: Basic gameplay (HarvesterAnt, ThrowerAnt)
- ✅ Phase 2: Extended ant types (8 new ant types)
- ✅ Phase 3: Water terrain and QueenAnt mechanics

## 📝 Credits

- **Course**: UC Berkeley CS 61A
- **Original Project**: Tom Magrino, Eric Tzeng, and John DeNero
- **Artwork**: Alana Tran, Andrew Huang, Emilee Chen, Jessie Salas, Jingyi Li, Katherine Xu, Meena Vempaty, Michelle Chang, and Ryan Davis
- **Implementation**: Abraham Guan

## 📄 License

This project was completed as coursework. Please refer to UC Berkeley's academic integrity policies.


