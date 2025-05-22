# EX 3A Knight Tour & Count Path
## DATE:16/5/25
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
1.Define the Knight’s Moves: The knight moves in 8 possible directions (L-shaped moves).

2.Use BFS (Breadth-First Search): A queue is used to explore each possible move level by level, tracking the number of steps.

3.Track Visited Cells: A 2D array marks which cells the knight has already visited to avoid repeating paths.

4.Check Valid Moves: Only move to cells that are inside the board and haven’t been visited.

5.Stop at Target: When the knight reaches the target position, return the number of steps taken.



## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: GURUMOORTHI R
Register Number: 212222230042
```
```python
class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,
                         targetpos, N):
    dx = [2, 2, -2, -2, 1, 1, -1, -1]
    dy = [1, -1, 1, -1, 2, -2, 2, -2]
     
    queue = []
    queue.append(cell(knightpos[0], knightpos[1], 0))
    visited = [[False for i in range(N + 1)]
                      for j in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True
    while(len(queue) > 0):
         
        t = queue[0]
        queue.pop(0)
        if(t.x == targetpos[0] and
           t.y == targetpos[1]):
            return t.dist
             
        # iterate for all reachable states
        for i in range(8):
             
            x = t.x + dx[i]
            y = t.y + dy[i]
             
            if(isInside(x, y, N) and not visited[x][y]):
                visited[x][y] = True
                queue.append(cell(x, y, t.dist + 1))  
    # add your code here
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
```

## Output:

![image](https://github.com/user-attachments/assets/1b9133b0-ca5d-49b4-a8e2-da255e2e14a3)


## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
