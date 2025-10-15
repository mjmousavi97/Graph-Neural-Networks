# Node Classification on Cora Dataset with Vanilla GNN and GCN

## Project Overview
This repository demonstrates node classification on the **Cora citation network dataset** using **Vanilla Graph Neural Networks (GNNs)** and **Graph Convolutional Networks (GCNs)**. The goal is to classify each publication (node) into one of 7 categories based on its features and graph structure.

---

## Dataset
**Cora Dataset** (Sen et al., 2008)
- 2,708 publications (nodes)
- 10,556 citation links (edges)
- Each node has a 1,433-dimensional binary feature vector (bag-of-words)
- 7 target classes
- Citation links are undirected
- No isolated nodes or self-loops

### Data Statistics
| Attribute | Value |
|-----------|-------|
| Number of graphs | 1 |
| Number of nodes | 2,708 |
| Number of edges | 10,556 |
| Number of node features | 1,433 |
| Number of classes | 7 |
| Directed edges | No |
| Isolated nodes | No |
| Self-loops | No |

---

## Key Concepts
- **Vanilla Neural Network (MLP)**: Uses only node features for classification without graph structure.
- **Vanilla GNN**: Aggregates neighbor information via adjacency matrix multiplication.
- **GCN**: Normalizes aggregation based on node degrees to prevent high-degree nodes dominating embeddings.

---

## Implementation

### Libraries
- Python 3.x
- PyTorch & PyTorch Geometric
- NumPy, Pandas, Matplotlib, NetworkX

### Main Components
1. **MLP for Node Classification**: Input -> Linear -> ReLU -> Linear -> LogSoftmax, Cross-Entropy Loss, Adam optimizer.
2. **Vanilla GNN**: Uses adjacency matrix for neighbor aggregation and linear layers.
3. **GCN**: Degree-normalized aggregation with two GCNConv layers and ReLU.

### Training
- Epochs: 100
- Learning rate: 0.01
- Weight decay: 5e-4
- Evaluation: Accuracy on validation and test masks

---

## Results
| Model | Test Accuracy |
|-------|---------------|
| MLP (feature-only) | 52.3% |
| Vanilla GNN | 71.6% |
| GCN | 80.2% |

Observation: Using graph structure improves classification, and GCN normalization boosts stability and accuracy.

---

## Usage
1. Install dependencies: `pip install torch-geometric torch pandas matplotlib networkx`
2. Run the notebook to train and evaluate models.
3. Visualize graph with NetworkX or export as `.graphml`.

---

## References
- Sen, P., et al. (2008). Collective Classification in Network Data. AAAI.
- Kipf, T., & Welling, M. (2017). Semi-Supervised Classification with Graph Convolutional Networks. ICLR.
'''

