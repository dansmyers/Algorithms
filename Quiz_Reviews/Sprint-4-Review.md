# Sprint 4 Quiz Review

## 0-1 Knapsack Revisited

Recall the 0-1 knapsack problem we introduced in class.

- You have a knapsack that can hold a total of `W` pounds.

- There are a total of `N` items that can go in the knapsack. Each item `i` has a weight given by `weight[i]` and a value
given by `value[i]`.

- There is only one of each item, so you can either choose to include item `i` or not include it: the choice is binary.

- Your goal is to find the combination of items that yields the maximum total value while still having a combined weight less than `W`.

For example, if

```
W = 12
N = 4
weight = [5, 3, 8, 4]
value = [10, 20, 50, 15]
```

The optimal choice is to take items 2 and 3 for a total value of 70 and weight of 11.

Define a solution function called `knapsack(N, W)`, where `N` is the number of items to consider and `W` is the remaining capacity
of the knapsack.

Consider the `N`th item: the last one in the set. If item `N` is included in the knapsack, the best overall solution that can be
obtained is the value of item `N` plus the optimal allocation of the remaining `N - 1` items:

```
value[N] + knapsack(N - 1, W - weight[N])
```

If item `N` is **not** included, the best possible value is the optimal allocation of the other `N - 1` items, but with the full
capacity of the knapsack available.

```
knapsack(N - 1, W)
```

Therefore, the overall best solution for `N` items is the max of the two choices: include item `N` or don't include it.

```
max{value[N] + knapsack(N - 1, W - weight[N]), knapsack(N - 1, W)}
```

**Code**. Write a recursive pseudocode solution that implements the `knapsack` function.

**Matrix**. Using the data below, fill in the 2-D solution matrix using the bottom-up strategy:

```
N = 3
W = 5
weight = [1, 3, 5]
value = [2, 5, 6]
```

```
                     W
                  
        0    1    2    3    4    5
        
     0
     
     1
N
     2
     
     3
```

## Dice

Suppose that you have `N` standard six-sided dice. How many ways are there to generate a roll that adds up to a sum of `X`?

(Note that this problem isn't asking about the **probability** of rolling `X` but the **number of outcomes** that yield `X`.)

Let `die(N, X)` represent the solution. If the first die is a 1, you would need to get a sum of `X - 1` from the other `N - 1` dice
so that the total sum is `X`. Therefore, the number of potential solutions that have a 1 in the first position is

```
die(N - 1, X - 1)
```

If the first die is 2, you would need to generate a sum of `X - 2` from the other `N - 1` dice, so the number of solutions that
have a 2 in the first position is:

```
die(N - 1, X - 2)
```

This pattern continues for each of the other possible values of the first die. The result is that:

```
die(N, X) = die(N - 1, X - 1) + die(N - 1, X - 2) + die(N - 1, X - 3) + ... + die(N - 1, X - 6)
```

Fill in the table below to find the number of ways to roll a sum of 5 on three dice.

```
                     X
                  
        0    1    2    3    4    5
        
     0
     
     1
N
     2
     
     3
```
