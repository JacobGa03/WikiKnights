---
title: Binary Search Trees 
author:
  - Jacob Gadberry 
toc: false
---

## Introduction

Binary Search Trees give us a data structure that will allow us to store data in a strategic way to make searching for data quicker than just a simple `O(n)` linear search.

## Binary Search Tree

With regular Binary Trees we did not define a way of placing values into the tree. This makes it harder to search for values since we have no way of knowing where they lie within the Binary Tree. If we think about it, a search on a Binary Tree with data placed arbitrarily will still do no better than a Linked List search, `O(n)`. Think about why this is.

Building off of what we've discussed, we will add another property to our Binary Tree: any data less than the root will be placed in the left subtree and any value greater than or equal to the root will go in the right subtree. 

Here is an example of a Binary Search Tree:

```
                    +--------+
                    |   10   |
                    +--------+
                  /           \
        +-------+               +--------+           
        |   5   |               |   15   |
        +-------+               +--------+
      /           \           /           \
    X          +-------+     X        +--------+
               |   9   |              |   20   |
               +-------+              +--------+
             /           \           /          \
            X            X          X            X
```

Now we have a data structure where we've placed values in a way where we can perform a more clever search that can help improve runtime from our regular Binary Tree.

## Running a Search on a Binary Search Tree

Now that we have defined what a Binary Search Tree is, let's consider running search on the Binary Search Tree above.

Let's look for `9`; and consider how we could devise some code to search for `9` on this Binary Search Tree. It's important to state that we ALWAYS start our search at the root of the tree `10`.

```
                    +--------+    
                    |   10   |  <---
                    +--------+
                   /          \
```

Since we are searching for `9` and we are currently looking at `10` we can safely look into the left subtree since we know that `9` must be in the left subtree since ALL values less than `10` will reside in the left subtree.

```
                    +-------+    
                    |   5   |   <---
                    +-------+
                   /          \
```

`9` is greater than `5` so we will need to look in `5`'s right subtree to find it.

```
                    +-------+    
                    |   9   |   <---
                    +-------+
                   /          \
```

Great! Now we have found the `9`, the value we were looking for.

Let's run another search. This time let's look for `25`

Note that runtime of the search is `O(h)`

```
                    +--------+    
                    |   10   |    <---
                    +--------+
                   /          \
```

Since `25` is greater than `10`, we will need to search the right subtree.

```
                    +--------+    
                    |   15   |    <---
                    +--------+
                   /          \
```

`25` is greater than `15`, so we search the right subtree.

```
                    +--------+    
                    |   20   |    <---
                    +--------+
                   /          \
```

`25` is greater than `20`, so we search the right subtree.

```
                    +-------+    
                    |   X   |     <---
                    +-------+
```

Now we have hit a `NULL` node, which must mean that `25` is not in our Binary Search Tree.

## Search in Code

Now that we have traced through an example, lets write some code to do the search. Remember that Binary Trees are recursive in nature, so a lot of our code will also be recursive.

```c
int search(treeNode* root, int val){
  if(root == NULL){
    return 0; // Return an int that represents an unsuccessful search
  }
  // We have to search the left subtree
  if(val < root->data){
    return search(root->left ,val);
  }
  // We have to search the right subtree
  else if(val > root->data){
    return search(root->right, val);
  }
  //If val isn't greater or less than, it must be equal to root
  else{
    return 1; // Return an int that represents a successful search
  }
}
```

## Runtime Analysis

What would the runtime of this search algorithm be? 

Unlike our search on a regular Binary Tree, which was `O(n)`, this search will be based on the height on the Binary Search Tree. We say that the runtime of this algorithm will be `O(h)`, where `h` is the height of the binary tree.

The height of a Binary Tree is the longest path from root to leaf. Therefore, at the worst, we will have to traverse the longest path to possibly find the desired value.

## Conclusion

We've learned about a better way to store data within a recursive tree structure. Doing this takes us a step in the direction of getting a better structure that will allow us to insert and search quickly.

## Additional Resources

[Binary Search Tree - GeeksForGeeks](https://www.geeksforgeeks.org/binary-search-tree-data-structure/)

[Calculating the Height of a Binary Tree](https://www.baeldung.com/cs/binary-tree-height)

[DSA Binary Search Trees](https://www.w3schools.com/dsa/dsa_data_binarysearchtrees.php)

[Lecture 5: Binary Search Trees, BST Sort - MIT OCW](https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-fall-2011/resources/lecture-5-binary-search-trees-bst-sort/)

## Credits

Thanks to professor Arup Guha, as this tutorial is an adaptation of his class notes. If you would like to view them click [here](https://www.cs.ucf.edu/~dmarino/ucf/transparency/cop3502/lec/BinaryTrees-1.pdf).