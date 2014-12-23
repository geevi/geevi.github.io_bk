---

layout: page
title:  "Approximation and its Limits : Layman's Introduction to Probabilistically Checkable Proofs and Hardness of Approximation"

date:   2014-10-18 12:58:29

categories: puzzles 
mathjax: enable

---

### Approximation and its Limits
<span style="display: block; padding-bottom: 10px; font-size: 18px; text-align: center; font-weight: 300;
border-bottom: gray 1px dotted;">
A layman's introduction to probabilistically checkable proofs and hardness of approximation.</span>


In the previous blog post, we saw that computers as we know it cannot help in 
solving many puzzles and some of these puzzle need to be solved routinely.
So should we give up hope? Is there another way out?

One way out is to relax the conditions that is required of the solutions. 
For the sudoku puzzle, we might say that we are happy with solutions with
just the rows and columns having all distinct numbers and not the blocks.
If we further remove the condition that every column has distinct elements,
then the puzzle becomes easy to solve (since for every row we can fill
in the blanks without worrying about the other rows). For every puzzle, 
we would ideally like to do minimal relaxation and come up with
a polynomial time algorithm.  

Now lets consider a problem which has very wide practical application. It
is called the 3-SAT problem. An instance of the problem has a collection
of "clauses" 


consist of variables
$x_1,\cdots, x_n$ which takes $0,1$ values.


#### Sudoku
<p style="text-align:center">
<img src="../../images/sudoku_9x9.png" width="200px" style="margin: 10px 20px"/> <img src="../../images/sudoku_9x9_solved.png" width="200px" style="margin: 0px 20px"/>
</p>

Above is a sudoku puzzle. Since very few 
numbers are given, it is difficult to solve.
Neverthless a person might solve it in a few
hours. But what if the puzzle was "larger".
That is instead of a 9x9, it is a 16x16 version,
where numbers from 1 to 16 could be filled in.
It has similar restrictions on having all
numbers in rows and columns and sub blocks.

<p style="text-align:center">
<img src="../../images/sudoku_16x16.png" width="400px" style="margin: 10px 20px"/> </p>

Such a puzzle would be mind boggling for
humans to handle. But may be there is a 
clever computer program to do the job for
us. There is some hope, since a solution
given below for a sudoku puzzle is very
easy to verify. 


<p style="text-align:center">
<img src="../../images/sudoku_16x16_solved.png" width="400px" style="margin: 10px 20px"/> </p>

One just needs to check if every row, column and
sub block has all the numbers from 1 to 16. So
 an algorithm (a computer program) would be to 
go over all assignments of numbers to the blanks
and check if it is a solution. This might look
like a simple thing to do, except when one tries
to run the program. 

Suppose half the blanks were
already filled in a puzzle, the number of possiblilites
the program has to try is $16^{16 \times 16/2}$ (try all the 16 possibilities
for each of the $16\times 16/2$ blanks). This number is
more than the number of seconds since the Bing Bang,
more than the number of particles in the universe. No
matter how fast or large a computer we have, it will
keep running (if we can maintain it that way) till
our universe gets distroyed.

Hence the try all possiblilites is definitely not an
acceptable solution. We want a program which lets say
finds the solution in a day. As we saw, we would
also like to solve "larger" nxn versions of the puzzle.
9x9 was the case for $n=9$ and 16x16 for n=16. The try
all possiblilites algorithm that we saw, needs to try
$n^n$ possiblilites. This even for $n=16$ is a humonguous number,
because k is in the exponent. Suppose the number of steps
the algorithm runs is $n^c$ for some constant $c$, it wouldnt
be that bad. But yet all the algorithms known so far can
take $n^n$ time on some puzzles.

Stephen Cook and Karp found that Sudoku is not just a pathological
case for which reasonable algorithms cannot be found. They found
that a whole class of puzzles called NP-Complete (NPC), for which the same mistery exists.
They showed this by divising a way of solving any one puzzle in NPC by
using solutions to any other puzzle in NPC. That is for any pair of puzzles,
say Sudoku and Kakuro in NPC, they showed how to convert an instance of
sudoku to an instance of Kakuro such that solutions to the Kakuro puzzle
can be converted to a solution to the Sudoku puzzle. If that was confusing
what it means is that if there is a reasonable algorithm for any one puzzle
in NPC that would mean there is a reasonable algorithm for all puzzles in NPC! 

#### Why Care?

Who cares about solving puzzles when there are
more pressing problems in the world. These might appear to be
questions that a jobless unrealistic philosopher might ponder
about. Though it is not so. A lot depends on finding answers
to this question. 

Nobody would disagree that computers and
internet is one of the greatest things to happen in end of the
previous century. It holds a lot of prommise in bring the world
together, making people accept each other differences and 
solving those pressing needs for food, jobs and education. An
underlying technology that makes all this possible is encryption.
That is a way of sending messages so that only the intended person
is able to read it.

All the existing methods of encryption are based on the assumption
that NPC problems doesnt have reasonable algorithhms. That is if
somebody come up with a resonable algorithm for solving that
sudoku puzzle, he can break all the codes in the internet. 

Dont panic! your internet banking solutions are safe. We
dont expect this to happen. However we need to know what other
problems are in NPC. This will help us design better encryption
systems and many more.

#### A Philosophical Detour

Though most people are interested in solving those pressing problems
of the world, there are still some stupid harmless philosophers
who find it intereting to think about these for the sake of curiosity.









