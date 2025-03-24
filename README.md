
# 🧠 MGTA 415 Project: Image Classification via Prototyping

## 📌 Overview

This project explores **image classification** through the lens of **data prototyping**, aiming to reduce the complexity of training datasets while maintaining accuracy. By leveraging techniques like **random sampling** and **K-Means clustering** for prototype selection, we evaluate how well smaller, representative subsets can substitute full datasets in model training.

We apply these methods to three classic computer vision datasets:
- **MNIST** – Handwritten digits
- **EMNIST** – Extended handwritten characters
- **KMNIST** – Japanese character dataset

## 🎯 Objective

> Can we reduce the size of image datasets for training **without sacrificing model accuracy**?

This project treats image classification as a **data prototyping problem** by testing whether smart data selection strategies can:
- Decrease training time
- Reduce memory usage
- Maintain or even improve generalization on unseen data

---

## 🗃️ Datasets

| Dataset | Description | Classes | Samples |
|--------|-------------|---------|---------|
| MNIST | Handwritten digits (0–9) | 10 | 70,000 |
| EMNIST | Letters and digits | 62 | 814,255 |
| KMNIST | Hiragana characters | 10 | 70,000 |

---

## ⚙️ Prototyping Methods

### 🔹 Random Sampling
- Selects a random subset of the training data.
- Fast and easy, but may not preserve class balance or structure.

### 🔹 K-Means Clustering
- Clusters images and selects centroids as prototypes.
- Provides a more structured and representative subset.
- Variants:
  - **K-Means++**
  - **Random Initialization**

### 📊 Visual Samples

| Method | Example |
|--------|---------|
| Random | ![](./mnist-imgs/random_mnist.png) |
| K-Means | ![](./mnist-imgs/kmeans_mnist.png) |
| K-Means++ | ![](./mnist-imgs/kmeans_plus_mnist.png) |

---

## 🧪 Experiments & Results

### MNIST

#### KNN Accuracy on MNIST (K-Means++)
![](./mnist-imgs/k++.png)

#### KNN Accuracy on MNIST (Base K-Means)
![](./mnist-imgs/kmeans.png)

#### KNN Accuracy with Random Prototypes (MNIST)
![](./mnist-imgs/random_mnist.png)

---

### KMNIST

#### KNN Accuracy on KMNIST (Base K-Means)
![](./kmnist-images/kmeans_kmnist.png)

#### KNN Accuracy with Random Prototypes (KMNIST)
![](./kmnist-images/random_kmnist.png)

---

### EMNIST

#### KNN Accuracy on EMNIST (K-Means++)
![](./emnist-imgs/k++_emnist.png)

#### KNN Accuracy on EMNIST (Base K-Means)
![](./emnist-imgs/kmeans_emnist.png)

#### KNN Accuracy with Random Prototypes (EMNIST)
![](./emnist-imgs/random_emnist.png)

---

### CNN Experiment (with Lipschitz Regularization)

#### CNN Loss Comparison
![](./ex_imgs/lipschitz.png)

---

## 📁 Repository Structure

```
mgta415-project/
│
├── data/                         # Raw .npz files for MNIST/EMNIST/KMNIST
│   ├── MNIST/
│   ├── EMNIST/
│   └── KMNIST/
│
├── emnist.ipynb                 # Prototyping & classification on EMNIST
├── kmnist.ipynb                 # Prototyping & classification on KMNIST
├── mnist.ipynb                  # Prototyping & classification on MNIST
│
├── acl-ijcnlp2021-templates/    # LaTeX report and figures
│   └── mnist-imgs/              # Visualizations of prototype images
│
└── README.md                    # Project overview
```

---

## 📓 How to Run

1. Open and run the notebooks:
   ```bash
   jupyter notebook mnist.ipynb
   ```

---

## 🧾 Report

The full academic report is available in [`acl2021.tex`](./acl-ijcnlp2021-templates/acl2021.tex). It describes the motivation, methodology, and analysis of our findings in detail.

---

## ✍️ Authors

- Team members from MGTA 415 – Winter 2025  
- Contributions: Data analysis, modeling, visualizations, and report writing

---
