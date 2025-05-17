# EX:3C - Sudoku Solver
## DATE:

## AIM:

To write a python program to find the solution of sudoku puzzle using Backtracking.

## Algorithm

1. Traverse the board to find the first unassigned cell (i.e., cell with value 0).
2. For the empty cell, try digits from 1 to 9 and check if the digit can be placed without violating Sudoku rules.
3. Use a helper function (isPossible) to verify the digit is not already present in the current row, column, or 3×3 subgrid.
4. If the digit is valid, assign it to the cell and recursively try to solve the remaining board.
5. If placing a digit doesn’t lead to a solution, reset the cell to 0 (backtrack) and try the next digit. Once complete, print the solved board.

## Program:
```
Program to implement to to find the solution of sudoku puzzle using Backtracking

DEVELOPED BY    : NIRAUNJANA GAYATHRI G R
REGISTER NUMBER :  212222230096
```
```
board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]
def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()
def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False
    for i in range(0, 9):
        if board[i][col] == val:
            return False
    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True
def solve():
    for i in range(0,9):
        for j in range(0,9):
            if board[i][j]==0:
                for val in range(1,10):
                    if isPossible(board,i,j,val):
                        board[i][j]=val
                        solve()
                        board[i][j]=0
                return 
    printBoard(board)
solve()
```

## Output:

![image](https://github.com/user-attachments/assets/2a2f5867-34ec-497a-8303-6619dac9d674)


## Result:

The Sudoku solver program executed successfully and found the solution for the given puzzle.
