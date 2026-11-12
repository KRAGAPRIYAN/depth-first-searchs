# ExpNo 2: Implement Depth First Search Traversal of a Graph

### Name: K RAGAPRIYAN

### Register Number: 212225040323

---

### Aim:

To implement Depth First Search Traversal of a Graph using Python 3.

### Theory:

**Depth First Traversal (DFS)** for a graph is similar to Depth First Traversal of a tree. The only difference is that, unlike trees, graphs may contain cycles (a node may be visited more than once). A Boolean visited array is used to avoid processing a node more than once.

A graph can have more than one DFS traversal. Depth First Search is an algorithm for traversing or searching tree or graph data structures. The algorithm starts at the root node (selecting an arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

**Step 1:** Initially, the stack and visited arrays are empty.

![Step 1](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/640b3c6f-3ac1-49a2-a955-68da9a71f446)

The stack and visited arrays are empty initially.

**Step 2:** Visit node 0 and put its adjacent nodes that are not yet visited into the stack.

![Step 2](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/86dcf7d9-1f9d-49b0-a821-5976a6e77606)

Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack.

**Step 3:** Now, node 1 is at the top of the stack. Visit node 1, pop it from the stack, and put all its adjacent nodes that are not yet visited into the stack.

![Step 3](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/e6017942-08b1-4742-87ad-c97eb97bf985)

Visit node 1.

**Step 4:** Now, node 2 is at the top of the stack. Visit node 2, pop it from the stack, and put all its adjacent nodes that are not yet visited (i.e., 3 and 4) into the stack.

![Step 4](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c)

Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack.

**Step 5:** Now, node 4 is at the top of the stack. Visit node 4, pop it from the stack, and put all its adjacent nodes that are not yet visited into the stack.

![Step 5](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/20b76a05-5668-4da5-8189-e10fb1bb7238)

Visit node 4.

**Step 6:** Now, node 3 is at the top of the stack. Visit node 3, pop it from the stack, and put all its adjacent nodes that are not yet visited into the stack.

![Step 6](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/3b88f04a-7846-4f75-89b4-22bbd5b48e52)

Visit node 3.

Now, the stack becomes empty, which means that all the nodes have been visited, and the DFS traversal ends.

---

### Algorithm:

1. Construct a graph with nodes and edges.
2. Depth First Search uses a stack and recursion.
3. Insert a START node into the stack.
4. Find its successors or neighbours and check whether each node has been visited.
5. If a node has not been visited, add it to the stack. Otherwise, call the function again until no more nodes need to be visited.

---

### Python Program:

```python
def dfs(graph, start):
    visited = set()
    stack = [start]
    result = []

    while stack:
        node = stack.pop()

        if node not in visited:
            visited.add(node)
            result.append(node)

            for neighbor in reversed(graph[node]):
                if neighbor not in visited:
                    stack.append(neighbor)

    return result


n, e = map(int, input().split())

graph = {}

for i in range(e):
    u, v = input().split()

    if u not in graph:
        graph[u] = []
    if v not in graph:
        graph[v] = []

    graph[u].append(v)
    graph[v].append(u)

start = list(graph.keys())[0]

print(dfs(graph, start))
```

---

### Sample Input 1:

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

---

### Sample Output 1:

```text
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
```

---

### Sample Input 2:

```text
5 5
0 1
0 2
0 3
2 3
2 4
```

---

### Sample Output 2:

```text
['0', '1', '2', '3', '4']
```

---

## OUTPUT 1

![Output 1](<Screenshot 2026-11-12 100029.png>)

## OUTPUT 2

![Output 2](<Screenshot 2026-11-12 100518.png>)

---

### Result:

Thus, a graph was constructed, and Depth First Search traversal was successfully implemented for the same graph using Python 3.