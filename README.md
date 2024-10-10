# Network-Science: CS-7280
Collection of notes and code worked on for Network Science - CS-7280


# Network Measures and Metrics

This document provides an overview of key network metrics, focusing on centrality, cliques, cores, and components.

## 1. Centrality Measures
Centrality measures identify the most influential or important nodes in a network. Key types include:

- **Degree Centrality**: Measures the number of direct connections (edges) a node has. It’s useful for identifying influential nodes based on their immediate connections.
- **Eigenvector Centrality**: Extends degree centrality by considering not just the number of connections, but also the influence of those connections. A node connected to high-centrality nodes will also have a high score.
- **Katz Centrality**: Similar to eigenvector centrality but adds a baseline centrality to every node, which helps avoid zero scores for nodes with few connections.
- **PageRank**: A variant of Katz centrality that divides a node’s influence by the number of outgoing links. This helps prevent nodes with many outbound links from having disproportionate influence.
- **Hubs and Authorities**: Relevant in directed networks, this measure distinguishes between two roles:
  - **Authorities**: Nodes with valuable information.
  - **Hubs**: Nodes that link to many authorities.
- **Closeness Centrality**: Measures the average shortest path from a node to all other nodes, identifying those that can quickly reach others in the network.
- **Betweenness Centrality**: Measures the extent to which a node lies on paths between other nodes, indicating potential control over information flow.

## 2. Groups of Nodes
Different ways to understand subgroups within a network:

- **Cliques**: A clique is a subset of nodes where each node is directly connected to every other node in the subset. Cliques often indicate highly cohesive subgroups, like tightly-knit friend circles.
- **Cores**: A k-core is a connected subset where each node has at least k connections within the subset. This is useful for identifying resilient or influential clusters.
- **Components**: Components are maximal connected subgraphs where every node can reach every other node. A k-component extends this concept by requiring at least k independent paths between nodes, providing insight into the network's robustness.

These metrics are widely used in fields like social network analysis, biology, and computer science to understand the structure and dynamics of networks.
