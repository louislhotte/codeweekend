# In It To Win IT - Code Weekend #1

Welcome to the GitHub repository for Team "In It To Win IT"! This document outlines the basic rules and setup for our participation in Code Weekend #1.

## Team Members
- **louislhotte**
- **romainlhotte**

## Contest Overview
The contest begins on **June 7th at 21:00 UTC** and ends on **June 9th at 21:00 UTC**.

## Timeline
- **June 7th at 21:00 UTC:** Contest starts.
- **June 8th at 21:00 UTC:** New version of the statement is released with additional tests.
- **June 9th at 21:00 UTC:** Contest ends.

## Game Description
- **World:** The game world is a grid of size `width x height`.
- **Hero Attributes:** You control a hero with the following attributes:
  - **Coordinates:** `(xh, yh)`
  - **Base Speed:** `base_speed`
  - **Base Power:** `base_power`
  - **Base Range:** `base_range`
- **Monsters:** The world contains monsters with attributes:
  - **Coordinates:** `(xm, ym)`
  - **Health Points:** `hp`
  - **Gold:** `gold`
  - **Experience Points:** `exp`

### Hero Actions
- **Move:** The hero can move to any `(xt, yt)` within their speed range.
- **Attack:** The hero can attack a monster within their attack range. If the monster's HP drops to 0 or below, it dies, and the hero gains gold and experience points.

### Hero Attributes and Leveling
- The hero gains experience points by defeating monsters.
- Leveling up increases the hero's speed, power, and range.
- The hero starts at level 0 and needs 1000 experience points to reach level 1. Subsequent levels require more experience points.

### Level Experience Requirements
- Level 1: 1000 experience points
- Level 2: 1100 additional experience points
- Level 3: 1300 additional experience points
- Level 4: 1600 additional experience points
- Level 5: 2000 additional experience points
- For level L, the additional experience points required are `1000 + L * (L - 1) * 50`.

### Objective
- The main goal is to collect as much gold as possible within the given number of turns.

## Submission Guidelines
- **Format:** Submissions are JSON files containing the hero's moves and actions.
- **Moves:** Each move can be either a move to new coordinates or an attack on a monster.
- **Example JSON Output:**
  ```json
  {
      "moves": [
          {
              "type": "move",
              "target_x": <X>,
              "target_y": <Y>
          },
          {
              "type": "attack",
              "target_id": <0-based monster index>
          }
      ]
  }
