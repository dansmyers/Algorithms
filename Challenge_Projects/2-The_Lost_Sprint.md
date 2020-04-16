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

### What Is the Class of NP Problems?

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

There are two ways to think about a problem like the TSP:

1. As an **optimization** problem: given a map and the list of cities to visit, find the route of minimum distance.

2. As a **decision** problem: given the map, the list of cities, and a target distance *d*, determine if there is a route with length no more than *d*.

In the NP-completeness world, **we are interested in the decision version of the problem**. We don't need to find the **best** solution,
just find out if one with a length less than the target *d* exists.

This may seem like a big concession, but it really isn't: if I could solve the decision version of the problem efficiently, I could
still solve the full optimization version by binary searching on the distance *d*, adjusting it until I identify the smallest
distance that has a solution.

Here's the key idea:

- Actually solving the decision version by finding the route with length *d* or better is probably going to be hard. The naive algorithm would require enumerating all routes through the cities, which has factorial complexity.

- Suppose though, that a mysterious benefactor happens to give you a candidate solution to the problem. **It's easy to check if the
proposed solution actually solves the problem**: verify that it visits every city and that the total length of the route is less than
*d*. You can do that in polynomial time.

The class NP consists of problems that have this property: they're **hard to solve** but it's **easy to check** if a proposed solution
is valid.

### From NP to NP-Complete

Okay. A problem is in the class NP if it has this special "hard to solve, easy to check" property. What about **NP-complete** problems?

The standard statement is that the NP-complete problems are **as hard as any other problem in NP**. I've always found this phrasing
tough, because it relies on understanding the idea of relative hardness of problems.

Suppose you have a problem *P* that you want to solve, but don't have an efficient algorithm for. Also suppose that you have another
problem *Q* that **does** have an efficient algorithm. Here's a strategy for solving *P* efficiently:

1. Transform problem *P* into an instance of problem *Q*.

2. Use your efficient algorithm to solve *Q*.

3. Transform the solution for *Q* back into a solution for *P*.

This strategy will allow you to solve *P* efficiently, provided that the transformations in steps (1) and (3) don't take too much work.

What does this setup imply about the relationship between the difficulty of the two problems, *P* and *Q*?

- First, if *Q* has a polynomial-time algorithm, that would mean that *P* can also be solved in polynomial time (again, provided that
the transformation overhead in steps (1) and (3) is also polynomial). **Therefore, if *Q* is easy, *P* must also be easy**.

- How about if we go the other way? Suppose that *P* is a problem that we believe to be **hard**, like the Traveling Salesman Problem. If I can use *Q* to solve *P*, then *Q* **must also be hard**: if *Q* had an easy polynomial-time solution, it would imply that the TSP
has an easy polynomial solution, contradicting our assumption.

Therefore, if we start with *P* as a problem that we know to be hard, we can use this technique to show that a new problem *Q* must
also be hard, **at least as hard as *P***. This technique is called a **reduction**, because it "reduces" an instance of problem *P* to problem *Q*.

Through reduction, we can build up a chain of problems that could all be used to solve each other. Because an efficient algorithm for
any problem in the chain implies an efficient solution for all the others, we can say that they are all of "equal" difficulty, even
if the different problems don't appear to have anything in common with each other.

This "chain" of equivalent problems is the set of NP-complete problems.

- They all have the "hard to solve, easy to check" property.

- **Any other NP problem** can be transformed into an instance of an NP-complete problem.

### Cook's Theorem

In order to kick this process off, we need one problem that we know to be NP-complete. Once that problem is identified, we can use
the reduction argument to show that other problems are also NP-complete.

This result was provided in 1971 by Stephen Cook, who showed
that a problem called **Boolean satisfiability** was NP-complete. This turned out to be a fairly insane result, because it required
showing that **any problem in NP** could be turned into an instance of the Boolean satisfiability problem, which doesn't seem like a 
thing you should be able to do.

Section 34.3 in CLRS tells you more about Cook's result and Boolean satisfiability.


## Reading

## Deliverables

