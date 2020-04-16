# The Lost Sprint: NP-Completeness

## Description

Here, as promised, is an intro to the material that would have been part of our last sprint had, you know, the world not screwed
itself up quite so bad.

This micro-unit will let you dig into two important topics in theoretical CS: the concept of NP-completeness and the famous P = NP problem.

## Key Ideas

## Overview
The CLRS chapter on NP-completeness can be complex and a bit daunting, so let's try to sum up some of the main points as a primer before
you engage with the text.

Almost all of the problems we've looked at this semester have had **polynomial** time complexity, with solution algorithms that were
O(n<sup>*k*</sup>) for some *k*. These problems are, in some sense, "easy" in that we can solve many instances of practical interest with
reasonable amounts of computing power.

There are some problems, though, that do not have any known polynomial-time solution algorithms: we've talked about, for example,
algorithms that have exponential complexities like O(2<sup>*n*</sup>). These problems tend to be "hard" or **intractable** for anything
other than very small values of *n*.

The NP-complete problems are a set of problems that have attracted interest because of some interesting properties they share:

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




## Reading

## Deliverables

