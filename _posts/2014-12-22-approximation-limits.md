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


In the previous [blog post](/2014/puzzles.html), we saw that computer as we know it cannot help in 
solving many puzzles. But some of these puzzles need to be solved routinely in real life programs.
So should we give up hope? Is there another way out?

One way out, is to relax the conditions that is required of the solutions. 
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
of *clauses* $C_1,\cdots,C_m$ of the following form, 

<p style="text-align:center">
<img src="../../images/3SAT.png" width="600px" style="margin: 10px 20px"/> </p>

Here $x_1,\cdots, x_n$ are *variables* which takes  $0,1$ values. Here $\neg x_3$ is to be 
read as NOT of $x_3$, which is the value of $1- x_3$ and $\vee$ is the OR which evaluates to $1$
when at least one of the values is $1$. The goal is to find an
assignment of $0,1$ to the variables (if it exists), such that in each of the clauses 
evaluates to $1$. This was the
first problem that was proved to be NP-Complete by Cook and Levin.

#### Approximation

One way to relax the problem, is to only ask for an algorithm that
finds an assignment, if it exists, that satisfies (makes a clause evaluate to 1),
99% of the clauses. Such an algorithm is called an *approximation
algorithm* for the original $3$-SAT problem with *approximation factor*   $ 0.99$.

There is a very stupid approximation algorithm for $3$-SAT, which does not
even need to look at instance of the problem, and has an approximation factor of $7/8$ 
(i.e. if there is an assignment that satisfies all the clauses,
the algorithm is guaranteed to give an assignment that satisfies $7/8$ fraction of the clauses).
But this algorithm uses some
randomness and answers correctly only most of the times. Most programming
languages allows algorithms to choose random numbers during executions, hence
these can be implemented in computers.

>All the algorithm does is, for every variable, assign a random $0,1$ value. Since
a clause is the Boolean OR of $3$ variables, it will not be satisfied only
when all the variables are $0$, the chances of which are $1/8$. Hence this
stupid algorithm gives an assignment that satisfies a $7/8$ fraction of
the clauses (most of the time), without even looking at the problem.

#### Limits

#### Probabilistically Checkable Proofs