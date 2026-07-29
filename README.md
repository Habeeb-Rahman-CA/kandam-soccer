# 5v5 Soccer Game - Godot 4

<img width="2723" height="2342" alt="Untitled-2026-04-18-1845" src="https://github.com/user-attachments/assets/0944f789-ed21-4113-b10b-e2241dbfac91" />

A fast-paced, 5v5 retro-style local multiplayer soccer game built with **Godot 4.6 (GL Compatibility)**. The game supports single-player vs CPU, local 1v1 PvP, and local cooperative modes. It features a robust state-machine-driven architecture for gameplay rules, player behaviors, and ball physics.

---

## 🎮 Game Controls

The game supports local multiplayer with two distinct keyboard layout control schemes:

### Player 1 (Keyboard 1)
| Action | Key |
| :--- | :--- |
| **Move Up** | `W` |
| **Move Down** | `S` |
| **Move Left** | `A` |
| **Move Right** | `D` |
| **Pass / Tackle** | `F` |
| **Shoot / Power-Up** | `Spacebar` |

### Player 2 (Keyboard 2)
| Action | Key |
| :--- | :--- |
| **Move Up** | `↑` (Up Arrow) |
| **Move Down** | `↓` (Down Arrow) |
| **Move Left** | `←` (Left Arrow) |
| **Move Right** | `→` (Right Arrow) |
| **Pass / Tackle** | `K` |
| **Shoot / Power-Up** | `L` |

---

## 🚀 Key Features

* **Finite State Machine (FSM) Architecture**: 
  * **Player States**: Moving, Tackling, Recovering, Prepping Shot, Shooting, Passing, Header, Volley Kick, Bicycle Kick, Chest Control, Hurt, Diving, Celebrating, Mourning, and Reseting.
  * **Ball States**: Carried, Freeform, and Shot.
  * **Game States**: Reset, Kickoff, In Play, Scored, Overtime, and Game Over.
* **Custom AI Behaviors**: Fully automated CPU behaviors for field players (`ai_behavior_field.gd`) and goalies (`ai_behavior_goalie.gd`) using steering behaviors and context-based decision trees.
* **Data-Driven Rosters**: Squad configurations are loaded dynamically via JSON (`squads.json`). Players have individual, customizable attributes including:
  * Full name
  * Role (Goalie, Defence, Midfield, Offence)
  * Skin Color (Light, Medium, Dark)
  * Speed & Shot Power
* **Dynamic Team Customization**: Custom shaders dynamically adjust player sprites to show correct skin color tones and team-colored jerseys based on the selected club.
* **Local Coop & PvP modes**: Supports standard single-player vs CPU match, local co-op, or head-to-head 1v1 competitive play.

---

## ⚽ Clubs & Squads

A variety of prestigious football clubs and custom squads are fully configured and playable:
* 🇪🇸 **Real Madrid**
* 🇪🇸 **Barcelona**
* 🇫🇷 **PSG**
* 🇩🇪 **Bayern Munich**
* 🏴󠁧󠁢󠁥󠁮󠁧󠁿 **Man City**
* 🏴󠁧󠁢󠁥󠁮󠁧󠁿 **Man United**
* 🏴󠁧󠁢󠁥󠁮󠁧󠁿 **Liverpool**
* 🇮🇹 **AC Milan**
* 🇮🇹 **Inter Milan**
* 🇮🇳 **Edathodika FC**

---

## 🛠️ Project Structure

```text
├── assets/
│   ├── art/            # Character sprites, control markers, and stadium assets
│   └── json/
│       └── squads.json # Dynamic team/player database
├── resources/
│   └── player_resource.gd  # Custom Godot Resource template for player rosters
├── scenes/
│   ├── ball/           # Ball scene, state factory, and ball state nodes
│   ├── characters/     # Player scene, state factory, player state nodes, and AI behaviors
│   ├── game_manager/   # Game referee/manager, timers, and match state nodes
│   ├── goal/           # Goalposts and score collision zones
│   └── world.tscn      # Primary match/stadium gameplay scene
└── utils/
    ├── data_loader.gd  # JSON squad parser utility
    └── key_utils.gd    # Dynamic keyboard input layout mapper
```

---

## ⚙️ How to Run & Play

1. **Download Godot**: Ensure you have **Godot 4.6** or later installed.
2. **Import Project**: Open the Godot Project Manager, click **Import**, and navigate to the project directory containing `project.godot`.
3. **Run Game**: Press `F5` or click the **Play** button in the upper-right corner of the editor.
