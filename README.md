# Puzzle Generators

> Note: The repository is a WIP. I'm currently working on the design document where I want to explain everything before coding it.

Within this document is stated the general logic to **generate and solve** some board puzzles.

Here is defined a **board puzzle** as any logic puzzle that takes place at an NxM chess board.
This board does not require to have white and black cells, but it is divided into single cells.
Depending on the puzzle, other rules might apply over the board.

The following are the puzzles (alphabetically sorted) contained within the repository:

- Nonogram [WIP]
- Numberlink [WIP]
- Queens [WIP]
- [Sudoku](./docs/sudoku/readme.md)
- Tango [WIP]

## Puzzles Descriptions

### Nonogram

A **Nonogram** is a paint-by-number type of puzzle defined over an M*N board.
Each row and column have an ordered sequence of numbers, which define how many cells must be colored within that row or column.
The separation of the numbers means that the sets of colored cells must be separated by at least one uncolored cell.

These puzzles can be colored in black and white, describing a binary image, or they can use different colors.

_Example_<br>
Considering a 10x10 board, a single column has the numbers "3 4 1".
Because the column has a maximum of 10 positions, and each set of colored cells must be separated, it is known that the solution for this row is "ccc.cccc.c" or "1110111101" where `c` or `1` correspond to the colored cell.

Let's consider now a different column within the same board with the numbers "2 5".
Without more information, this column might have multiple solutions as:

- The total number of colored cells plus an extra uncolored cell in between them does not match to 10.
- The column can start or end either with a colored or a non-colored cell.
- The set of colored cells must be separated by at least one uncolored cell. Thus, the separation by uncolored cells can be greater than 1.

![Solved Nonogram board 10 by 10 showing the draw of the outline of a heart](Nonogram.jpg)

### Numberlink (connecting pipes)

### Queens

### Sudoku

### Tango
