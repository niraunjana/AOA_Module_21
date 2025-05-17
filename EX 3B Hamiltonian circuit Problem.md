# EX:3B - Hamiltonian Circuit Problem
## DATE:

## AIM:

To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm

1. Create a path array of size N (number of vertices), initialized with -1, and set the starting vertex (e.g., 0).
2. Define a recursive function to attempt placing each unvisited vertex at the next position in the path.
3. Only consider vertices adjacent to the current vertex and not already in the path.
4. If no further vertex leads to a solution, backtrack by resetting the position and trying the next candidate.
5. If all N vertices are included in the path successfully, return True; else, return False.

## Program:
```
Program to implement to check whether Hamiltonian path exits in the given graph

DEVELOPED BY    : NIRAUNJANA GAYATHRI G R
REGISTER NUMBER : 212222230096
```
```
def Hamiltonian_path(adj, N):
    def is_hamiltonian_path(path, pos):
        if pos == N:
            return True
        for v in range(N):
            if adj[path[pos - 1]][v] == 1 and v not in path:
                path[pos] = v
                
                if is_hamiltonian_path(path, pos + 1):
                    return True
                path[pos] = -1
        return False
    path = [-1] * N
    path[0] = 0
    if not is_hamiltonian_path(path, 1):
        return False
    return True
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

![image](https://github.com/user-attachments/assets/db54eb21-7c79-408b-a810-5ad0a28cbcfd)


## Result:

The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
