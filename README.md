# ExpNo 2 : Implement Depth First Search Traversal of a Graph

**Name:** K Mithran 

**Register Number:** 212225220064

## Aim

To Implement Depth First Search Traversal of a Graph using Python 3.

## Theory

**Depth First Traversal (DFS)** for a graph is similar to the Depth First Traversal of a tree. The only difference is that, unlike trees, graphs may contain cycles (a node may be visited more than once). Therefore, a Boolean visited array is used to avoid processing the same node multiple times. A graph can have more than one valid DFS traversal.

Depth First Search (DFS) is an algorithm used for traversing or searching tree and graph data structures. The algorithm starts from a root node (or any arbitrary node in a graph) and explores as far as possible along each branch before backtracking.

### Step 1
Initially, the stack and visited arrays are empty.

![Step 1](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/640b3c6f-3ac1-49a2-a955-68da9a71f446)

- Stack and visited arrays are empty initially.

### Step 2
Visit node **0** and put its adjacent nodes that have not yet been visited into the stack.

![Step 2](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/86dcf7d9-1f9d-49b0-a821-5976a6e77606)

- Visit node **0**.
- Push its adjacent nodes (**1, 2, 3**) into the stack.

### Step 3
Now node **1** is at the top of the stack. Visit node **1** and push all its unvisited adjacent nodes into the stack.
