+++
author = "Hashim Y"
title = "The Depressed Physics Student's Guide to Crank Nicholson implementation in C"
date = "2024-02-22"
description = "An educative article talking about the Crank Nicholson finite difference method for solving PDEs in C"
tags = ["C","Crank-Nicholson","Finite-Difference","Computational-Methods"]
+++

Recently, I had the displeasure of falling victim to a wolf in sheep's clothing, a "coding module" called Scientific Computing. The module itself was a lesson to always read the syllabus. While at first it seemed like an introductory C coding module, my feelings of contentment at understanding pointers quickly turned to abject horror the moment the lecturer started adding more than one funny little symbol next to a letter. 

The majority of this module revolved around mastering the solving of differential equations in C, and it's hard! It showed just how maths-intensive coding can be sometimes. Anyway, here's a breakdown of how to solve simple problems using the Crank-Nicholson method. 

First off, you need a band matrix. A band matrix is a matrix which contains exclusively non-zero information about the diagonal points, and has information relating to boundary conditions of your equations at all points for which i =/= j.  Your band matrix is going to contain all the information about your system's boundary conditions, so the way you set this up is the key to solving your problem. 

An example of how a band matrix may look:

$$ \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}$$


Your band matrix is going to be placed in to an equation of the form:

$$ Ax = b $$ (A standard eigenvalue equation!)

Here, your band matrix is represented by A, and x and b represent two arrays of values. The variables x and b represent the next set of values to be obtained (what we're solving for) and the current set of values we have (on first iteration, the starting value for each point in the co-ordinate space defined). If you're familiar with solving eigenvalue equations, the concept is the same. Using the LAPACKE package, we can invert matrices easily, and can hence use the package to solve the eigenvalue equation. 





If we think of a matrix as merely a transformation being performed on a co-ordinate system, then we can see that the band matrix is a representation of the time-evolution of the system with respect to the boundary conditions placed on to it. (Have I got this the wrong way around? If it was the right way around, we wouldn't have to solve the eigenvalue equation. )

In other words, every time the band matrix operates on the values contained in your system, we are causing the values stored in the resulting calculation to evolve with time, and hence we are solving our system. 