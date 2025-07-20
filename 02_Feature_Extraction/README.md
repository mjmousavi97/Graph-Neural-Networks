# 🧠 Graph Concepts and Feature Extraction

This notebook provides an in-depth exploration of **graph representation learning**, focusing on **node-level feature extraction** and foundational concepts in graph theory. It is ideal for anyone looking to understand how mathematical and structural properties of graphs are used in machine learning tasks like node classification.

---

## 📌 Overview

Graph-structured data is ubiquitous across various fields, from social networks to biological systems. However, analyzing and understanding such data—especially at scale—requires mathematical abstractions.

The primary learning tasks in graph domains include:

- **Node-level prediction**
- **Edge-level prediction**
- **Graph-level prediction**

This notebook mainly focuses on **node-level features**, which are essential for node classification problems.

---

## 🎯 Key Topics Covered

### 🔍 Node Classification and Graph Dependencies

Unlike traditional classification tasks that assume i.i.d. samples, graph-based classification violates this assumption because nodes are connected and influence one another.

> 💡 Hence, node classification in graphs is often approached as a **semi-supervised learning** problem.

---

### 📘 Node Degree

- **Definition**: The degree of node $i$ is the number of edges adjacent to node $i$.
- **Formula**:  
  $$
  d_i = \sum_j A_{ij}
  $$
  where $A$ is the adjacency matrix of the graph.

---

### 🧮 Adjacency Matrix

- A matrix $A$ where $A_{ij} = 1$ if an edge exists between nodes $i$ and $j$, otherwise $0$.
- Symmetric for undirected graphs.

---

### 📗 Degree Matrix

- A diagonal matrix $D$ where each diagonal element is the degree of a node:  
  $$
  D_{ii} = d_i
  $$

---

### 📘 Graph Laplacian

- Defined as:  
  $$
  L = D - A
  $$
- The Laplacian is key in many applications such as spectral clustering and graph signal processing.

---

### 🧠 Eigenvectors and Visualization

- Eigenvectors of the Laplacian matrix are used to project the graph into lower-dimensional spaces (e.g., for 2D visualization).
- The 2nd and 3rd smallest eigenvectors (excluding the trivial zero eigenvalue) often define an effective 2D layout.

---

## 📦 Dependencies

- `networkx`
- `numpy`
- `matplotlib`
- `scipy`

Install using:

```bash
pip install networkx numpy matplotlib scipy
```

---

## 📊 Visualizations

The notebook includes:

- Degree distributions
- Graph layouts using spectral methods
- Adjacency, Degree, and Laplacian matrix visualizations

---

## 📁 File Structure

- **Notebook**: The `feature_extraction_of_graph.ipynb` file contains both explanation and code cells.
- **Sections**:
  - Intro to Graph Learning
  - Node-Level Features
  - Matrix Representations
  - Laplacian and Spectral Methods
  - Graph Visualization Techniques

---

## 📚 Use Cases

This notebook serves as an educational tool for:

- Graph theory enthusiasts
- Machine learning students
- Practitioners exploring GNNs
- Network analysis researchers

---

## ✍️ Author
Mohammad Javad — 2025  
[GitHub Profile](https://github.com/mjmousavi97) | [LinkedIn](https://linkedin.com/in/mjmousavi97)


Feel free to contribute or fork this project. If you use this material in your research or coursework, proper citation is appreciated.
