# EX 6B KNAPSACK PROBLEM

## DATE :

## AIM :

To create a python program using dynamic programming for 0/1 knapsack problem..

## Algorithm :

1.If there are no items or capacity is 0.

2.Return 0 (no value can be added).

3.Check the weight of the current item:

4.If it's more than the remaining capacity, skip it and move to the next item.

5.If the item can fit:

6.Include it: Add its value and reduce the weight from total capacity.

7.Exclude it: Move to the next item without including it.

8.Return the maximum of the two choices (include or exclude).

## Program :

### Developed by: VARSHINI S
### Register Number:  212222220056

```
def knapSack(W, wt, val, n):
  
    if n==0 or W==0:
        return 0
    if(wt[n-1]>W):
        return knapSack(W,wt,val,n-1)
    else:
        return max(val[n-1] + knapSack(W-wt[n-1],wt,val,n-1) , knapSack(W,wt,val,n-1))
    

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```

## Output :

![image](https://github.com/user-attachments/assets/00f1b996-a7b1-4680-9a0d-fd565215da71)


## Result :

Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
