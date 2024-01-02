## Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

- What is a binary tree
- What is the difference between a binary tree and a Binary Search Tree
- What is the possible gain in terms of time complexity compared to linked lists
- What are the depth, the height, the size of a binary tree
- What are the different traversal methods to go through a binary tree
- What is a complete, a full, a perfect, a balanced binary tree

### What is a binary tree?

A binary tree is a type of data structure used to store and organize data in a hierarchical manner. It is called "binary" because each node in the tree can have at most two children. A binary tree typically has a root node at the top, and all other nodes in the tree are connected to the root node through a series of parent-child relationships. The nodes are arranged in a way that resembles the branches of a tree, hence the name "tree". Binary trees are commonly used in computer science for tasks such as sorting, searching and data retrieval.

### What is the difference between a binary tree and a Binary Search Tree?

A Binary Search Tree (BST) is a specific type of binary tree that is designed to support fast searching and insertion of data.
The main difference between a general binary tree and a BST is that in a BST, the nodes are arranged in a specific order based on their values. In a BST, each node's value is greater than or equal to the values of all nodes in its right subtree, and less than or equal to the values of all nodes in its left subtree. This allows for efficient searching and insertion of data because the tree can be traversed in a systematic manner to find a specific node or insert a new one.
In contrast, a general binary tree does not have any specific order to its nodes, and data can be added and searched in any order.

Let's say you want to store a list of numbers in a BST. The root node of the tree could be the number 5. The left child of the root node could be the number 2, and the right child could be the number 8. The left child of the node 2 could be the number 1, and the right child could be the number 4. The right child of the node 8 could be the number 9. So, the tree would look like:

```
      5
2         8
1         9
```

in a BST, the value of each node is greater than or equal to the values of all nodes in its left subtree, and less than or equal to the values of all nodes in its right subtree. This means that for the node 5, all the nodes in its left subtree (node 2) must be less than or equal to 5, and all the nodes in its right subtree (node 8) must be greater than or equal to 5.
So in this case, since the node 2 is in the left subtree of the node 5, its value (2) is less than 5, which satisfies the BST property.

### What is the possible gain in terms of time complexity compared to linked lists?

Binary Search Trees can have some big advantages over linked lists in terms of time complexity for certain operations.
For example, searching for a specific element in a linked list can take O(n) time, since you have to traverse the entire list to find what you're looking for. However, in a BST, searching for a specific element can be done in O(log n) time, which is much faster for large data sets.
Inserting a new element into a linked list also takes O(n) time, since you have to traverse the list to find the right spot to insert the new element. In a BST, inserting a new element can be done in O(log n) time, since you can do a binary search to find the right spot for the new element.
So overall, BSTs can offer big performance gains over linked lists for certain operations, especially as the size of the data set grows.

### What are the depth, the height, the size of a binary tree?

- **Depth**: The depth of a binary tree is the longest path from the root node to any leaf node in the tree. For example, in the BST example I gave earlier, the depth of the tree would be 3 because the longest path from the root node (5) to a leaf node (1 or 9) is 3 nodes long.
- **Height**: The height of a binary tree is the maximum depth of any node in the tree. So in the BST example, the height of the tree would also be 3 because the maximum depth of any node is 3 (i.e. the depth of the nodes 1 and 9).
- **Size**: The size of a binary tree is the number of nodes it contains. In the BST example, the size of the tree would be 5 nodes.

### What are the different traversal methods to go through a binary tree?

There are three main ways to traverse a binary tree:

- **Inorder Traversal**: This method traverses the tree by visiting the left subtree first, then the root node, then the right subtree. This method produces the nodes in sorted order.
- **Preorder Traversal**: This method traverses the tree by visiting the root node first, then the left subtree, then the right subtree.
- **Postorder Traversal**: This method traverses the tree by visiting the left subtree first, then the right subtree, then the root node.
  Each of these traversal methods can be useful for different purposes, depending on how you want to access and process the data in the tree.

### What is a complete, a full, a perfect, a balanced binary tree?

Those are some fancy terms, but I'll do my best to break them down!

- **Complete Binary Tree**: A complete binary tree is a binary tree in which every level, except possibly the last, is completely filled, and all nodes in the last level are as far left as possible. In other words, all the nodes are filled in from left to right, and all the nodes at the same level are at the same depth.
- **Full Binary Tree**: A full binary tree is a binary tree in which every node has either 0 or 2 children. In other words, every node is either a leaf node (with 0 children) or an internal node (with 2 children).
- **Perfect Binary Tree**: A perfect binary tree is a binary tree in which all internal nodes have two children and all leaves are at the same depth. In other words, the tree is symmetrical and has a very specific structure.
- **Balanced Binary Tree**: A balanced binary tree is a binary tree in which the left and right subtrees of every node differ in height by at most 1. This type of tree is important because it allows for efficient searching and insertion of data.
