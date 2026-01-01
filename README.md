# Image Denoising: Deep Autoencoder vs. Variational Autoencoder

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?style=flat&logo=tensorflow)
![Keras](https://img.shields.io/badge/Keras-Deep%20Learning-red?style=flat&logo=keras)

## Project Overview
This project implements and compares two powerful deep learning architectures for **Image Denoising**:
1.  **Deep Denoising Autoencoder (DAE):** A deterministic model that learns to map noisy inputs back to clean images.
2.  **Variational Autoencoder (VAE):** A probabilistic generative model that learns the underlying distribution of the data.

The goal is to evaluate which architecture performs better at removing synthetic noise from handwritten digits (MNIST dataset).

## Architectures Implemented

### 1. Deep Denoising Autoencoder (DAE)
* **Mechanism:** Uses a stack of Convolutional layers to compress the noisy image into a latent space and then reconstruct it.
* **Input:** Images with added Gaussian noise.
* **Optimization:** Minimizes reconstruction error directly.

### 2. Variational Autoencoder (VAE)
* **Mechanism:** Encodes inputs into a probability distribution (mean and variance) in latent space, then samples from it to reconstruct the image.
* **Loss Function:** Combines reconstruction loss (MSE) with Kullback-Leibler (KL) divergence to regularize the latent space.

## Results & Comparison
Both models were trained on the MNIST dataset with artificially added noise. The performance was measured using **Mean Squared Error (MSE)** on the test set.

| Model Architecture | MSE Score | Conclusion |
| :--- | :--- | :--- |
| **Deep Autoencoder (DAE)** | **0.01070** | Superior reconstruction quality for this specific denoising task. |
| **Variational Autoencoder (VAE)** | 0.07581 | Produced blurrier outputs due to the probabilistic nature of the latent sampling. |

*(Note: Visual comparisons of the denoised images are available in the notebook.)*

## Tech Stack
* **Frameworks:** TensorFlow, Keras
* **Dataset:** MNIST
* **Core Concepts:** Encoder-Decoder, Latent Space, Sampling, KL Divergence

## How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/PyPro2024/MNIST-Image-Denoising-DAE-vs-VAE.git]
    ```
2.  **Install dependencies:**
    ```bash
    pip install tensorflow numpy matplotlib
    ```
3.  **Run the Notebook:**
    Open `DeNoisingAutoencoders.ipynb` to see the training process and the visual comparison of results.

---
*If you find this project helpful, feel free to ⭐ the repo!*
