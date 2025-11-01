# Node Classification on PubMed Dataset with GraphSAGE

## Project Overview
This repository demonstrates node classification on the **PubMed citation network dataset** using **GraphSAGE**. The goal is to classify each publication (node) into one of 3 categories based on its features and graph structure. GraphSAGE uses neighbor sampling to efficiently aggregate information from local graph neighborhoods.

---

## Dataset
**PubMed Dataset** (Yang et al., 2016)
- 19,717 publications (nodes)
- 44,338 citation links (edges)
- Each node has a 500-dimensional feature vector (TF/IDF weighted word vectors)
- 3 target classes
- Citation links are undirected
- No isolated nodes or self-loops

### Data Statistics
| Attribute | Value |
|-----------|-------|
| Number of graphs | 1 |
| Number of nodes | 19,717 |
| Number of edges | 44,338 |
| Number of node features | 500 |
| Number of classes | 3 |
| Directed edges | No |
| Isolated nodes | No |
| Self-loops | No |

---

## Key Concepts
- **GraphSAGE**: Learns node embeddings by sampling and aggregating features from a node’s local neighborhood.
- **Neighbor Sampling**: Reduces computation by only aggregating information from a fixed-size set of neighbors at each layer.
- **Inductive Learning**: Can generate embeddings for unseen nodes without retraining on the entire graph.

---

## Implementation

### Libraries
- Python 3.x
- PyTorch & PyTorch Geometric
- NumPy, Pandas, Matplotlib, NetworkX

### Main Components
1. **NeighborLoader**: Efficiently loads mini-batches of nodes and their sampled neighbors.
2. **GraphSAGE Model**: Two SAGEConv layers with ReLU activation and dropout.
3. **Training Loop**: Uses Cross-Entropy Loss and Adam optimizer; tracks training and validation accuracy.
4. **Evaluation**: Computes test accuracy on nodes masked for testing.

### Training
- Epochs: 200
- Learning rate: 0.001
- Weight decay: 5e-4
- Batch size: 16
- Neighbor sampling: 10 neighbors per layer

---

## Results
| Model | Test Accuracy |
|-------|---------------|
| GraphSAGE | ~75% |

Observation: GraphSAGE effectively captures local neighborhood information, leading to higher accuracy compared to feature-only models, especially on large graphs like PubMed.

---
