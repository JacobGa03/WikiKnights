---
title: Linked List Basics
author:
  - Jacob Gadberry 
---

# Introduction

One of the first, and most basic, data structures that we will learn about in COP 3502 is Linked Lists. This data structure is really useful for a whole host of different problems. Here we will learn about the basics.

# What is a Linked List

A linked list is exactly what it sounds like, a list where all of the elements are linked together like a chain.

Here is an example of a linked list

```
+------+    +------+    +------+    +-----+    +-----+    +------+
| head | -> |  10  | -> |  15  | -> |  3  | -> |  1  | -> | NULL |
+------+    +------+    +------+    +-----+    +-----+    +------+
```

While this might just look like an array IT IS NOT! An array gives us the ability to index into different spots within our array. We cannot do this with linked list because all of the nodes reside in non-contiguous spots in memory. All of the `->` represent pointers that each node has pointing to the next.

A linked list are really useful for storing things when the number of items you need to store might not be known. We can also delete nodes pretty easily which allows us to save memory while not wasting it on unused slots like in an array.

# Linked List in Code

```c
typedef struct node{
    struct node* next; // A pointer to the next node
    int data; //NOTE: Any kind of data could go here
}node;
```

# Insert

# Delete

# Search

# Additional Resources

# Credits

Thanks to professor Arup Guha, as this tutorial is an adaptation of his class notes. If you would like to view them click [here](https://www.cs.ucf.edu/~dmarino/ucf/transparency/cop3502/). Once on the main site, click `Study Materials`, then go to `Linked List`. There will be all of his notes on this topic.