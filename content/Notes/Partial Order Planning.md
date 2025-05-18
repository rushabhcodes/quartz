---
created: 2025-05-19T01:04
updated: 2025-05-19T01:16
---
**Partial-Order Planning (POP)** is a type of planning where the order of actions is only partially specified. This means that the planner allows some actions to remain unordered if there is no reason to enforce a specific order, offering flexibility and efficiency in planning.

#### Key Concepts:

1. **Actions**: Basic steps with preconditions and effects.
    
2. **Ordering Constraints**: Define which action must occur before another (e.g., A < B).
    
3. **Causal Links**: Indicate that one action provides a condition required by another.
    
4. **Open Preconditions**: Preconditions of actions that still need to be satisfied.
    
5. **Dummy Actions**:
    
    - **Start**: Represents the initial state.
        
    - **Finish**: Represents the goal state.
        

#### Example of POP:

**Goal**: Wear both shoes.

- `Goal: RightShoeOn ∧ LeftShoeOn`
    

**Actions**:

- `Action(RightSock, Effect: RightSockOn`
    
- `Action(RightShoe, Precondition: RightSockOn, Effect: RightShoeOn)`
    
- `Action(LeftSock, Effect: LeftSockOn)`
    
- `Action(LeftShoe Precondition: LeftSockOn, Effect: LeftShoeOn)`


#### Plan Setup:

- **Initial Actions**: `{Start, Finish}`
    
- **Initial Open Preconditions**: `{RightShoeOn, LeftShoeOn}`
    
- The planner must find a consistent way to fulfill these using available actions while adding ordering constraints and causal links as needed.
    

A possible **linearization** (totally ordered plan):

1. Start
    
2. RightSock
    
3. RightShoe
    
4. LeftSock
    
5. LeftShoe
    
6. Finish
    

But in **partial-order**, the socks can be worn in any order as long as each is worn before its respective shoe. This reduces constraints and increases flexibility.

A **consistent POP plan**:

- No cycles in ordering
    
- No conflicts in causal links
    
- All preconditions are satisfied

![[Partial Order Planning.excalidraw.svg]]