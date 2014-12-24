---
layout: page
title: "Approximation and its Limits : An Introduction to Probabilistically Checkable Proofs and Hardness of Approximation"
categories: puzzles
mathjax: enable
published: true
---

### Approximation and its Limits
<span style="display: block; padding-bottom: 10px; font-size: 18px; text-align: center; font-weight: 300;
border-bottom: gray 1px dotted;">
An introduction to probabilistically checkable proofs and hardness of approximation.</span>


In the previous [blog post](/2014/puzzles.html), we saw that computers as we know it cannot help in 
solving many puzzles and some of these puzzle need to be solved routinely.
So should we give up hope? Is there another way out?

One way out is, to relax the conditions that is required of the solutions. 
For the sudoku puzzle, we might say that we are happy with solutions with
just the rows and columns having all distinct numbers and not the blocks.
If we further remove the condition that every column has distinct elements,
then the puzzle becomes easy to solve (since for every row we can fill
in the blanks without worrying about the other rows). For every puzzle, 
we would ideally like to do minimal relaxation and come up with
a polynomial time algorithm.  


#### 3-SAT
Now lets consider a problem which has very wide practical application. It
is called the 3-SAT problem. An instance of the problem has a collection
of *clauses*,

<p style="text-align:center">
<img src="../../images/3sat.jpg" width="600px" style="margin: 10px 20px"/> </p>


consist of *variables*
$x_1,\cdots, x_n$ which takes $0,1$ values. The goal is to find an
assignment of $0,1$ to the variables, if it exists, such that each of the clauses 
evaluates to $1$ in *[Boolean logic]()*. This was the first problem that
was proved to be NP-Complete by Cook and Levin.

#### Approximation
One way to relax the problem, is to only ask for an algorithm that
finds an assignment, if it exists, that satisfies (makes a clause evaluate to 1),
99% of the clauses. Such an algorithm is called an *approximation
algorithm* for the original $3$-SAT problem with *approximation factor* $0.99$.

There is a very stupid approximation algorithm for $3$-SAT, which does not
even need to look at instance of the problem, and has an approximation factor of $7/8$ (i.e. if there is an assignment that satisfies all the clauses, the algorithm is guaranteed to give an assignment that satisfies $7/8$ fraction of the clauses).
But this algorithm uses some
randomness and answers correctly only most of the times. Most programming
languages allows algorithms to choose random numbers during exections, hence
these can be implemented in computers.

>All the algorithm does is for every variable, assign a random $0,1$ value. Since
a clause is the Boolean OR of $3$ variables, it will not be satisfied only
when all the variables are $0$, the chances of which are $1/8$. Hence this
stupid algorithm give an approximation factor $7/8$ (most of the time), without
even looking at the problem.

#### Limits

#### Probabilistically Checkable Proofs