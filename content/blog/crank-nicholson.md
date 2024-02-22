+++
author = "Hashim Y"
title = "The Depressed Physics Student's Guide to Crank Nicholson implementation in C"
date = "2024-02-22"
description = "An educative article talking about the Crank Nicholson finite difference method for solving PDEs in C"
tags = ["C","Crank-Nicholson","Finite-Difference","Computational-Methods"]
+++

Recently, I had the displeasure of falling victim to a wolf in sheep's clothing, a "coding module" called Scientific Computing. The module itself was a lesson to always read the syllabus. While at first it seemed like an introductory C coding module, my feelings of contentment at understanding pointers quickly turned to abject horror the moment the lecturer started adding more than one funny little symbol next to a letter. 

The majority of this module revolved around mastering the solving of differential equations in C, and it's hard! It showed just how maths-intensive coding can be sometimes. Anyway, here's a breakdown of how to solve simple problems using the Crank-Nicholson method. 

First off, you need a band matrix. Your band matrix is going to contain all the information about your system, so the way you set this up is the key to solving your problem. 

Your band matrix is going to be placed in to an equation of the form:

$$ Ax = b$$