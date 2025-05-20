---
created: 2025-05-20T21:56
updated: 2025-05-20T22:29
---
In Artificial Intelligence, **agent types** are classified based on how they perceive their environment and make decisions. The five main types of agents are:

---

## ✅ Types of Agents in AI

1. **Simple Reflex Agent**
    
2. **Model-Based Reflex Agent**
    
3. **Goal-Based Agent**
    
4. **Utility-Based Agent**
    
5. **Learning Agent**
    

---

### 1. 🧠 **Simple Reflex Agent**

#### ➤ **Explanation**

- Acts only on the **current percept**.
    
- Ignores the history of percepts.
    
- Uses **condition–action rules** ("if condition then action").
    
- Suitable only for fully observable environments.
    

#### **Block Diagram**:

![[Simple Reflex Agent.excalidraw.svg]]

---

### 2. 🧠 **Model-Based Reflex Agent**

#### ➤ **Explanation**

- Maintains an **internal state** based on the **history of percepts**.
    
- Uses a model of the world to handle **partially observable environments**.
    

#### **Block Diagram**:

![[Model Based Reflex Agent.excalidraw.svg]]

---

### 3. 🎯 **Goal-Based Agent**

#### ➤ **Explanation**

- Chooses actions by considering **future consequences** and **goals**.
    
- Uses **search and planning** to achieve the desired goal.
    
- More flexible than reflex agents.
    

#### **Block Diagram**:

![[Goal Based Agent.excalidraw.svg]]

---

### 4. 📈 **Utility-Based Agent**

#### ➤ **Explanation**

- Chooses the **best** action among multiple alternatives.
    
- Uses a **utility function** to measure **happiness/satisfaction**.
    
- Balances conflicting goals and handles trade-offs.
    

#### **Block Diagram**:

![[Utility based Agent.excalidraw.svg]]

---

### 5. 📚 **Learning Agent**

#### ➤ **Explanation**

- Can **learn from experience** and improve performance over time.
    
- Consists of a **learning element**, a **performance element**, a **critic**, and a **problem generator**.
    

#### **Block Diagram**:

![[Learning Agent.excalidraw.svg]]

---

## 📌 Summary Table

|Agent Type|Memory|Uses Goals|Utility|Learning|
|---|---|---|---|---|
|Simple Reflex|❌|❌|❌|❌|
|Model-Based Reflex|✅|❌|❌|❌|
|Goal-Based|✅|✅|❌|❌|
|Utility-Based|✅|✅|✅|❌|
|Learning Agent|✅|✅|✅|✅|
