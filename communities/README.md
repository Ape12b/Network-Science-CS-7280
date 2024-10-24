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

# Transitivity and Clustering Coefficient

## 1. Transitivity
Transitivity in a network refers to the likelihood that if node A is connected to node B, and node B is connected to node C, then node A is also connected to node C. This concept is important in social networks, where the "friend of my friend is also my friend" scenario is common. Perfect transitivity means that every component is a clique, though in most networks, transitivity is partial.

### Measuring Transitivity
- Consider a path of two edges (A-B-C).
- If there is also a direct edge from A to C, then this path forms a closed triangle (A-B-C-A).
- The clustering coefficient quantifies this transitivity.

## 2. Clustering Coefficient
The clustering coefficient measures the degree to which nodes in a network tend to cluster together. It is the ratio of closed triplets (three nodes that form a triangle) to the total triplets (three nodes connected by two edges).

### Formulas for Clustering Coefficient

- **Global Clustering Coefficient**:
  - \( C = \) (Number of closed triplets) / (Number of total triplets)
  - Where a triplet is a set of three nodes with two or three connecting edges.

- **Alternative Formula (using triangles)**:
  - \( C = 3 \times \) (Number of triangles) / (Number of connected triples)
  - Where a triangle consists of three nodes with three edges, and a connected triple is a set of three nodes with two edges.

- **Local Clustering Coefficient for a Node \( i \)**:
  - \( C_i = \) (Number of pairs of neighbors of \( i \) that are connected) / (Total number of pairs of neighbors of \( i \))
  - This can also be expressed as:
    - \( C_i = 2 \times E_i / [k_i \times (k_i - 1)] \)
  - Where \( E_i \) is the number of connections between the neighbors of \( i \), and \( k_i \) is the degree of node \( i \).

These formulas provide insights into how likely it is for a network to contain clustered or densely connected regions.

# Notes on Reciprocity in Network Analysis

## 1. Reciprocity Definition
Reciprocity in network analysis refers to the mutual exchange of ties or connections between nodes in a directed network. If node A connects to node B and node B also connects back to node A, the relationship is reciprocal. 

This measure is commonly used in social networks to assess the level of mutual connections, which can indicate:
- Trust
- Cooperation
- Balance in social relationships

## 2. Measuring Reciprocity
- The simplest measure of reciprocity is the proportion of reciprocal ties over the total number of directed ties. A higher proportion suggests a network with a high degree of mutual exchanges.
- Reciprocity can also be assessed through more complex statistical models that account for factors like network size and density, which can affect the likelihood of reciprocal ties.

## 3. Applications of Reciprocity
- **Social Networks**: Reciprocity is often linked to concepts of friendship, alliances, and mutual support. It helps identify the strength and balance of relationships within a network.
- **Communication Networks**: Reciprocity applies to communication networks as well, where two-way exchanges can enhance robustness and efficiency.

## 4. Reciprocity and Network Dynamics
- A high level of reciprocity can lead to network stability, as mutual ties often imply trust and reduced conflict.
- In directed networks, such as organizational hierarchies, lower reciprocity levels may indicate asymmetrical power dynamics, as relationships are not mutual but directed from superiors to subordinates.

These insights into reciprocity highlight its significance in understanding the structure and function of various networked systems, especially in the social sciences.

# Notes on Signed Edges and Structural Balance

## 1. Signed Edges
- **Definition**: Signed edges are edges in a network that carry a positive or negative sign. They represent relationships that can be either friendly/positive or hostile/negative.
- **Use Cases**: Commonly used in social networks to capture sentiments like friendship (positive) or rivalry (negative).
- **Interpretation**: In networks with signed edges, the nature of relationships can influence the dynamics of interactions. For example:
  - Positive edges can indicate alliances, trust, or cooperation.
  - Negative edges can indicate conflicts, competition, or distrust.

## 2. Structural Balance
- **Concept**: Structural balance is a theory that examines the stability of relationships in networks with signed edges.
- **Balance Conditions**: According to structural balance theory, a triangle (three nodes and three edges) is considered balanced if:
  - All three edges are positive, or
  - Two edges are negative and one edge is positive.
- **Imbalance**: A triangle is unbalanced if:
  - It has one negative edge and two positive edges.
  - All three edges are negative.
- **Implications**: The theory suggests that people tend to shift their relationships to achieve balance, so unbalanced triangles will often change over time to reduce tension. For example:
  - If two friends share a mutual enemy, the relationship is balanced.
  - If two friends dislike each other’s friend, the relationship is imbalanced and may lead to shifts to restore balance.

## 3. Applications of Structural Balance
- **Social Dynamics**: Structural balance can be used to predict changes in social networks as people adjust their relationships to achieve a state of balance.
- **Conflict Resolution**: In networks with frequent conflicts, structural balance theory helps understand how alliances and enmities might evolve over time.
- **Organizational Analysis**: In workplace settings, understanding structural balance can aid in identifying potential sources of tension and avenues for team-building.

These concepts provide insights into how the signs of relationships affect the stability and evolution of networks.
