---
created: 2025-05-20T21:53
updated: 2025-05-20T21:53
---
### ✅ Problem Formulation in AI

**Problem formulation** is the process of defining a search problem in terms of:

1. **Initial State** – The starting point.
    
2. **Goal Test** – The condition that defines a successful outcome.
    
3. **Successor Function** – All possible actions and resulting states.
    
4. **Cost Function** – The cost associated with each step or path.
    

Below are the formulations for the given problems:

---

### i. 🚕 Autonomous Taxi Driver

- **Initial State:** Taxi is at a certain location, passenger(s) at pickup location(s), destination(s) known.
    
- **Goal Test:** All passengers are dropped off at their respective destinations.
    
- **Successor Function:** Move to adjacent location, pick up a passenger, drop off a passenger.
    
- **Cost Function:** Distance travelled (e.g., number of blocks), fuel consumption, or time taken.
    

---

### ii. 🕳️ Wumpus World Problem

- **Initial State:** Agent in the start square (usually [1,1]), with no knowledge of Wumpus/pit locations.
    
- **Goal Test:** Agent has found the gold and returned safely to the start square.
    
- **Successor Function:** Move forward, turn left/right, grab gold, shoot arrow, climb out.
    
- **Cost Function:** Each action has a cost (e.g., -1 per move, -10 for using arrow, +1000 for gold), minimizing danger and maximizing score.
    

---

### iii. 🐒 Monkey and Bananas Problem

- **Initial State:** Monkey at location A, crates at different locations, bananas hanging from the ceiling.
    
- **Goal Test:** Monkey has bananas in hand.
    
- **Successor Function:** Move monkey, move crates, stack crates, climb crate, grab bananas.
    
- **Cost Function:** Number of actions or time steps taken to obtain bananas.
    

---

### iv. 🔢 8-Puzzle Problem

- **Initial State:** Any random configuration of 8 numbered tiles and 1 blank on a 3x3 grid.
    
- **Goal Test:** Tiles arranged in order:
    
    ```
    1 2 3  
    4 5 6  
    7 8 _
    ```
    
- **Successor Function:** Move the blank tile (up, down, left, right) to swap with adjacent tile.
    
- **Cost Function:** Each move costs 1; total path cost is the number of moves.
    

---

These formulations are designed to be precise and implementable for designing intelligent agents or search algorithms.