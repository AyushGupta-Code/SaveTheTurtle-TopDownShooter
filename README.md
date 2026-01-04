# Save the Turtle 
A fast, two-act top-down shooter built in **Godot 4.5**. Clear out AI-driven mercs, pry open a cage, grab your turtle, and then survive a brutal escort sprint to the safe zone while smarter squads close in.

## Quick Start
1) Install **Godot 4.5**.  
2) Clone this repo and open `project.godot` in Godot.  
3) Play the main scene `world_scene.tscn`. (Hit ▶️ in the editor.)

## Objective
- Stage 1: Fight FSM/BT enemies, grab the **key** dropped by the last enemy, and open the cage to rescue the turtle.  
- Stage 2: Picking up the turtle triggers a fade-to-black transition, spawns Extended BT squads around you, and reveals the **safe zone**. Dash, shoot, and deliver the turtle to extract.

## Features
- **Layered AI**: Classic FSM grunts, Behavior Tree shooters, and Extended BT squads that flank, seek cover, dodge, and coordinate via a shared squad coordinator.  
- **A\* Navigation**: NavigationAgent2D pathing with smooth steering, wander/retreat cycles, and cover seeking.  
- **Responsive Gunplay**: Rapid-fire rifle, tracers, muzzle flashes, camera shake, and a short dash with stamina bar feedback.  
- **Dynamic pacing**: Key drops from the final Stage-1 enemy, turtle pickup triggers the stage swap, and a safe zone spawns for the escort finale.  
- **Built-in analytics**: `PerformanceMetrics` logs run data (kills by AI type, damage taken, dash cadence, turtle timings, proximity risk) to `user://metrics.csv` for balancing.

## Controls
| Input | Action |
| :-- | :-- |
| **W / A / S / D** | Move |
| **Mouse** | Aim |
| **Left Click** | Shoot |
| **Dash** (Input action `Dash`, default: Shift) | Burst movement |
| **Esc** | Quit run |
| **U** | Toggle infinite health (debug/testing) |

## Project Notes
- Core gameplay lives in `world_scene.tscn` with scripts in `scripts/` (player, enemies, BT variants, squad coordination, turtle/box, safe zone).  
- Assets are in `assets/` (player/enemy sprites, crate, cage, key, turtle).  
- Metrics autoload is configured in `project.godot` as `PerformanceMetrics` so every run logs without extra setup.
