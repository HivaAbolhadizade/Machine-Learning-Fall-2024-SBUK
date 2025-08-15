# HW6 - Noise Reduction on Fashion-MNIST using PCA and Autoencoders

📌 **Overview**
This project compares **Principal Component Analysis (PCA)** and **Autoencoders** for image denoising on the **Fashion-MNIST** dataset. Gaussian noise is added to the dataset, and both methods are applied to reconstruct cleaner images. The focus is on evaluating their ability to preserve image details and reduce noise under different noise levels.

---

🔹 **PCA (Principal Component Analysis)**
A linear dimensionality reduction method that identifies directions (principal components) capturing the maximum variance in the data.

* **Steps**:

  1. Project noisy images onto a reduced set of principal components.
  2. Reconstruct images using only the selected components.
* **Strengths**: Works well for low-noise data and preserves global variance.
* **Limitations**: Struggles with high-noise data and loses fine details due to its linear nature.

---

🔹 **Autoencoders**
A type of neural network designed for data compression and reconstruction.

* **Architecture**:

  * **Encoder**: Compresses input images into a lower-dimensional representation.
  * **Decoder**: Reconstructs the original images from this compressed form.
* **Strengths**:

  * Learns **non-linear** relationships in data.
  * Performs well even with high noise levels.
  * Preserves more fine-grained image details.
* **Limitations**: Requires training and more computational resources.

---

🔹 **Dataset**

* **Fashion-MNIST**:

  * 60,000 training and 10,000 test images.
  * Grayscale, 28×28 pixels.
  * 10 clothing categories (e.g., T-shirt, Trouser, Sneaker, etc.).
* **Noise Addition**:

  * Gaussian noise with mean = 0 and standard deviation = predefined value.

---

🔹 **Results**

| Method      | Low Noise Performance | High Noise Performance | Detail Preservation |
| ----------- | --------------------- | ---------------------- | ------------------- |
| PCA         | ✅ Good                | ❌ Weak                 | ⚠ Limited           |
| Autoencoder | ✅ Good                | ✅ Strong               | ✅ High              |

**Key Findings**:

* PCA is effective for mild noise but loses details in high-noise scenarios.
* Autoencoders handle complex noise better and preserve the original image structure more effectively.

---

🔹 **Implementation Highlights**

* Gaussian noise generation for dataset augmentation.
* PCA-based denoising using scikit-learn.
* Deep Autoencoder built with TensorFlow/PyTorch.
* Visual comparison of original, noisy, and denoised images.

---

✅ **Conclusion**

* **Autoencoders** outperform PCA for high-noise conditions due to their non-linear learning capability.
* **PCA** remains a good choice for quick, low-complexity denoising in low-noise datasets.
* Combining PCA and Autoencoders could leverage the strengths of both methods.


