# Sprint 1 Quiz Review

## Notations

### Big-O Definition
Use the **formal definition** of Big-O notation to argue that 

*f*(*n*) = 3*n*<sup>2</sup> + 9*n* + 5

is *O*(*n<sup>2</sup>)

### Big and Little
What is the difference between Big-O and Little-O notation? Explain why it's correct to say that 

*f*(*n*) = 3*n* + 1

is *O*(*n*), *O*(*n*<sup>2</sup>), and *o*(*n*<sup>2</sup>)

### It's Better Than Bad, It's Good!

Show that *f*(*n*) = log(*n*!) is O(*n* log *n*)

### Polynomials

Use the **formal definition** of *Θ* notation to argue that the log of a *d*-degree polynomial with positive coefficients must be
*Θ*(log *n*).

## Pseudocode Complexity

Take a look at the following pseudocode for our old friend selection sort. Use the statement counting strategy to derive the complexity
of the method.

You can assume the worst-case input, which is an array in reverse-sorted order.

```
algorithm: selection sort

input: array a
output: a, sorted in-place

for (i = 0; i < a.length - 1; i++) {

    min_index = i
    min_value = a[i]
    
    for (j = i + 1; j < a.length; i++) {
        if (a[j] < min_value) {
            min_value = a[j]
            min_index = j
        }
    }
    
    swap a[i] and a[min_index]  // swap the ith smallest element into position i
}

Tip: think about how many times the outer `for` loop must execute, then think about how many times the inner `for` loop must execute.
```

## Linked Lists

Write pseudocode implementations of the following linked list operations:

- add to head
- add to back (in a singly-linked list)
- remove from back (in a singly-linked list)
- remove the element at a given index *i*

## Trees

Write psuedocode for pre-order, in-order, post-order, and level-order traversals of a tree. Be able to perform all four kinds of
traversals on an example tree and give the output that results.

## Tortoise and Hare

Here's a classic question that sometimes shows up in programming interviews. **Do some research** to find a solution, then write
it up in pseudocode.

