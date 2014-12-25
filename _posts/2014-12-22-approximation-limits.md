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
is called the 3-SAT problem. An *instance* of the problem has a collection
of *clauses* $C_1,\cdots, C_m$ of the form,

<p style="text-align:center">
<img src="../../images/3sat.jpg" width="600px" style="margin: 10px 20px"/>
</p>

where $x_1,\cdots, x_n$ are *variables* which takes $0,1$ values. The goal is to find an
assignment of $0,1$ to the variables, such that each of the clauses 
evaluates to $1$ in *[Boolean logic]()*, if it exists. Such an assignment is 
said to *satisfy* the instance and such an instance is called *satisfiable*. This problem is NP-Complete (and was in fact the first problem that
was proved to be NP-Complete by Cook and Levin).

#### Approximation

One way to relax the $3$-SAT problem, is to only ask for an algorithm that
given a  *satisfiable instance*,
finds an assignment that satisfies (makes a clause evaluate to 1),
99% of the clauses. Such an algorithm is called an *approximation
algorithm* for the original $3$-SAT problem with *approximation factor* $0.99$.

Instead of $0.99$, if we only require the *approximation factor* to be $7/8$,
then there is a very stupid approximation algorithm, which does not
even need to look at instance of the problem. But this algorithm uses some
randomness and answers correctly only most of the times. Most programming
languages allow algorithms to choose random numbers during execution, hence
these can be implemented in computers.

>All the algorithm does is for every variable, assign a random $0,1$ value. Since
a clause is the Boolean OR of $3$ variables, it will not be satisfied only
when all the variables are $0$, the chances of which are $1/8$. Hence this
stupid algorithm gives an assignment with satisfies $7/8$ fraction of the 
clauses (most of the time).

#### Limits

The algorithm above is very trivial. May be an algorithm can obtain an
approximation factor better than $7/8$, by further looking at the
clauses in the problem instance. 

>In 1998, Hastad proved that if there is a polynomial time algorithm with
factor better than $7/8$, then NP-Complete problems have polynomial time
solutions. This not expected to happen. Hence that trivial algorithm 
cannot be improved.

#### Probabilistically Checkable Proofs


#### Unique Games Conjecture
