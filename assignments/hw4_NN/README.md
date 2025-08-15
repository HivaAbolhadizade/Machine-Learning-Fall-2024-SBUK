# HW4 - Neural Network Implementation on MNIST Dataset

## 📌 Overview

This project implements a **simple neural network** for classifying handwritten digits from the **MNIST dataset**, which contains 60,000 training images and 10,000 test images (digits 0–9). The model is implemented using **PyTorch**.

---

## 🔹 Model Architecture

* **Input Layer:** 784 neurons (flattened 28×28 images)
* **Hidden Layer 1:** 512 neurons, **ReLU** activation
* **Hidden Layer 2:** 512 neurons, **ReLU** activation
* **Output Layer:** 10 neurons (one for each digit class)

---

## 🔹 Training Setup

* **Loss Function:** CrossEntropyLoss (suitable for classification)
* **Optimizer:** Adam with learning rate 0.006
* **Batch Size:** 64
* **Epochs:** 5

---

## 🔹 Evaluation Metrics

| Metric    | Value  |
| --------- | ------ |
| Accuracy  | 0.9622 |
| Precision | 0.9626 |
| Recall    | 0.9622 |
| F1 Score  | 0.9621 |

> The results show that the model achieves high accuracy and maintains a good balance between precision and recall.

---

## 🔹 Optimizer Comparison

* **RMSProp:** Best performance, fastest loss reduction, highest test accuracy (\~98%)
* **Adam:** Good performance, similar to RMSProp
* **Adagrad:** Slightly weaker than RMSProp and Adam
* **SGD:** Simple but slower convergence, lower accuracy (\~80%)

**Observations:**

* RMSProp and Adam achieve rapid and stable loss reduction.
* SGD struggles with convergence and achieves lower accuracy.

---

## ✅ Conclusion

* **RMSProp** is the best-performing optimizer due to adaptive learning and fast loss reduction.
* **SGD** performs worse due to slower convergence.
* Future improvements could include learning rate adjustments and using techniques like **Momentum** to enhance performance.
