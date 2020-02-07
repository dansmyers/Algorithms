# Sprint 2 Quiz Review

## Recurrences

I **promise** that the first page of the quiz will have the following form:

- You will be given a recurrence relation
- Use the master theorem to determine the complexity of *T*(*n*)
- Use induction to show that a given function satisfies the recurrence

For example, consider the recurrence

*T*(*n*) = 4*T*(*n* / 2) + *n*<sup>2</sup>

Use the master theorem to derive a Theta complexity for this recurrence (hint: look at case 2). Then use induction to show that the
recurrence is satisfied by

*T*(*n*) = *n*<sup>2</sup> lg *n*
