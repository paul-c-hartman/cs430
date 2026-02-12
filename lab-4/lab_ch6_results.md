# Names: Paul, Jenessy
# Lab: lab3 (CSP)
# Date: Today's date

1. Each constraint applies to 9 variables, and constraints that apply to more than 2 variables can be reduced to only binary constraints. For instance, the constraint "all variables in this row must be different" is the same as a bunch of binary restraints that say "this cell must be different from that one."
  
  The total number of binary constraints is 972. Each of the initial 27 constraints is reducible to 36 binary constraints; 36 * 72 = 972.

2. A puzzle with zero solutions has constraints that can't be satisfied. A puzzle with multiple solutions has multiple configurations that satisfy its constraints. You can detect both zero- and multiple-solution puzzles by using constraint propagation, which checks that all variables have at least one valid value based on the given constraints. A puzzle with zero solutions will have at least one variable with no valid values and a puzzle with multiple solutions will have at least one variable with multiple valid values.

3. One example is if the algorithm filled up nearly all squares and the last two are incompatible due to a very early assignment being in an invalid spot. This would require backtracking nearly all the way back to the beginning.

4. You can start anywhere, so this particular ordering is potentially inefficient. This is because some variables are easier to infer than others--for instance, a square in a row that has all other squares filled in. Knowing the size of the domain of each variable allows you to choose to infer the easier variables first.

5. Sudoku has a branching factor close to 5, as mentioned in the question. This means that each additional empty cell essentially multiplies the size of the search tree by around 5. A puzzle with 50 empty cells would require close to 5^50 nodes to be explored in the worst case.

6. That means the current assignment is not a valid solution and the algorithm needs to backtrack and remove the current value from the current variable's domain. Forward checking is more efficient than the brute-force algorithm because eliminating potential branches makes the search tree smaller; you don't have to check unnecessary values.

7. Forward checking pruned 37,260 search nodes. This is 96.1% of the nodes that the brute-force algorithm checks, so the speedup is also 96.1%.

8. 

9. 

10. 

11. MRV selects the variable that is closest to being fully defined (i.e., closest to a solution), and then LCV tries values that are least restrictive for surrounding variables. Keeping neighbors open is good because it prevents over-restriction; you want to keep as many options open as possible while following constraints so you don't skip over the solution by accident.

12. Constraining more variables is good for variable selection because it reduces the number of possibilities more. It immediately makes the neighbors easier to solve, and the search space overall becomes smaller, reducing future search.

13. The search space has a lot of dead-ends clustered behind moves that look valid but aren't. So you have to utilize constraint propagation and heuristics to narrow down the possibilities you search to valid branches to be efficient.

14. The distribution of givens partly determines how big the search space is. For instance, a puzzle with 21 givens that are evenly distributed throughout the board is more difficult to apply intelligent techniques to than one where they're all clustered together, since clusters are more constrained by nature--MRV is more effective with a clustered board. A truly hard Sudoku puzzle is one with few given values that are evenly distributed (both on the board and between 1 through 9).

15. Even though there is a tradeoff between implementation complexity and computational cost, the ceiling for complexity is not high enough for a Sudoku solver specifically that it causes any issues. The reduced computational cost and increased solving power is staggeringly more impactful than the increased implementation complexity.

16. With CSPs, you can reach an invalid state due to a decision you made many decisions ago. Local decision-making never backtracks, since the decisions it makes always keep or decrease the heuristic (in this case, the number of conflicts). Backtracking would require it to make a suboptimal decision, so it gets stuck in a certain area of the search space. The backtracking approach can go back multiple decisions to try a different area of the search space.

17. Part of what makes N-queens amenable to local search is how much each decision constrains other variables. In Sudoku, a full solution often has 40 or 60 decisions, while a 9-queens problem (with the same size board) only has 9. Problems like N-queens do not have local optima that are not global optima so a local-search approach won't get stuck, as opposed to Sudoku which has so many constraints that it will get stuck, requiring a backtracking approach.