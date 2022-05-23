# Sprint 3: Intermediate Data Structures

## Linked Lists
Time complexity for singly linked lists: 
* Insert or delete at beginning: O(1)
* Access a specific index: O(n) (we have to traverse node by node to get to the desired index)
* Insert or delete at a specific index: O(n) 

Variations:
* Singly Linked List (the standard version, each node stores a value and next pointer)
* Doubly Linked List (each node stores a value and both next and previous pointers)
* Circular Linked List (last node points to the first node rather than None)

In a singly-linked list, you may only traverse forward using the "next node" pointers, while in other implementations you may also be able to traverse backwards or go around the horn from end to beginning.

Depending on the implementation, you'll generally always have access to the "head" node (beginning of list) and also the "tail node" (end of list) in the case of a doubly linked list. 

Algorithms problems involving linked lists are often testing your ability to manipulate pointers, traverse through a linked list and handle edge cases. Here are some tricks that are helpful for many common whiteboarding questions:
* Dummy head: Create a dummy starting node and construct a list using its next pointer. Useful for handling edge cases like traversing an empty list
* Two-pointer technique: use two pointers to manipulate references to nodes. Useful for getting info about a list, e.g., detecting a cycle


## Queues and Stacks
A queue is a data structure that stores its items in a first-in, first-out (FIFO) order. 
A stack data structure handles information in a last-in, first-out (LIFO) order.

The names are helpful in remembering exactly these work! A queue is just like people standing in line, while a stack functions like a stack of plates. 

### Implementing a Queue
Elements can be added only at one end, the "rear", Elements can be removed only at the other end, the "front".
We call adding to a queue "enqueueing", and removing from a queue "dequeueing".

Use a linked list or dynamic array to implmement a queue.  
The linked list implementation has the advantage of O(1) insertion and deletion. (vs O(n) with the array implementation)

### Implementing a Stack
Elements can be added to or removed from a stack at only one end. Since we view this end as the "top" of the stack, we use the term "push" for add, and the term "pop" for remove. 

Similarly, you can use a linked list (O(1) push/pop) or dynamic array (O(n) push/pop) to implement a stack.

## Caching

## Binary Trees
Each node has:
* a value
* (optional) left child
* (optional) right child

A "leaf" is a node at the end of a branch of the tree, i.e., it has no children.

### Balanced Binary Trees
The height of left and right subtree of every node may differ, at most, by 1.


### Perfect Binary Trees
A "perfect" tree has every level completely filled. Every node has either 2 children or none, and the height/depth is exactly the same across the tree. 

By definition, a perfect binary tree is also balanced.

If you know the number of nodes in a perfect tree, n, you can calculate the tree height:
h = log2(n + 1)

And likewise, if you know the height you can calculate the number of nodes in a perfect tree:
n = 2^h - 1


## Binary Search Trees
* Left subtree contains children <= root
* Right subtree contains children > root

If they are balanced, BST's can provide better lookup and insert performance than non-BSTs.

Time complexity of get, insert, remove operations:
* O(n) for a non-balanced BST
* O(log n) for a balanced BST

Retreiving all the values in a binary search tree in order is simple -- just do an in-order (DFS) traversal. BSTs also have efficient O(log n) searches, just like a sorted array. The main advantage of using a BST over a sorted array is for more efficient insertions and deletions.

## Tree Traversal
Linked lists, stacks, and queues are linear data structures in the snese that there is really only one sensible way to traverse. However, for hierarchical data structures like trees, there are many possible ways to traverse.

There are two main categories for how to traverse a tree:

### Depth-first search (DFS)
In general, the idea here is to traverse all the way out to a leaf first, then move "across" the tree gradually, finding each leaf before moving on.

There are 3 variations of DFS:
* In-order: left, current, right
* Pre-order: current, left, right
* Post-order, left, right, current

Each of these can be implemented iteratively or recursively. Either way, a stack is the natural data structure for handling this kind of traversal! In an iterative implementation, you write your own stack pushes and pops, while in the recursive version it's the system call stack effectively doing the same thing. 

A good way to think about the role of the stack in these implementations is that we're stacking up the values that we've **seen but not "visited" (printed) yet.** Then we backtrack up the tree, visiting those nodes in reverse order after having visited all their subtrees.

### Breadth-first search (BFS)
For a BFS, we want to make our way all the way across the tree (it's "breadth") first. You can visualize this as traversing each "level" of the tree from left to right, saving the leaves for last.

Level-order: search left to right at each level. This can be implemented using a queue.

## Additional Resources
### Articles & Docs
* [Data Structures: Linked Lists](https://www.youtube.com/watch?v=njTh_OwMljA&ab_channel=HackerRank)
* [Hash Table Collision Resolution](https://eng.libretexts.org/Courses/Folsom_Lake_College/CISP_430%3A_Data_Structures_(Aljuboori)/07%3A_Hash_Tables/7.03%3A_Collision_resolution)
* [DJB2 Hash Function Explained](https://theartincode.stanis.me/008-djb2/)


### Videos
* [NeetCode: Reverse Linked List - Iterative AND Recursive](https://www.youtube.com/watch?v=G0_I-ZF0S38&ab_channel=NeetCode)

### Tools
* [Finite State Machine Designer](https://madebyevan.com/fsm/) - helpful for whiteboarding & visualizing linked lists
