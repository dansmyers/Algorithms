# Sprint 2 Quiz Review

## Recurrences

I **promise** that the first page of the quiz will have the following form:

- You will be given a recurrence relation.
- Use the master theorem to determine the complexity of *T*(*n*). **You may bring a written copy of the master therorem with you**.
- Use induction to show that a given function satisfies the recurrence. You will only need to use the exact form of induction, not the Big-O version.

For example, consider the recurrence

*T*(*n*) = 4*T*(*n* / 2) + *n*<sup>2</sup>

Use the master theorem to derive a complexity for this recurrence (hint: look at case 2). Then use induction to show that the
recurrence is satisfied by

*T*(*n*) = *n*<sup>2</sup> lg *n*

You may assume that the recurrence is satisfied for a base case of *n* = 2.

Here are some more relations you can try:

- *T*(*n*) = *T*(*n* / 2) + *n* is Θ(*n*) and is satisfied by *T*(*n*) = 2*n* - 1

- *T*(*n*) = 2*T*(*n* / 2) + *n*<sup>2</sup> is Θ(*n*<sup>2</sup>) and is satisfied by *T*(*n*) = 2*n*<sup>2</sup> - *n*

## Quicksort

Be able to use the partition algorithm to divide an array.

Be able to give, in your own words, a justification for why quicksort is Θ(*n* lg *n*) in the average case and Θ(*n*<sup>2</sup>) when the input is already sorted.
