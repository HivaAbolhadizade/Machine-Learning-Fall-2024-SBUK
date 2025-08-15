# HW5 - Backpropagation Implementation on Fashion-MNIST

## 📌 Overview

This project implements a **Multilayer Perceptron (MLP)** from scratch using **NumPy** and trains it on a subset of the **Fashion-MNIST** dataset. The focus is on demonstrating the **backpropagation algorithm**, which minimizes the network's error by updating weights to bring the outputs closer to desired values.

---

## 🔹 Backpropagation Algorithm

The algorithm consists of two main steps:

1. **Forward Pass:** Inputs are passed through the network to compute outputs.
2. **Backward Pass:** The output error is computed and propagated backward to update network weights using **gradient descent**.

Gradient for each weight is computed as:

$$
\frac{\partial L}{\partial w} = \frac{1}{N} \sum_{i=1}^{N} \frac{\partial L}{\partial y_i} \cdot \frac{\partial y_i}{\partial w}
$$

Where $L$ is the loss function and $w$ represents the network weights.

---

## 🔹 Model Components

* **Linear Layer:** Performs a matrix multiplication of inputs and weights.
* **ReLU Activation:** Introduces non-linearity.
* **Softmax Layer:** Converts outputs into probabilities.
* **Loss Function:** Cross-Entropy for classification tasks.

---

## 🔹 Training Results

* Selected classes: T-shirt, Trouser, Sneaker
* Final Accuracy: **98.48%**

---

## 🔹 Implementation Highlights

* Two hidden layers in the neural network
* Data normalization
* One-hot encoding for labels
* Gradient computation using the chain rule

---

## ✅ Conclusion

Backpropagation is a fundamental method for training neural networks. Combined with gradient descent, it effectively updates weights, improving model accuracy and predictive performance.


