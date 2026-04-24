# 🚨 Disaster Evacuation Planner (Missionaries & Cannibals Variant)

## 📌 Problem Description

The **Disaster Evacuation Planner** is a logical puzzle inspired by the classic *Missionaries and Cannibals problem*.

In this scenario:

* There are **3 Civilians** and **3 Responders** on the *Danger Zone (left side)*.
* The goal is to safely move everyone to the *Safe Zone (right side)* using a boat.
* The boat can carry **a maximum of 2 people at a time**.

### ⚠️ Constraints:

* At no point should **Civilians outnumber Responders** on either side (if Responders are present).
* If this rule is violated, the mission fails.

---

## 🧠 Algorithms Used

### 1. **State Representation**

Each state is represented as:
(Civilians_Left, Responders_Left, Boat_Position)

Example:
(3, 3, Left)

---

### 2. **State Transition Logic**

Valid moves:

* (1 Civilian)
* (2 Civilians)
* (1 Responder)
* (2 Responders)
* (1 Civilian + 1 Responder)

Each move updates the state depending on the boat position.

---

### 3. **Constraint Checking**

A function ensures:

* Civilians ≤ Responders (on both sides, if responders exist)

---

### 4. **Search Strategy (Conceptual)**

Although the current implementation is interactive, the problem can be solved using:

* **Breadth-First Search (BFS)** → guarantees shortest solution
* **Depth-First Search (DFS)** → explores deeper states first

---

## ⚙️ Execution Steps

### 🖥️ Running the Program

1. Copy the provided code into a file named:

   ```
   index.html
   ```
2. Open the file in any browser (Chrome, Edge, Firefox).

---

### 🎮 How to Play

1. Click buttons to move people:

   * 1 Civilian
   * 2 Civilians
   * 1 Responder
   * 2 Responders
   * 1 Civilian + 1 Responder

2. The boat switches sides automatically after each move.

3. Follow the rules:

   * Do not leave Civilians outnumbering Responders.

4. Reach the goal:

   * Move all individuals to the Safe Zone.

---

## 📊 Sample Outputs

### ✅ Successful Execution

```
Initial State:
Left: Civilians=3, Responders=3
Right: Civilians=0, Responders=0

Moves:
1. 1 Civilian + 1 Responder → Right
2. 1 Civilian → Left
3. 2 Responders → Right
4. 1 Responder → Left
5. 2 Civilians → Right
6. 1 Civilian + 1 Responder → Left
7. 2 Civilians → Right
8. 1 Responder → Left
9. 2 Responders → Right

Final State:
Left: Civilians=0, Responders=0
Right: Civilians=3, Responders=3

Result: ✅ All Evacuated Successfully
```

---

### ❌ Failure Case

```
Move leads to:
Left: Civilians=3, Responders=1

Condition Violated:
Civilians > Responders

Result: ❌ Mission Failed
```

---

## 💡 Future Enhancements

* Implement **BFS auto-solver**
* Add **visual animations for boat movement**
* Deploy using **GitHub Pages**
* Add **difficulty levels (more people, bigger boat)**

---

## 🏁 Conclusion

This project demonstrates:

* Problem-solving using constraints
* State-space representation
* Foundations of AI search algorithms (BFS/DFS)

It is a great beginner-friendly project for students learning **Data Structures, Algorithms, and Artificial Intelligence concepts**.
https://naxix6677.github.io/AI_problemSolving_-RA2411026050295-RA2411026050278/problem2-disaster-evacuation/index2.html
