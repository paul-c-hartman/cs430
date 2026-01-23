# Names: Paul, Jenessy
# Lab: lab1 (Intelligent Agents)
# Date: 1/19/26

1. If any of those components are missing, the search algorithm may not be able to find a solution or it may find an invalid solution.
2. It's easy to access elements. It's a little less computationally efficient, since every time the algorithm needs the row/column number of a specific element, it has to calculate them--you wouldn't need that in a 2D array. At the same time, it's easier to *find* a specific element (just use `index()`).
3. If `get_actions()` was allowed to return invalid actions, the search algorithm could move the model into an invalid state. There's no guarantee the algorithm knows how to identify or handle invalid actions.
4. For example, it checks all paths of cost 1 before checking any paths of cost 2.
5. The frontier grows quickly because it includes every possible node. BFS pays the memory cost upfront, finding the shortest solution every time but checking every possible solution that's shorter than it first. The algorithm has a high space complexity, which means it can be unsuitable as-is for larger problems.
6. The frontier grows quickly because it includes every possible node. BFS pays the memory cost upfront, finding the shortest solution every time but checking every possible solution that's shorter than it first. The naive algorithm essentially trades efficiency for correctness.