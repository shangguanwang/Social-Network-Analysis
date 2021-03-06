## Robustness of a network 

The ability to maintain its structure if edge or node removal.

## Disconnect a network

==> What is the smallest number of `nodes` to be removed if we want to 
disconnect a graph

```python
import networkx as nx

G = nx.Graph()
G.add_edges_from([('A', 'K'), ('A', 'B'), ('A', 'C'), ('B', 'C'),
                  ('B', 'K'), ('C', 'E'), ('C', 'F'), ('D', 'E'),
                  ('E', 'F'), ('E', 'H'), ('F', 'I'), ('I', 'J')])

print(nx.node_connectivity(G))
# 1
print(nx.minimum_node_cut(G))
# {'C'}
```

==> What is the smallest number of `edges` to be removed if we want to 
disconnect a graph

```python
import networkx as nx

G = nx.Graph()
G.add_edges_from([('A', 'K'), ('A', 'B'), ('A', 'C'), ('B', 'C'),
                  ('B', 'K'), ('C', 'E'), ('C', 'F'), ('D', 'E'),
                  ('E', 'F'), ('E', 'H'), ('F', 'I'), ('I', 'J')])

print(nx.edge_connectivity(G))
# 1
print(nx.minimum_edge_cut(G))
# {('F', 'I')}
```

__Robust network has large minimum cuts__

## Disconnect a connection between two nodes in graph

Block the connection by removing __nodes__ in graph

```python
import networkx as nx

G = nx.Graph()
G.add_edges_from([('A', 'K'), ('A', 'B'), ('A', 'C'), ('B', 'C'),
                  ('B', 'K'), ('C', 'E'), ('C', 'F'), ('D', 'E'),
                  ('E', 'F'), ('E', 'H'), ('F', 'I'), ('I', 'J')])

print(nx.node_connectivity(G, 'A', 'H'))
# 1
print(nx.minimum_node_cut(G, 'A', 'H'))
# {'E'}
```

Block the connection by removing __edges__ in graph

```python
import networkx as nx

G = nx.Graph()
G.add_edges_from([('A', 'K'), ('A', 'B'), ('A', 'C'), ('B', 'C'),
                  ('B', 'K'), ('C', 'E'), ('C', 'F'), ('D', 'E'),
                  ('E', 'F'), ('E', 'H'), ('F', 'I'), ('I', 'J')])

print(nx.edge_connectivity(G, 'A', 'H'))
# 1
print(nx.minimum_edge_cut(G, 'A', 'H'))
# {('E', 'H')}
```