# EX 6C TRAVELLING SALES MAN PROBLEM

## DATE :

## AIM :

To Solve the given 2D matrix tsp[][], where each row has the array of distances from that indexed city to all the other cities and -1 denotes that there doesn’t exist a path between those two indexed cities. The task is to print minimum cost in TSP cycle.

## Algorithm :

1.Take the cost matrix that shows the cost between every pair of cities.

2.Generate all possible orders (permutations) in which the cities can be visited.

3.For each order, calculate the total travel cost, including returning to the starting city.

4.Keep track of the minimum total cost found so far.

5.After checking all possible orders, return the minimum cost as the final answer.

## Program :

### Developed by: VARSHINI S
### Register Number:  212222220056

```
def tsp_cost(tsp):
    return min(sum(tsp[i][j] for i, j in zip(path, path[1:] + path[:1])) for path in permutations(range(len(tsp))))

from itertools import permutations
tsp = [[-1, 30, 25, 10], [15, -1, 20, 40], [10, 20, -1, 25], [30, 10, 20, -1]]
print("Minimum Cost is :",tsp_cost(tsp))
```

## Output :

![image](https://github.com/user-attachments/assets/ecf9c7a0-3e7b-445b-96cd-5a069c62bebc)


## Result :

Thus the program was executed successfully for finding the minimum cost to vist all cities.
