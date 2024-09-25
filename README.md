----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**PROJECT OVERVIEW:**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
This project implements fundamental search algorithms to navigate Pacman through various mazes. The objective is to create intelligent agents that can plan Pacman’s path through a maze efficiently, either to reach a goal, collect food, or explore the maze. The algorithms designed include Depth-First Search (DFS), Breadth-First Search (BFS), Uniform-Cost Search (UCS), and A Search (A)**, with additional support for solving more complex problems like the CornersProblem and FoodSearchProblem using heuristics.

These algorithms are widely used in game AI to handle pathfinding, decision-making, and planning in games with complex environments. By implementing these algorithms, we can demonstrate how search techniques work to help Pacman reach his goals, whether it’s finding the shortest path or collecting all dots.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**IMPLEMENTED ALGORITHMS**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**1. Depth First Search (DFS)**

DFS explores as deep as possible along each branch before backing up. Pacman uses DFS to explore the maze, prioritizing paths that extend further away from the start. This strategy is not optimal for finding the shortest path but works well for certain scenarios where exploration is key.
In game development, DFS can be useful for exhaustive exploration tasks, though it’s generally less effective for pathfinding in large, complex mazes as it might miss shorter paths.

**How DFS works:**

A) Starts from the root (Pacman's initial position).
B) Explores each branch to its deepest point.
C) Backtracks when no further moves are possible.
D) Uses a stack data structure to manage unvisited nodes.
   
**3. Breadth First Search (BFS)**

BFS explores the maze level by level, ensuring that Pacman finds the shortest path to the goal in terms of steps. It expands the shallowest unvisited node first, making it ideal for finding optimal solutions in unweighted graphs.
BFS is widely used for pathfinding problems in grid-based games or environments where the shortest path is desired.

**How BFS works:**

A) Explores all nodes at the present depth level before moving on to nodes at the next depth level.
B) Uses a queue to maintain the order of exploration.
C) Guarantees the shortest path in terms of the number of actions.

**4. Uniform Cost Search (UCS)**

UCS expands nodes based on the total cost from the start, ensuring that Pacman always follows the least-cost path to the goal. Unlike BFS, UCS takes path costs into account, making it optimal for finding the least-cost solution.
UCS is crucial in game development where certain paths have different costs, like terrains with varying difficulty. It ensures that Pacman finds the path with the lowest overall cost, even if it's longer.

**How UCS works:**

A) Expands the node with the lowest cumulative cost from the start.
B) Uses a priority queue where nodes are prioritized based on their cost.
C) Guarantees the optimal path in terms of the total cost.

**5.** **A*** **Search** **(A*** **)**

A* combines the advantages of UCS with a heuristic that estimates the cost to reach the goal. This results in faster and more efficient searches. Pacman uses A* to reach the goal while considering both the cost to get there and an estimate of the remainingdistance.
A* is the go-to algorithm for pathfinding in most games because it provides an optimal solution efficiently. It’s widely used in game development for navigation, enabling game characters to find optimal routes while minimizing computational overhead.

**How** **A*** **works:**

A) Expands nodes based on the sum of the cost to reach them and an estimate of the cost to reach the goal (heuristic).
B) Uses a priority queue, where nodes are prioritized by their combined cost and heuristic value.
C) Guarantees the optimal path as long as the heuristic is admissible (doesn’t overestimate the cost).

**7. Corners Problem**

In this problem, Pacman must visit all four corners of the maze. The challenge lies in optimizing the path so Pacman doesn’t revisit unnecessary areas. This is solved using BFS combined with state tracking to remember which corners Pacman has visited.
Solving this problem efficiently involves designing a search algorithm that tracks visited states, an essential technique in AI for managing complex navigation tasks.

**9. Corners Heuritstics**

This heuristic improves the Corners Problem by estimating the cost to visit all remaining corners. By using A* with this heuristic, Pacman can find a more efficient route through the corners.
Heuristics like this are widely applicable in optimizing search problems in games, reducing the number of explored nodes and thus improving performance.

**11. Food Search Problem**

The objective here is to find the optimal path for Pacman to eat all the dots on the map. This problem introduces additional complexity as Pacman must plan an efficient route to clear the board. A* is again used, this time with a heuristic that helps Pacman navigate toward the remaining dots.
This showcases how search algorithms and heuristics can be applied to more advanced problems like resource collection in games.

**13. Closest-Dot Search(Suboptimal Search)**

This is a greedy search strategy where Pacman always moves toward the closest dot, without regard for overall efficiency. While not optimal, it’s an example of a simpler, faster solution for less complex problems

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**The Role of Search Algorithms in Game Development**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In game development, search algorithms are fundamental for creating AI that can navigate dynamic environments, make decisions, and solve problems. The algorithms implemented in this project directly impact the ability of game characters like Pacman to find optimal paths, avoid ghosts, and complete objectives efficiently. 

These techniques are widely applicable across different types of games, from maze navigation to resource collection and beyond. Search algorithms provide the backbone for game AI, enabling characters to think and plan. By using BFS, DFS, UCS, and A*, we can solve problems in a variety of ways, balancing between solution optimality and computational efficiency, depending on the game's requirements.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**HOW TO TEST AND EXPERIENCE THE ALGORITHMS*
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Follow below steps:**

**A)** Install Python on your system.

**B)** Clone or download this repository to your local machine.

**C)** Navigate to the project folder in your terminal or command prompt.

**Testing Each Algorithm**

You can test and experience how Pacman navigates the mazes using different algorithms by running the following **commands**. 

Each command launches the Pacman game using a specified algorithm and environment:

**1) Depth-First Search (DFS):**

python pacman.py -l tinyMaze -p SearchAgent -a fn=dfs

python pacman.py -l mediumMaze -p SearchAgent -a fn=dfs

python pacman.py -l bigMaze -z 0.5 -p SearchAgent -a fn=dfs

**2) Breadth-First Search (BFS):**

python pacman.py -l mediumMaze -p SearchAgent -a fn=bfs

python pacman.py -l bigMaze -p SearchAgent -a fn=bfs -z 0.5

**3) Uniform-Cost Search (UCS):**

python pacman.py -l mediumMaze -p SearchAgent -a fn=ucs

python pacman.py -l mediumDottedMaze -p StayEastSearchAgent

python pacman.py -l mediumScaryMaze -p StayWestSearchAgent

**4) A Search (A):**

python pacman.py -l bigMaze -z 0.5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic

**5) Corners Problem:**

python pacman.py -l tinyCorners -p SearchAgent -a fn=bfs,prob=CornersProblem

python pacman.py -l mediumCorners -p SearchAgent -a fn=bfs,prob=CornersProblem

**6) Corners Heuristic:**

python pacman.py -l mediumCorners -p AStarCornersAgent -z 0.5

**7) Food Search Problem:**
   
python pacman.py -l trickySearch -p AStarFoodSearchAgent

**8) Closest-Dot Search (Suboptimal Search):**

python pacman.py -l bigSearch -p ClosestDotSearchAgent -z 0.5

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**CONCLUSION**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
This project demonstrates the power of search algorithms in game AI, showing how Pacman can intelligently navigate through mazes using classic AI techniques. By implementing and testing various search algorithms, you can explore how different strategies affect Pacman's performance and decision-making. Whether you’re solving simple mazes or optimizing paths through more complex environments, these algorithms form the foundation for intelligent navigation in games.
