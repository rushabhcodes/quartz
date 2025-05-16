The **task environment** is everything an agent interacts with while performing a task. To design effective intelligent agents, it's essential to understand the **nature of the environment** in which they operate.

The properties of task environments are classified along **several dimensions**:

### 1. **Observable: Fully vs. Partially Observable**

- **Fully Observable**: The agent's sensors give access to the **complete state** of the environment.
    - **Example**: Chess – all pieces on the board are visible to both players.

- **Partially Observable**: The agent has **incomplete or noisy** sensory input.
    - **Example**: Driving a car – you cannot see around corners or the internal state of other drivers.    
---
### 2. **Agents: Single Agent vs. Multi-Agent**

- **Single Agent**: Only **one agent** is acting in the environment.
    - **Example**: Solitaire game or cleaning robot.
    
- **Multi-Agent**: Multiple agents interact; can be **competitive** or **cooperative**.
    - **Example**: Football (players), Self-driving cars on the road (partially cooperative), Chess (competitive).
---
### 3. **Deterministic vs. Stochastic**

- **Deterministic**: The **next state** is completely determined by the current state and the agent’s action.
    - **Example**: Crossword puzzle – filling a word always leads to the same result.

- **Stochastic**: There is **some randomness** involved in state transitions.
    - **Example**: Dice games, robot navigation on slippery floors.
---
### 4. **Episodic vs. Sequential**

- **Episodic**: Each episode (action + perception) is **independent** of the previous ones.
    - **Example**: Image classification – each image is processed independently.

- **Sequential**: The current decision **affects future decisions**.    
    - **Example**: Chess or driving – early moves impact the outcome.
---
### 5. **Static vs. Dynamic**
- **Static**: The environment **does not change** while the agent is thinking.
    - **Example**: Crossword puzzles.

- **Dynamic**: The environment **can change** during decision-making.   
    - **Example**: Driving a car – traffic changes constantly.
---
### 6. **Discrete vs. Continuous**
- **Discrete**: A finite number of distinct states and actions.
    - **Example**: Chess or board games – limited moves and positions.

- **Continuous**: Infinite states and actions possible.
    - **Example**: Robotic arm movement, self-driving cars (speed, angle).        
---

### 7. **Known vs. Unknown**
- **Known**: The agent **knows the rules and outcomes** of its actions.
    - **Example**: Board games with defined rules.

- **Unknown**: The agent must **learn or explore** the rules through experience.    
    - **Example**: New video game or unknown terrain for a robot.
---
### 📝 Summary Table

| **Property**      | **Types**                  | **Example**                    |
| ----------------- | -------------------------- | ------------------------------ |
| **Observability** | Fully / Partially          | Chess / Driving                |
| **Agents**        | Single / Multi-agent       | Vacuum cleaner / Football      |
| **Determinism**   | Deterministic / Stochastic | Puzzle / Dice game             |
| **Episodes**      | Episodic / Sequential      | Image classifier / Chess       |
| **Change**        | Static / Dynamic           | Crossword / Self-driving car   |
| **State**         | Discrete / Continuous      | Tic-tac-toe / Autonomous drone |
| **Knowledge**     | Known / Unknown            | Chess / Maze exploration       |
