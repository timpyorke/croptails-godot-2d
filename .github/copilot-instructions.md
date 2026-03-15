# Project Guidelines

## Code Style
Use GDScript conventions. Reference key files that exemplify patterns, such as [scenes/charecters/player/player.gd](scenes/charecters/player/player.gd) for player implementation and [scripts/state_machine/node_state_machine.gd](scripts/state_machine/node_state_machine.gd) for the state machine pattern.

## Architecture
The project uses a reusable State Machine pattern for character behaviors. Major components include Player (CharacterBody2D), StateMachine (Node), and States (NodeState subclasses). Service boundaries: Input handled by GameInputEvents singleton, data types in globals. The "why" behind structural decisions: Clean separation of concerns, reusability for NPCs and other characters.

## Build and Test
Open the project in the Godot editor. Run test scenes like [scenes/test/test_scence_player.tscn](scenes/test/test_scence_player.tscn) with F5. Export the project via Project > Export.

## Conventions
Patterns that differ from common practices: Use enum for tools in DataTypes to gate state transitions. Signal-based transitions between states, no hard references. Directional animations stored on the player node. Non-looping states auto-recover to Idle when animation finishes. Folder structure: scenes/, scripts/, assets/.

Potential pitfalls: Avoid typos like "charecters" (should be "characters"). Ensure animations are named correctly (e.g., no "tailingg_front"). Plant states are in enum but not implemented yet. No main scene defined; use test scenes for now.