# Bug Byte Puzzle
This project was inspired by a puzzle shared by the Jane Street, which can be found [here](https://www.janestreet.com/bug-byte/). The goal is to fill in the edge weights of a graph using the numbers 1 through 24 exactly once, while adhering to specific node constraints. Once the graph is filled, the shortest path between two nodes reveals a secret message.

## Puzzle Instructions
Fill the Graph: Use each number from 1 to 24 exactly once as edge weights in the given graph.

Node Sum Constraints: Certain nodes have constraints where the sum of all edges directly connected to them must equal a specified value.

Path Sum Constraints: There are nodes from which a non-self-intersecting path must exist with edge weights summing to specified values. Multiple target sums may exist for a single node.

Reveal the Message: After filling the graph, find the shortest weighted path between two specified nodes. Convert the weights on this path to letters (1=A, 2=B, etc.) to reveal a secret message.

## My Programmatic Approach
To solve this puzzle programmatically, I used a combination of constraint satisfaction techniques and shortest path algorithms. The solution is implemented in Python, utilizing the Z3 solver for constraint satisfaction and Dijkstra's algorithm for finding the shortest path.

### Key Steps and Insights
1. **Graph Representation:**
- Define a graph class to manage vertices and edges.
- Initialize the graph with known and unknown edge weights.

2. **Constraint Solving:**
- Set up node sum constraints using the Z3 solver.
- Ensure each edge weight is unique and within the range of 1 to 24.
3. **Path Verification:**
- Verify the existence of required paths for nodes with path sum constraints using Depth First Search (DFS).
4. **Shortest Path Calculation:**
- Implement Dijkstra's algorithm to find the shortest path between the specified nodes.
- Convert the weights along this path to letters to uncover the secret message.