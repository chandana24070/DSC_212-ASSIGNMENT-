Modularity on the Karate Club Graph

After performing recursive spectral modularity partitioning on Zachary’s Karate Club graph, we obtain multiple communities across several iterations. At each split, the leading eigenvector of the modularity matrix identifies a division that maximizes modularity. The algorithm naturally stops when the largest eigenvalue of the restricted modularity matrix becomes non-positive, indicating that further splits would not improve modularity.

1. How Communities Evolve

In the early iterations, the graph divides into two large communities corresponding closely to the known factions in the original karate club (Mr. Hi vs. the Officer). As the recursive splits progress:

Larger communities break into smaller and more cohesive subgroups.

Dense clusters tend to remain intact until later iterations.

Sparse “bridge” nodes may get separated earlier due to having conflicting alignment.

This matches real-world expectations: cohesive groups resist splitting, while weakly attached nodes allow earlier partitioning.

2. Node Centrality Patterns Across Iterations
⋆ Degree Centrality

High-degree nodes such as node 0 and node 33 consistently maintain high degree centrality.

Their scores remain stable across iterations because they sit at the centers of their respective factions.

Nodes with very low degrees show minimal change across iterations.

Interpretation:
Degree centrality mainly reflects local structure, so community splitting has little influence on it.

⋆ Betweenness Centrality

Node 0 and node 32 (bridge-like nodes) show high betweenness before the first few splits.

After splitting, their betweenness drops sharply because once the graph is divided, they no longer lie on many shortest paths across communities.

Interpretation:
Betweenness decreases after partitioning because the graph becomes fragmented, reducing the number of paths requiring bridges.

⋆ Closeness Centrality

Closeness centrality is highest for central nodes in the original network.

After recursive splitting, the closeness of several nodes drops as the effective size of reachable components becomes smaller.

Nodes inside cohesive groups show stable closeness values.

Interpretation:
Closeness depends on how many nodes are reachable and at what distance; splitting communities increases the average distance between groups.

⋆ Clustering Coefficient

Nodes in highly interconnected portions of the graph (e.g., nodes in triangles and cliques) show high clustering coefficients that remain stable across iterations.

Nodes acting as bridges have low clustering coefficients and show little change.

Interpretation:
The clustering coefficient is highly local and is barely influenced by higher-level community splits.

3. Which Nodes Remain Central Across Splits?

Across all centrality measures:

• Node 0 and Node 33

Stay important across all iterations.

Maintain high degree and closeness centrality.

Act as anchors for their respective communities.

• Node 32

Appears as a structural bridge early on.

Loses betweenness importance after splitting.

• Nodes in tight clusters

Maintain high clustering values.

Are less affected by external splits.

4. How Community Structure Influences Metrics

Division reduces global connectivity, so closeness and betweenness typically decrease.

Nodes at faction boundaries lose influence once the graph is partitioned.

Local metrics (degree, clustering) remain stable because they depend only on immediate neighbors.

Bridge nodes show the biggest changes, especially in betweenness.

5. Final Summary

The recursive spectral modularity method reveals meaningful community boundaries in the karate club network. Nodes with high influence in the original unpartitioned graph often maintain structural importance, while bridge nodes lose centrality once the network is split. The evolution of centrality measures across iterations highlights how community division changes information flow, local cohesion, and the structural roles of individual nodes.
