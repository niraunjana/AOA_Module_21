# EX:3A - Knight Tour & Count Path
## DATE:

## AIM:

To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm

1. Store all 8 possible moves a knight can make using dx[] and dy[] arrays.
2. Use a queue to perform Breadth-First Search starting from the knight’s initial position, with step distance 0.
3. Create a 2D boolean array visited[][] to ensure each cell is only processed once.
4. For each valid move within bounds and not yet visited, mark as visited, add to the queue with distance incremented.
5. If the current cell matches the target position, return the distance as the minimum steps needed.

## Program:
```
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight

DEVELOPED BY    : NIRAUNJANA GAYATHRI G R
REGISTER NUMBER : 212222230096
```
```
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
    dx = [-2, -1, 1, 2, -2, -1, 1, 2]
    dy = [-1, -2, -2, -1, 1, 2, 2, 1]

    queue = []
    queue.append(cell(knightpos[0], knightpos[1], 0))
    visited = [[False for _ in range(N + 1)] for _ in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True
    while len(queue) > 0:
        curr = queue.pop(0)

        if curr.x == targetpos[0] and curr.y == targetpos[1]:
            return curr.dist

        for i in range(8):
            x = curr.x + dx[i]
            y = curr.y + dy[i]

            if isInside(x, y, N) and not visited[x][y]:
                visited[x][y] = True
                queue.append(cell(x, y, curr.dist + 1))

    return float('inf')
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
```

## Output:

![image](https://github.com/user-attachments/assets/8a79d404-db2c-4f1c-b1d1-f4890be51173)


## Result:

The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
