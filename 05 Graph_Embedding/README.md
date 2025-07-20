
# 🔁 Graph Representation Learning with DeepWalk

This project provides a comprehensive walkthrough of **graph representation learning**, focusing on **DeepWalk**, **skip-gram modeling**, and **embedding-based classification** using social networks.

---

## 📌 Overview

Graph representation learning aims to map graph nodes to low-dimensional vectors (embeddings) such that **structural and semantic properties** of the graph are preserved.

This notebook walks through:
- Node embeddings using matrix-based encoders
- Skip-gram Word2Vec theory and implementation
- DeepWalk: Random-walk-based unsupervised graph embedding
- Node classification with learned embeddings

---

## 🔷 Key Concepts

### 📊 Graph Embedding

Mapping a node $u$ to a vector $f(u) \in \mathbb{R}^d$ such that:
- Close nodes in the graph stay close in embedding space
- Structural patterns (e.g., communities) are preserved

---

### 🧠 Encoder-Decoder Framework

- **Encoder**: Maps node $v$ to embedding $\mathbf{z}_v$  
- **Decoder**: Predicts node similarity from $\mathbf{z}_u, \mathbf{z}_v$

Similarity matrix $S[u,v]$ can be derived from:
- Adjacency matrix $A$
- Common neighbors: $S_{CN} = AA$

---

## 🧩 Skip-Gram Model (Word2Vec)

### CBOW vs Skip-Gram

| Feature | CBOW | Skip-Gram |
|--------|------|-----------|
| Input | Context words | Center word |
| Output | Center word | Context words |
| Best for | Frequent words | Rare words |

Used here: **Skip-Gram**, trained using Word2Vec.

### Training Objective

Maximize:
$$
\frac{1}{N} \sum_{n=1}^N \sum_{-C \le j \le C, j \ne 0} \log p(w_{n+j} | w_n)
$$

Softmax probability:
$$
p(w_c | w_t) = \frac{\exp(h_c^\top h_t)}{\sum_{i=1}^{|\mathcal{V}|} \exp(h_i^\top h_t)}
$$

---

## 🔁 DeepWalk Algorithm

### Steps:
1. Generate **random walks** over the graph (treat as "sentences")
2. Apply **Word2Vec Skip-Gram** to the walk corpus
3. Get node embeddings

Each node is treated like a word; random walks become sentences.

---

### Dataset

- Graph: Zachary’s Karate Club (from `networkx`)
- Labels: 'Mr. Hi' (0) and 'Officer' (1)

---

## 🚶 Random Walks

Random walks simulate node co-occurrence:
```python
def random_walk(start, length):
    walk = [str(start)]
    for i in range(length):
        neighbors = list(G.neighbors(start))
        start = np.random.choice(neighbors)
        walk.append(str(start))
    return walk
```

---

## 🧠 Word2Vec with Gensim

```python
model = Word2Vec(
    walks, 
    sg=1,      # Skip-gram
    hs=1,      # Hierarchical Softmax
    window=10,
    vector_size=100,
    seed=1
)
```

---

## 📈 Node Classification

- Classifier: RandomForest
- Feature: Node embeddings
- Accuracy > 90% on test set

```python
clf.fit(embeddings[train], labels[train])
acc = accuracy_score(clf.predict(embeddings[test]), labels[test])
```

---

## 🗺️ Visualization

- Used **t-SNE** to visualize high-dimensional embeddings
- Clear separation of community labels

---

## 📦 Dependencies

```bash
pip install networkx matplotlib gensim scikit-learn
```

---

## 👤 Author
Mohammad Javad — 2025  
[GitHub Profile](https://github.com/mjmousavi97) | [LinkedIn](https://linkedin.com/in/mjmousavi97)

This notebook is ideal for graph ML learners and NLP enthusiasts who want to understand **embedding-based learning on graphs** using **random walks** and **Word2Vec**.

