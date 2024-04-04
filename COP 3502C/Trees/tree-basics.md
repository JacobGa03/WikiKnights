---
title: Intro to Trees
author:
    - Jacob Gadberry
---

# Introduction

Another useful data structure that we will discuss in COP 3502 are Trees. In COP 3502 you will focus on a couple of different type of trees: Binary Trees, Binary Search Trees, AVL Trees, Tries, and Heaps. Let's start with the simplest tree we will discuss: a Binary Tree. 

## Why Trees?

If we look back at Linked Lists, what made them useful compared to array? It was easier to add more items since we could simply attach a new node to the Linked List where ever we wanted. What was a drawback? It took more time to find an item in our Linked List, assuming items were stored in an ordered fashion, because we couldn't index into it. Remember at worst we had an `O(n)` runtime to search.

Trees allow us to have a linked data structure (easy to add items), and allow us to structure our data in a way where it is easier to find, add, and delete items.

Here is an picture of what a binary tree might look like
```
                    +-------+
                    |   A   |
                    +-------+
                  /           \
        +-------+               +-------+           
        |   B   |               |   C   |
        +-------+               +-------+
      /           \           /          \
    X          +-------+     X            X
               |   D   |
               +-------+
             /           \
            X            X
```

## Defining the Binary Tree in code

Before we do anything with binary trees, we first need to set up a way to represent them in C. As the word binary implies, each node in the tree can have a max of two children. To keep track of the children, each node will contain two pointers, `left` and `right`. Each node will store some sort of data; this could be an `int`, `char`, `char*`, or another struct you create. Lastly, a property ALL Trees share is that there are no cycles allowed. If node A points to node B, and node B points to node A, then there is a cycle. 

```c
typedef struct node{
    struct node* left;
    struct node* right;
    int val; //NOTE: Any kind of information can be stored here
}node;
```

## Traversing a Binary Tree

Now that we have a Binary Tree constructed we need a way to search for items within our new data structure. How should traverse the tree? 

An iterative approach in this situation will be quite difficult since there is no easy we to keep track of paths we've traversed. Can you think of a better way?

One thing that is really useful about Trees is that they are recursive in nature. The left and right sub-trees are really just smaller version of the main trees from which they come. Because of this fact, we can utilize recursion to traverse through a Binary Tree.

//TODO: Describe the 3 basic Pre/In/Post order traversals
```c
//Print the data first
void PreOrder(treeNode* root){
	if(root == NULL)
		return;
	//Pre means data first
	printf("%d ", root->data);
	PreOrder(root->left);
	PreOrder(root->right);
}
//Print the data second
void InOrder(treeNode* root){
	if(root == NULL)
		return;
	InOrder(root->left);
	//In means data in the middle
	printf("%d ", root->data);
	InOrder(root->right);
}
//Print the data last
void PostOrder(treeNode* root){
	if(root == NULL)
		return;
	PostOrder(root->left);
	PostOrder(root->right);
	//Post means data at the end
	printf("%d ", root->data);

}
```

## Binary Search Tree

With regular Binary Trees we did not define a way of placing items into the tree. This makes it harder to search for items, since we have no way of knowing where items lie within the Binary Tree. If we think about it, a search on a Binary Tree with data arbitrarily placed will still do no better than a Linked List search, `O(n)`. Think about why this is.

Building off of what we've discussed, we will add another property to our Binary Tree: any data less than the root will be placed in the left sub-tree and any value greater than or equal to the root will go in the right sub-tree. 

## Conclusion



## Additional Resources

[Binary Tree Bootcamp: Full, Complete, & Perfect Trees. Preorder, Inorder, & Postorder Traversal.](https://www.youtube.com/watch?v=BHB0B1jFKQc&t=1033s)

[MIT OpenCourseWare Binary Trees](https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/resources/lecture-6-binary-trees-part-1/)

[Introduction to Binary Tree – Data Structure and Algorithm Tutorials](https://www.geeksforgeeks.org/introduction-to-binary-tree-data-structure-and-algorithm-tutorials/)

## Credits

Thanks to professor Arup Guha, as this tutorial is an adaptation of his class notes. If you would like to view them click [here](https://www.cs.ucf.edu/~dmarino/ucf/transparency/cop3502/lec/BinaryTrees-1.pdf).