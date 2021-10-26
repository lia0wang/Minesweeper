# Minesweeper
## How to play Minesweeper
minesweeper.c is an implementation of the classic game Minesweeper. The objective of the game is to clear a board that contains hidden "mines" or bombs without detonating any of them. To do this, you will need to use the clues on the board, which indicate how many bombs are in the adjacent cells.

At any point, you can perform 2 actions:
  - Marking a cell - marking or flagging a cell that you think might be a bomb,
  - Revealing a cell - revealing the cell. If it is an empty cell, then all of the surrounding empty cells will also be revealed. Revealing a cell containing a bomb is game over.

Once you have revealed all cells that do not contain a bomb, you win the game.

## Test
    gcc -o minesweeper minesweeper.c
    echo -e "20\n2\n0\nname\n-1" > input
    cat input | ./minesweeper | tee c.out
    cat grid.s minesweeper.s > game.s
    cat input | spim -f game.s | tee mips.out
    diff c.out mips.out