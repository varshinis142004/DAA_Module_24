# EX 6A CHERRY PICK UP PROBLEM

## DATE :

## AIM :

To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm :

1.Initialize the DP table:Create a 2D dp array of size n x n (where n is the size of the grid) to store the maximum cherries that can be collected starting from each cell.

2.Iterate from the bottom-right corner:Start iterating the grid from the bottom-right corner (grid[n-1][n-1]) to the top-left corner (grid[0][0]) in reverse order.

3.Base case:The value at the bottom-right corner (dp[n-1][n-1]) is simply the value in the grid[n-1][n-1], as that's where the collection ends.

4.For the last row and last column:For the last row, move from right to left. Each cell collects cherries from the current grid cell and the cell to the right.

5.For the last column, move from bottom to top. Each cell collects cherries from the current grid cell and the cell below.

6.For all other cells:For each cell (i, j), the number of cherries is the current grid value plus the maximum of the possible moves (either move right or move down).

7.The top-left corner dp[0][0] will store the maximum number of cherries that can be collected.

8.Return the result, but add 1 (since the problem specifies counting the starting position's cherries too).  


## Program :

### Developed by: VARSHINI S
### Register Number: 212222220056

```
class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        
        dp = [[0]*n for _ in range(n)]
        for i in range(n-1,-1,-1):
            for j in range(n-1,-1,-1):
                if i == n-1 and j==n-1:
                    dp[i][j] = grid[i][j]
                elif i ==n-1:
                    dp[i][j] = grid[i][j]+dp[i][j+1]
                elif j == n-1:
                    dp[i][j] = grid[i][j] + dp[i+1][j]
                else:
                    dp[i][j] = grid[i][j] + max(dp[i][j+1],dp[i+1][j])
                    
        return max(0,dp[0][0])+1            
        
        
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```

## Output :

![image](https://github.com/user-attachments/assets/50dbfee4-579f-4805-8139-363652d02efd)


## Result :

Thus the above program was executed successfully for finding the maximum number of cherries from grid.
