# ExpNo 2 : Implement Depth First Search Traversal of a Graph

<h3>Name: K Mithran A</h3>
<h3>Register Number: 212225220064 </h3>

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

![Step 3](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/e6017942-08b1-4742-87ad-c97eb97bf985)

- Visit node **1**.

### Step 4
Now node **2** is at the top of the stack. Visit node **2** and push its unvisited adjacent nodes (**3, 4**) into the stack.

![Step 4](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c)

- Visit node **2**.
- Push nodes **3** and **4** into the stack.

### Step 5
Now node **4** is at the top of the stack. Visit node **4**.

![Step 5](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/20b76a05-5668-4da5-8189-e10fb1bb7238)

- Visit node **4**.

### Step 6
Now node **3** is at the top of the stack. Visit node **3**.

![Step 6](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/3b88f04a-7846-4f75-89b4-22bbd5b48e52)

- Visit node **3**.

The stack becomes empty after all the nodes are visited, indicating that the DFS traversal is complete.

## Algorithm

1. Construct a graph with nodes and edges.
2. Depth First Search uses **Stack and Recursion**.
3. Insert the starting node into the stack.
4. Find its successors (neighbors) and check whether each node has been visited.
5. If a node has not been visited, visit it recursively. Continue until all reachable nodes are visited.

---

## Python Program

```python
from collections import defaultdict

def dfs(graph, start, visited, path):
    path.append(start)
    visited[start] = True

    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)

    return path

graph = defaultdict(list)

n, e = map(int, input().split())

for i in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)

start = "A"
visited = defaultdict(bool)
path = []

traversedpath = dfs(graph, start, visited, path)
print(traversedpath)
```

---

## Sample Input 1

```text
8 9
A B
A C
B E
C D
B D
C G
D F
G F
F H
```

## Sample Output 1

```text
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
```

---

## Sample Input 2

```text
5 5
0 1
0 2
0 3
2 3
2 4
```

> **Note:** For this input, change:

```python
start = "A"
```

to

```python
start = "0"
```

## Sample Output 2

```text
['0', '1', '2', '3', '4']
```

---

## Result

Thus, a graph was constructed and the implementation of **Depth First Search (DFS)** traversal using Python was successfully completed.
