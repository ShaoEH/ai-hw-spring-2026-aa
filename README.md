# Assignment #7.1: Attack MNIST Recognition 🛡️

## 🎯 1. Project Objective
The goal of this assignment is to perform Adversarial Attacks on a trained Convolutional Neural Network (CNN) recognizing MNIST digits. I evaluate the model's vulnerability by generating imperceptible noise to fool the classifier using three different attack algorithms.

---

## 🏗️ 2. Base Model Setup
Before attacking, a base CNN model was trained to ensure high initial accuracy.
* **Architecture:** Convolutional Neural Network (MNISTConvNet).
* **Optimizer:** SGD (Learning Rate: 0.01, Momentum: 0.5).
* **Epochs:** 5.
* **Clean Accuracy:** **97.96%** (Accuracy on normal, unperturbed test data).

---

## ⚔️ 3. Attack Algorithms & Parameters
We applied three distinct adversarial attack methods:
1. **FGSM** (Fast Gradient Sign Method).
2. **PGD** (Projected Gradient Descent).
3. **MI-FGSM** (Momentum Iterative FGSM).

**Global Attack Parameters:**
* **Epsilon (Perturbation limit):** 0.9737 (Normalized).
* **Number of Steps (for PGD/MI-FGSM):** 20.
* **Momentum Decay (for MI-FGSM):** 1.0.

---

## 📊 4. Attack Results (Vulnerability Metrics)
The attacks were highly successful, causing the model's accuracy to plummet drastically. The Attack Success Rate (ASR) indicates the percentage of previously correct predictions that were successfully changed by the noise.

| Metric | Accuracy / Success Rate |
| :--- | :--- |
| **Clean Accuracy (Before Attack)** | **97.96%** |
| **FGSM Attack Success Rate** | **88.47%** |
| **PGD Attack Success Rate** | **99.54%** |
| **MI-FGSM Attack Success Rate** | **99.11%** |

*Insight: PGD and MI-FGSM were extremely effective, successfully fooling the model over 99% of the time.*

---

## 👀 5. Visual Demonstration
<img width="1122" height="833" alt="image" src="https://github.com/user-attachments/assets/4820cfc5-75e9-42c8-8ae5-3443db98f5d5" />


As seen in the visual results, the adversarial images (FGSM, PGD, MI-FGSM) look nearly identical to the original numbers to the human eye, but the added calculated noise causes the model to output completely incorrect predictions.
