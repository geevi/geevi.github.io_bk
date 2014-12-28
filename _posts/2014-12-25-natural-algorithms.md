---
layout: page
title: "Hardness of Coloring Problems"
categories: puzzles
mathjax: enable
published: true
---

Slime mold is a fungus like the ones that grow on bread that is more than a week old. They are single
celled creatures, but often many of them form a group and start moving as a single body as shown in
the picture. 


If this body is cut, they can find their way back and re-unite.
Despite their modest existence, they have shown remarkable ability to learn, predict danger and
gather food efficiently. A team of Japanese and Hungarian researchers used the slime mold cleverly
to solve a maze puzzle. A fascinating video of the slime mold solving the maze can be found in
Youtube (https://www.youtube.com/watch?v=F3z_mdaQ5ac).


They built a maze like the one above. Covered it with pieces of the mold and placed its favourite
food, oatmeal at the entry and exit of the maze. After a few hours they found that the slime mold
had retracted and aligned its body along the path from entry to exit. Moreover if there were
multiple paths between entry and exit, it aligned along the shortest path.


This caused a lot of excitement among computer scientists, for whom finding the shortest path was
a very commonly occurring problem. What was even more amazing to them is that the slime mold
seemed to be able to solve the maze, even though it doesn’t have a central nervous system
coordinating the different parts. A similar system without a central coordination mechanism is
required for solving shortest path problems for computers connected through the internet, since
communication over the internet can take too much delay as often seen when one tries to load
Youtube videos.

How does the slime mold achieve this amazing feat? Scientists discovered that the body of the slime
mold can be thought of as a network of tubes where food is continuously transported. When more
food is transported the mold increases the diameter of that tube. Also when a tube has very less
food transport happening, it contracts. So the tubes near to the oatmeal at the entry and exits will
grow bigger. Also the tubes along the dead ends inside the maze will grow smaller and eventually
disappear as they hardly contribute to the food transport. The most food transport will happen
along the shortest path and hence after some time the slime mold concentrates its body along this
path. Hence the slime mold gives an excellent algorithm that can be run on computers connected
across the internet to solve the shortest path problem.


