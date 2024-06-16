---
title: Intro to Stacks 
author:
    - Jacob Gadberry
---

# Introduction

The next data structure that we will study is called a stack. The stack data structure just represents a stack of things, either primitives or structs that you define. We will learn about how implement stacks and a few of their applications.

# What is a Stack?

According to Don Knuth, a stack is "a linear list for which all insertions and deletions are made at one end of the list." The quote illustrates the `Last in First Out` principle (LIFO) which all stacks follow. The last item placed in the stack will be the first item to be removed.

One thing that is interesting about stacks is that we call them "Abstract Data Types". This is because we only define the behavior of the data structure without describing how it is stored.

# Stack Implementation

The first thing that we should discuss is how to create a stack in C. There are two main ways that we can implement stacks: linked lists and arrays.

## Stack Behavior

There are two main things that a stack can do `push` and `pop`. `push` puts an item on the top of the stack. `pop` removes an item from the top of the stack. Sometimes you might implement `peek` which returns the item on the top of the stack without removing it. 

## Linked List

One way we can implementing a stack is with a linked list.

## Array

Another way we can implement stacks is with arrays.

# Applications of Stacks

One application where we can use Stacks is when evaluating mathematical expressions in `postfix notation`. In order to understand what `postfix` even means, let's relate it to something you're probably more familiar with.

When we write `3 + 7 * 5`, we call placing the arithmetic operators in between the numbers `infix notation`; this is because we place the operators `in`between the operands. As you might guess `postfix notation` is when we place the operators AFTER the operands. 

"Why would we need this?" Well, when computers perform arithmetic they have no concept of operator precedents like we do. This precedents allows us to remove the ambiguity that arises when we write equations in `infix notation`. 

> Think about it, if you didn't have operator precedents could you arrive at one "correct" answer to `3 + 7 * 5`?

## Postfix Evaluation

Given this expression `3 7 5 * +` (the `postfix` equivalent of the expression above), find what it equals. 

## Infix to Postfix

# Conclusion

## Additional Resources

[Data Structures: Stacks and Queues - HackerRank](https://youtu.be/wjI1WNcIntg)

## Credits

Donald E. Knuth "The Art of Computer Programming, Vol. 1: Fundamental Algorithms, 3rd Edition"

Thanks to professor Arup Guha, as this tutorial is an adaptation of his class notes. If you would like to view them click [here](https://www.cs.ucf.edu/~dmarino/ucf/transparency/cop3502/). Once on the main site, click `Study Materials`, then go to `Stacks`. There will be all of his notes on this topic.