# Graphs

A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.

![img](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DirectedGraph.PNG)

- Vertex: A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
- Edge: An edge is a connection between two nodes.
- Neighbor: The neighbors of a node are its adjacent nodes,are connected via an edge.
- Degree: The degree of a vertex is the number of edges connected to that vertex.

## Undirected Graphs

> is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.

![undirected](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3d/Undirected_graph.svg/1280px-Undirected_graph.svg.png)

## Directed Graphs (Digraph)

> also called a Digraph is a graph where every edge is directed.

![Directed Graphs (Digraph)](https://upload.wikimedia.org/wikipedia/commons/thumb/5/51/Directed_graph.svg/1280px-Directed_graph.svg.png)

### Complete vs Connected vs Disconnected

- ""Complete"" Graphs A complete graph is when all nodes are connected to all other nodes.

- ""Connected"" A connected graph is graph that has all of vertices/nodes have at least one edge.

- ""Disconnected"" A disconnected graph is a graph where some vertices may not have edges.

### Acyclic vs Cyclic

> **An acyclic graph is a directed graph without cycles.**

> A cycle is when a node can be traversed through and potentially end up back at itself.

#### Graph Representation

> We represent graphs through:

> Adjacency Matrix Adjacency List

![img](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DirectedGraph.PNG)

## Breadth First Traversal Code Example:

```

ALGORITHM BreadthFirst(vertex)
    DECLARE nodes <-- new List()
    DECLARE breadth <-- new Queue()
    DECLARE visited <-- new Set()

    breadth.Enqueue(vertex)
    visited.Add(vertex)

    while (breadth is not empty)
        DECLARE front <-- breadth.Dequeue()
        nodes.Add(front)

        for each child in front.Children
            if(child is not visited)
                visited.Add(child)
                breadth.Enqueue(child)

    return nodes;

```

## Real Life Examples:

1. GPS and Mapping
2. Driving Directions
3. Social Networks
4. Airline Traffic
5. Netflix uses graphs for suggestions of products
6. Directed vs Undirected
