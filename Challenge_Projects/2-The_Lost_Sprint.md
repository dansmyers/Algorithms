# The Lost Sprint: NP-Completeness

## Description

Here, as promised, is an intro to the material that would have been part of our last sprint had, you know, the world not screwed
itself up quite so bad.

This micro-unit will let you dig into two important topics in theoretical CS: the concept of NP-completeness and the famous P = NP problem.

## Key Ideas

### Overview
The CLRS chapter on NP-completeness can be complex and a bit daunting, so let's try to sum up some of the main points as a primer before
you engage with the text.

Almost all of the problems we've looked at this semester have had **polynomial** time complexity, with solution algorithms that were
O(n<sup>*k*</sup>) in the worst case for some *k*. These problems are, in some sense, "easy" in that we can solve most instances of 
practical interest with reasonable amounts of computing power.

There are some problems, though, that do not have any known polynomial-time solution algorithms: we've talked about, for example,
algorithms that have exponential complexities like O(2<sup>*n*</sup>). These problems tend to be "hard" or **intractable** for anything
other than very small values of *n*.

The NP-complete problems are a set of problems that are interesting because of some properties they share:

- There are no "easy" polynomial-time solutions to any of them, but it also hasn't been proven that any NP-complete problem
**can't** be solved in polynomial time. This is in contrast to some other hard problems that are known to have, for example,
exponential lower bounds on their complexities and can never have efficient solutions. The NP-complete problems are, for now, in a
kind of theoretical Limbo, where we don't know how hard they really are.

- The NP-complete problems have a huge number of interesting practical applications in fields like logistics, operations research,
and networking.

- The NP-complete problems are all, in an important way, "equal" to each other. If an efficient solution algorithms for any one of
them was ever discovered, it would imply that efficient algorithms exist for **all of them**.

- There are some cases where one version of a problem is known to be NP-complete, but a similar problem is known to be polynomial. The
fact that relatively small changes in a problem's formulation can lead to big changes in its apparent complexity is the kind of thing
that drives theoretical computer scientists bonkers (in a good way).

### What Does It Mean to Be NP?

It might be tempting to think that "NP" stands for "non-polynomial", but the term *NP* officially stands for **non-deterministic polynomial time**. The concept of non-determinisim originally came out of research on Turing machines and the name has stuck around,
but most books, including CLRS, don't rely on non-deterministic Turing machines to describe what a NP problem is (thankfully).

Here's the more concise modern definition of an NP problem:

- It's hard to calculate an exact answer to the problem.

- But easy to verify if a proposed answer is correct.

More formally, the class NP consists of the problems with solutions that can be **verified** in polynomial time. Let's unpack this idea
by looking at one famous problem.

### The Traveling Salesman Problem

Imagine a traveling salesman, who has to visit a number of cities to make sales calls. He wants to find a route that will let him start 
at his home, visit every city, and then return home, **taking the shortest possible distance for the entire route**.

Here's an example, [from MentalFloss](https://www.mentalfloss.com/article/84064/road-trip-genius-calculates-shortest-route-through-47-national-parks), showing the optimal route to make a circuit through all 47 mainland National Parks.

<img src="https://images2.minutemediacdn.com/image/upload/c_fill,g_auto,h_1248,w_2220/f_auto,q_auto,w_1100/v1555306224/shape/mentalfloss/primary_159.png" width="50%" />



## Reading

## Deliverables

