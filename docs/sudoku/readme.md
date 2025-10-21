## Sudoku



### Generator: Mathematical approach

There are two main approaches to generate a Sudoku puzzle.
The first one is to generate a board with some random numbers and positions, then try if the Sudoku is solvable.
The second one is to have a fully solved board, then remove numbers randomly.

This generator takes the second approach, where it is still needed to generate a fully solved board.
By completely ignoring hardcoding one solved board, it is crucial to understand the mathematics of the board to be able to generate a new board.

Considering a Sudoku board as an $M*N$ board, stating that $M$ and $N$ can be greater, equal or lower than 9;
it is definet the number $k$ that defines the maximum value for the numbers to be placed in a row, column or mayor square.

$$
k = M * N
$$

Considering the grid that corresponds to the Sudoku board, each minor cell is defined by the matrix coordinates $r$ (row) and $c$ (column).

### Solver: Backtracking algorithm

The backtracking algorithm consists on making a (valid) number guess over an empty cell and sequentially continuing doing so until all cells have a number (puzzle solved) or a guess was incorrect.

This algorithm iterates over the next five steps:

1. **An empty space is found**. It does not matter if the algorithm iterates over columns and then over rows, vice versa or takes a random coordinate to find an empty space. The goal is to start with an emtpy space.
2. **A guess is made**. The guess is just any number which is not contained in the row, column or major tile. This guess is only a valid number to be positioned at the current tile, but it doesn't have to be the correct one.
3. **Continue iterating steps 1 and 2**. With this, the tree continues expanding, creating new branches every time a new guess is made in a tile where multiple valid numbers can be used as a guess.
4. **Go back** to the last created branch if the puzzle reach a tile in which no valid guesses can be done.
5. **Iterate** until a solution is found.

![2x2 Sudoku board displaying a decision tree of the previous stated algorithm](./sudoku_decision_tree.png)

These steps can lead to two possible outcomes:

- **A solution is found**. It was possible to find a solution by the backtracking algorithm. This does not mean the found solution is the only solution.
- **No solution was found**. In this case, we are positive all numbers were tried over all empty cells. The conclusion of this case is that the initial Sudoku board is not solvable.

> Note: The solver could also be used to test if any randomly generated board is also a valid Sudoku puzzle.