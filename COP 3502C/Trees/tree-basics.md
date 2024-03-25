---
title: Intro to Trees
author:
    - Jacob Gadberry
---

# Introduction

Another useful data structure that we will discuss in COP 3502 is trees. In COP 3502 you will focus on a couple of different trees: Binary Trees, AVL Trees, Tries, and Heaps. This tutorial will be focused on Binary Trees. 

##  Defining the Tree

Before we do anything with binary trees, we first need to set up a way to represent them in C. As the word binary implies, each node in the tree can have a max of two children. To keep track of the children, each node will contain two pointers pointing to its children `left` and `right`. Lastly, each node will store some sort of data; this could be an `int`, `char`, `char*`, or another struct you create.

```c
typedef struct node{
    struct node* left;
    struct node* right;
    int val; //NOTE: Any kind of information can be stored here
}node;
```

## Conclusion



## Additional Resources

[Binary Tree Bootcamp: Full, Complete, & Perfect Trees. Preorder, Inorder, & Postorder Traversal.](https://www.youtube.com/watch?v=BHB0B1jFKQc&t=1033s)

[MIT OpenCourseWare Binary Trees](https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/resources/lecture-6-binary-trees-part-1/)

[Introduction to Binary Tree – Data Structure and Algorithm Tutorials](https://www.geeksforgeeks.org/introduction-to-binary-tree-data-structure-and-algorithm-tutorials/)

## Credits

Thanks to professor Arup Guha, as this tutorial is an adaptation of his class notes. If you would like to view them click [here](https://www.cs.ucf.edu/~dmarino/ucf/transparency/cop3502/lec/BinaryTrees-1.pdf).