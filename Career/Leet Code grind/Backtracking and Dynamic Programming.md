## Backtracking
recursive backtracking is a algorithmic technique used to solving problems incrementally by exploring all possible paths, and reverting back if a path leads to a dead end. It is used for solving problems that satisfy some constraints such as N-Queens, Soduku solvers, subset generation etc

#### How Backtracking Works

Backtracking involves recursion with state tracking. At each step, the algorithm explores a decision, recurses into the next level, and undoes the decision if it doesn’t lead to a valid solution. This approach ensures that all potential configurations are explored without redundancy.

#### Use Cases

- **N-Queens:** Placing queens on a board so no two attack each other
- **Sudoku Solver:** Filling a grid according to constraints
- **Combinations/Subsets:** Generating all valid sets or permutations
- **Pathfinding:** Exploring all possible routes in a maze

#### Performance Consideration

Backtracking has exponential time complexity in the worst case, but pruning techniques such as early stopping and memoization can significantly improve its efficiency.

## Dynamic Programming
Backtracking solutions that have overlapping subproblems can benefit from "memoization", i.e. adding a cache to reuse solutions of subproblems which is nothing but top-down DP

https://leetcode.com/studyplan/dynamic-programming/
