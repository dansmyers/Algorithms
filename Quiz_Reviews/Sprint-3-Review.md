# Sprint 3 Quiz Review

## Hash Tables

### Probing

Consider a hash table with 10 bukkits and a linear probing strategy. Draw the table that results after successively inserting the following keys:

11  2  45  17  31  9  15


### Double-Hashing

How does the double-hashing strategy work? What is its advantage over basic linear probing?

### O(1)

Summarize, in your own words, an argument for why the average lookup time in a chained hash table with moderate load is O(1).


## Search Trees

### BST Operations

Construct a binary search tree by successively inserting the following values:

20  15  35  18  12  19  28  32  24  45

then show the tree that results after deleting 35.


### I Suppose I Have to Ask One Question About Tries

Make an argument, in your own words, that the **average** time required to successfully look up a word in a trie is 

*O*(the average length of all words stored in the trie)


### Old School

Here's a classic interview question: write a method called `isSearchTree` that takes a binary tree as input and returns `true` if it's a
binary search tree and `false` otherwise.

Tip: you might be tempted to do this with a simple recursive solution:

```
isSearchTree(Tree t) {

    // Base case
    if (t is a single leaf node) {
        return true
    }

    // If the children don't obey the BST property, return false
    if (t.left.value > t.value || t.right.value < t.value) {
        return false
    }
    
    // Recursively check the left and right subtrees
    // Returns true only if both subtrees return true
    return isSearchTree(t.left) && isSearchTree(t.right)
}
```

This can fail, though, because it doesn't check that the BST property holds across more than one level. The following tree would be validated by the recursive method but isn't a binary search tree.

```
                100
                 |
            -----------
            |         |
           50        200
           |
        --------
        |      |
       10     1000
```

Find a method that works. This is a standard problem, so you may want to do some research.

Tip<sup>2</sup>: one strategy might be to enumerate the nodes using an in-order traversal and verify that they're in sorted order.


