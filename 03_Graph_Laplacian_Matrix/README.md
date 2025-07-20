
# 🌐 Spectral Graph Analysis and Walk Counting

This project presents a comprehensive exploration of **graph structure analysis** using linear algebra, with a focus on **walk counting**, **eigen decomposition**, and **spectral properties of adjacency and Laplacian matrices**.

---

## 📌 Overview

Graphs can be analyzed not only structurally but also algebraically. This notebook investigates:

- The number of walks of a given length using adjacency matrix powers
- Eigen decomposition of both adjacency and Laplacian matrices
- Spectral insights for graph connectivity, community structure, and visualization

---

## 🧮 Mathematical Concepts

### 🔹 Walk Counting

Given the adjacency matrix $A$ of a graph:
- Number of walks of length $l$ from node $j$ to $i$ is given by:
$$
N_{ij}^{(l)} = [A^l]_{ij}
$$

### 🔹 Eigen Decomposition

For matrix $A$:
$$
A u = \lambda u
$$
- $\lambda$: eigenvalue
- $u$: eigenvector

For symmetric matrices (undirected graphs), eigenvectors are orthogonal:
$$
A = U \Lambda U^{-1}
$$

### 🔹 Laplacian Matrix

$$
L = D - A
$$
Where $D$ is the degree matrix and $A$ is the adjacency matrix.

- Always has at least one eigenvalue = 0
- The number of zero eigenvalues equals the number of connected components
- The second smallest eigenvalue (algebraic connectivity) reflects the graph's overall connectedness

---

## 🧪 What’s Inside

- Graph construction using `NetworkX`
- Manual and automated matrix power calculations
- One-hot walk propagation: $Ax$, $A^2x$
- Eigen decomposition and visualization of:
  - Adjacency matrix
  - Laplacian matrix
- Use of **Perron–Frobenius Theorem** for interpreting eigenvectors
- Spectral graph visualization using color-mapped eigenvectors

---

## 📦 Dependencies

```bash
pip install numpy networkx matplotlib
```

---

## 📊 Graph Types Covered

- Simple undirected graphs
- Connected and disconnected graphs
- Graphs with isolated nodes

---

## 🎓 Applications

- Spectral clustering
- Graph visualization
- Random walks
- Network science
- Community detection

---

## 🧠 Notes

- The eigenvector of the largest eigenvalue (Perron root) has all positive entries.
- The Laplacian matrix always has real, non-negative eigenvalues.
- Row sums of the Laplacian are always zero.

---

## 👤 Author

This notebook is a teaching and research resource for those interested in the intersection of **graph theory**, **linear algebra**, and **network analysis**.
