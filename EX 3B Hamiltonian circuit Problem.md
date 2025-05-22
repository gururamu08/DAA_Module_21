# EX 3B Hamiltonian Circuit Problem
## DATE:16/5/25
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1.What is a Hamiltonian Path?
A path in a graph that visits every vertex exactly once without repeating.

2.Backtracking is Used
The algorithm tries each possible path recursively and backtracks if a dead-end is reached.

3.Path Array Keeps Track
An array (path[]) keeps track of the order of visited vertices.

4.Check Connections
At each step, it checks if there's an edge from the current vertex to the next possible one.

5.Success or Failure
If a valid path covering all vertices is found, it prints "YES"; otherwise, "NO".

  

## Program:
```
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
def Hamiltonian_path(adj, N):
    def k(path,pos):
        if pos==N:
            return True
        for v in range(N):
            if adj[path[pos-1]][v]==1 and v not in path:
                path[pos]=v
                if k(path,pos+1):
                    return True
                path[pos]=0
        return False        
    path=[-1]*N
    path[0]=0
    if not k(path,1):
        return False
    return True    
    ######################### Add your Code here ##########################
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```

## Output:


![image](https://github.com/user-attachments/assets/129dcef1-930c-44e1-b36c-efe95eb74ca6)

## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
