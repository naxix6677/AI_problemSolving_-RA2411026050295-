# Disaster Evacuation Planner

## 1. Problem Description

Natural and man-made disasters such as floods, earthquakes, wildfires, and industrial accidents require quick and efficient evacuation planning to minimize loss of life. The **Disaster Evacuation Planner** is designed to compute optimal evacuation routes for people in affected areas, ensuring:

* Fastest and safest paths to designated shelters
* Avoidance of hazardous or blocked routes
* Efficient distribution of evacuees across multiple shelters
* Real-time adaptability to changing conditions

The system models the affected region as a graph where:

* Nodes represent locations (homes, intersections, shelters)
* Edges represent roads with associated travel times and risk levels

The goal is to guide evacuees from their current location to the nearest safe shelter using optimal routing strategies.

---

## 2. Algorithms Used

The planner uses a combination of graph and pathfinding algorithms:

### a. Dijkstra’s Algorithm

* Used to compute the shortest (fastest) path from a source node to all other nodes.
* Assumes non-negative edge weights (travel time or cost).
* Ideal for static or moderately changing environments.

### b. A* (A-Star) Algorithm

* An extension of Dijkstra’s algorithm using heuristics.
* Faster in practice for large maps by prioritizing likely optimal paths.
* Heuristic used: Euclidean or Manhattan distance to the nearest shelter.

### c. Breadth-First Search (BFS)

* Used in simple scenarios where all edges have equal weight.
* Helps in quick reachability checks.

### d. Multi-Source Shortest Path

* Used when multiple shelters are available.
* Computes nearest shelter for each evacuee efficiently.

### e. Risk-Aware Routing (Optional Enhancement)

* Edge weights incorporate both distance and risk factor:

  ```
  cost = distance + (risk_factor × weight)
  ```
* Helps avoid dangerous areas even if the route is shorter.

---

## 3. Execution Steps

Follow these steps to run the Disaster Evacuation Planner:

### Step 1: Input Preparation

* Define the map as a graph:

  * Nodes (locations)
  * Edges (roads with distance and risk values)
* Specify:

  * Source location(s)
  * Shelter location(s)

### Step 2: Graph Construction

* Load or create adjacency list/matrix representation
* Assign weights (distance, time, or risk-adjusted cost)

### Step 3: Algorithm Selection

* Use:

  * **Dijkstra** for general shortest path
  * **A*** for faster performance with heuristic guidance

### Step 4: Path Computation

* Run the selected algorithm
* Compute optimal route from source to nearest shelter

### Step 5: Output Generation

* Display:

  * Shortest path
  * Total cost (time/distance)
  * Selected shelter
* Optionally visualize the route on a map

### Step 6: Dynamic Updates (Optional)

* Update graph in case of:

  * Blocked roads
  * Increased risk levels
* Recompute routes in real time

---

## 4. Sample Input

```
Nodes: A, B, C, D, E (Shelter), F (Shelter)

Edges:
A-B (2)
A-C (5)
B-C (1)
B-D (4)
C-D (2)
D-E (3)
C-F (6)

Source: A
Shelters: E, F
```

---

## 5. Sample Output

### Using Dijkstra’s Algorithm

```
Shortest Path from A to nearest shelter:

Path: A → B → C → D → E
Total Cost: 8

Alternative Path:
A → C → F
Total Cost: 11

Selected Shelter: E
```

---

### With Risk Factor Consideration

```
Adjusted Path (avoiding high-risk roads):

Path: A → B → D → E
Total Cost: 9 (lower risk)

Selected Shelter: E
```

---

## 6. Features

* Multiple evacuation routes
* Real-time adaptability
* Risk-aware decision making
* Scalable to large geographic areas

---

## 7. Future Enhancements

* Integration with live traffic and weather APIs
* Mobile app for real-time guidance
* AI-based crowd prediction and load balancing
* GIS-based visualization

---

## 8. Conclusion

The Disaster Evacuation Planner provides an efficient and scalable solution for emergency evacuation scenarios. By leveraging graph algorithms and intelligent routing strategies, it ensures safer and faster evacuation, potentially saving lives during critical situations.

