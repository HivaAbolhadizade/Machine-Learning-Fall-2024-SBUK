# HW3 - Linear Regression Analysis

## 📌 Overview

This project implements and analyzes **Linear Regression** with single and multiple variables. The main goals are:

* Predicting output values
* Evaluating model accuracy
* Comparing different parameter estimation and optimization methods

Methods used:

* **Closed-form solution**
* **Batch Gradient Descent (BGD)** and **Stochastic Gradient Descent (SGD)**
* **L2 Regularization (Ridge Regression)**

---

## 🔹 Linear Regression with a Single Variable

### Cost Function

$$
J(\theta) = \frac{1}{2m} \sum_{i=1}^m \big( h_\theta(x_i) - y_i \big)^2
$$

where $h_\theta(x_i) = \theta_0 + \theta_1 x_i$

### Parameter Estimation Methods

1. **Closed-form solution** – Direct calculation of $\theta_0$ and $\theta_1$
2. **Stochastic Gradient Descent (SGD)** – Parameters updated per sample
3. **Batch Gradient Descent (BGD)** – Parameters updated using the average gradient over all data

### Results Analysis

* **Closed-form:** Very accurate; minimizes $MSE$ effectively
* **BGD:** Similar performance to closed-form; stable convergence
* **SGD:** Faster but less accurate, with noticeable fluctuations

### Parameter Comparison

* $\theta_0$ and $\theta_1$ from closed-form and BGD are almost identical
* SGD values slightly differ due to its stochastic nature
* Indicates closed-form and BGD prioritize accuracy, while SGD prioritizes speed

### Cost Convergence

* **BGD:** Smooth and steady decrease of cost
* **SGD:** More fluctuations; slower convergence to a stable value

---

## 🔹 Linear Regression with Multiple Variables

### Data & Preprocessing

* Features include gender, region, smoking status, etc.
* Encoding:

  * Gender & smoking → Integer Encoding
  * Region → One-Hot Encoding (OHE)

> **Why One-Hot Encoding?**
> Prevents introducing artificial numerical relationships between categories and maintains feature independence.

### Parameter Estimation

1. **Closed-form solution (MSE)**
2. **Incremental training data analysis** – Observing test MSE from 10 to 1000 samples
3. **Gradient Descent** – Both batch and stochastic methods

**Observations:**

* Test error decreases significantly with more training data
* After a certain dataset size, MSE converges

### Training Curves

* Both **train and test errors** decrease over epochs
* Convergence indicates proper model optimization
* Small gap between train and test error → no significant overfitting

### L2 Regularization

* Added to the cost function; optimal $\lambda$ searched in $10^{-4} - 10^4$
* Observations:

  * Increasing $\lambda$ reduces training error steadily
  * Test error decreases initially, then increases → overfitting at low $\lambda$, underfitting at high $\lambda$
  * Optimal $\lambda \approx 1$ ($\log_{10}\lambda = 0$)

### Model Comparison (With/Without Regularization)

* Regularized model achieves lower test error
* Helps prevent overfitting and balances training and test performance

---

## ✅ Conclusions

* **Closed-form solution:** Fast and accurate, but limited for very large datasets
* **Gradient Descent:** Scalable to large datasets

  * **SGD:** Faster, less accurate
  * **BGD:** Slower, more accurate
* **L2 Regularization:** Reduces overfitting, balances bias-variance tradeoff
