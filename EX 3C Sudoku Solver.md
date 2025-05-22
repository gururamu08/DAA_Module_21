# EX 3C Sudoku Solver
## DATE:16/5/25
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1. The board is a 9×9 grid with some empty spots (marked as 0).

2.The goal is to fill the grid with numbers 1–9 so that:

3.Each row, column, and 3×3 box has all numbers 1–9 without repeating.

4.The isPossible() function checks if a number can go in a certain spot.

5.The solve() function tries numbers in empty spots using trial and error (backtracking).

6.When the board is filled correctly, it prints the complete solution.

  

## Program:
```
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: GURUMOORTHI R
Register Number: 212222230042
```
```python
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
    #####################  Add your code here #########################
solve()
```

## Output:

![image](https://github.com/user-attachments/assets/2a7ca3d1-abae-4f50-a81b-a7d7fffa5daf)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
