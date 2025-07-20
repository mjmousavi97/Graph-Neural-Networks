
# 🔷 Applications of Laplacian Matrix in Graph Theory

This notebook explores **three powerful applications** of the **Laplacian matrix** in graph theory and network analysis:

1. **Spectral Graph Partitioning**
2. **Graph Visualization using Laplacian Eigenmaps**
3. **Random Walks and Stationary Distributions**

---

## 📌 1. Graph Partitioning using Laplacian Matrix

### Goal
Minimize the number of edges (cut size $R$) between two node groups.

### Key Equations
- Cut Size:
  $$
  R = \frac{1}{4} \sum_{i,j} A_{ij}(1 - s_i s_j)
  $$
- Laplacian Form:
  $$
  R = \frac{1}{4} s^T L s
  $$

### Spectral Bisection Algorithm
- Compute $L = D - A$
- Find the eigenvectors of $L$
- Use the **Fiedler vector** (second smallest eigenvector) to split nodes:
  - $s_i > 0$: Group 1
  - $s_i < 0$: Group 2

---

## 📌 2. Graph Visualization via Eigenvectors

### Objective
Minimize the total squared edge lengths in layout:
$$
\Delta^2 = \frac{1}{2} \sum_{ij} A_{ij}(x_i - x_j)^2 = x^T L x
$$

### Method
- Compute the Laplacian matrix $L$
- Use:
  - Second smallest eigenvector of $L$ → x-coordinate
  - Third smallest eigenvector of $L$ → y-coordinate

This ensures connected nodes appear spatially close in the layout.

---

## 📌 3. Random Walks on Graphs

### Definitions
- $A$: Adjacency matrix
- $D$: Degree matrix
- $p(t)$: Probability vector at time $t$

### Transition Rule
$$
\mathbf{p}(t+1) = A D^{-1} \mathbf{p}(t)
$$

### Stationary Distribution
$$
\mathbf{p} = A D^{-1} \mathbf{p} \quad \Rightarrow \quad L D^{-1} \mathbf{p} = 0
$$

The long-term probability of being at node $i$ is:
$$
p_i \propto k_i
$$
Meaning: **nodes with higher degree are visited more often**.

---

## 📦 Requirements

```bash
pip install numpy networkx matplotlib
```

---

## 📊 Features

- Computes eigenvalues/eigenvectors of Laplacian matrix
- Performs graph partitioning via the Fiedler vector
- Visualizes graphs using Laplacian eigenmaps
- Simulates and explains random walks and stationary distributions
- Uses Rayleigh quotient and quadratic forms

---

## 📚 Theoretical Tools Used

- Rayleigh Quotient
- Eigenvalue decomposition
- Fiedler vector and spectral gap
- Perron–Frobenius Theorem
- Null space of Laplacian matrices

---

## 👤 Author

This notebook is an educational tool for graph learners, data scientists, and researchers exploring **spectral graph theory**, **visualization**, and **random walks**.
