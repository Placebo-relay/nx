# nx

maxflow 2783
```python
import networkx as nx
import matplotlib.pyplot as plt

# Example input data
n = 4  # Number of nodes
m = 5  # Number of edges
edges = [
    (1, 2, 3),
    (1, 3, 2),
    (2, 3, 1),
    (2, 4, 2),
    (3, 4, 4)
]

# Create a directed graph
G = nx.DiGraph()

# Add edges to the graph
for a, b, c in edges:
    G.add_edge(a, b, capacity=c)

# Calculate maximum flow from source (1) to sink (4)
flow_value, flow_dict = nx.maximum_flow(G, 1, 4)

# Print the maximum flow value
print("Maximum flow value:", flow_value)

# Draw the graph
pos = nx.spring_layout(G)  # positions for all nodes
nx.draw(G, pos, with_labels=True, node_size=700, node_color='lightblue', arrows=True)
edge_labels = nx.get_edge_attributes(G, 'capacity')
nx.draw_networkx_edge_labels(G, pos, edge_labels=edge_labels)

# Show the plot
plt.title("Directed Graph with Capacities")
plt.show()
```
