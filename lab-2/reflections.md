# Names: Paul, Jenessy
# Lab: lab1 (Intelligent Agents)
# Date: 1/19/26

1. If any of those components are missing, the search algorithm may not be able to find a solution or it may find an invalid solution.
2. It's easy to access elements. It's a little less computationally efficient, since every time the algorithm needs the row/column number of a specific element, it has to calculate them--you wouldn't need that in a 2D array. At the same time, it's easier to *find* a specific element (just use `index()`).
3. If `get_actions()` was allowed to return invalid actions, the search algorithm could move the model into an invalid state. There's no guarantee the algorithm knows how to identify or handle invalid actions.
4. For example, it checks all paths of cost 1 before checking any paths of cost 2.
5. The frontier grows quickly because it includes every possible node. BFS pays the memory cost upfront, finding the shortest solution every time but checking every possible solution that's shorter than it first. The algorithm has a high space complexity, which means it can be unsuitable as-is for larger problems.
6. The frontier grows quickly because it includes every possible node. BFS pays the memory cost upfront, finding the shortest solution every time but checking every possible solution that's shorter than it first. The naive algorithm essentially trades efficiency for correctness.
7. 
8. 
9. 
10. It always expands the node with the lowest cost, tie-breaking using the distance from the origin (farther is better). This will always result in an optimal solution since it searches the solution space in order of total cost.
11. It takes a longer route. It's both the shortest path and the one with the lowest cost, though UCS chose it for its low cost.
12. They perform identically when actions always have the same cost, like with the 8-puzzle. UCS performs better when actions have different costs, like with route-finding on a map with different-length roads.
13. It's making an educated guess, and in this case, the guess is correct. If the guess is way off, it can end up being less efficient than UCS--it may find a solution with short distance but high cost, like BFS.
14. It doesn't care about action cost, just the value of its heuristic.
15. It doesn't find solutions with low cost, just low distance. A better heuristic might be based off of Manhattan distance, but when two nodes have the same distance, taking the one with the lowest cost first.
16. It takes into account the cost to get to a node, which guarantees optimality, and it also uses a heuristic to check nodes closest to the goal when there are nodes with the same cost, which is usually a safe guess that results in shorter solutions.
17. A* was in between them, which means it performs better than UCS and worse than greedy BFS.
18. Admissible heuristics never over-estimate the cost to reach the goal. If a heuristic over-estimated the cost of the optimal solution enough that it appeared worse than a non-optimal solution, then the algorithm would find a non-optimal solution.
19. When $h(n)=0$, the A* formula is the same as UCS--only considering the cost from the start to the current node rather than also considering estimated cost from the current node to the goal. A* is the same as UCS, just that it uses a custom tiebreaker function ($h(n)$).
20. They expanded the same number of nodes. Manhattan distance is better for grid movement since it dominates the Euclidean distance heuristic while still being admissible (i.e., it more closely approximates minimum distance).
21. Providing more information means the algorithm expands more relevant nodes in general. As long as the heuristic is admissible, it won't lead the algorithm to check a possibly longer path before a possibly shorter one.
22. Tiles out of place encodes the information of how many tiles are out of place. Manhattan distance does this as well, but it additionally encodes a measure of how far the tiles are out of place. It dominates the tiles out of place heuristic.
23. If the tiles are in order except for the blank tile, the Manhattan distance and number of tiles out of place are the same. 
24. Manhattan distance dominates tiles out of place since Manhattan distance is always greater than or equal to the tiles out of place.
25. Manhattan distance doesn't take into account other tiles that have to move out of the way. A better heuristic might keep track of how much a movement to decrease a specific tile's distance might increase the distance of other tiles.
