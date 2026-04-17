# Histological Tissue Classification — CNN vs Logistic Regression

![Python](https://img.shields.io/badge/Python-3.x-blue) ![PyTorch](https://img.shields.io/badge/PyTorch-orange) ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-green)

## Overview
A deep learning project that classifies colorectal tissue types from histological images using a CNN, benchmarked against a logistic regression baseline. Built on a subset of the PathMNIST dataset.

## Dataset
- **Source:** PathMNIST (28×28 RGB histology patches)
- **Train / Test split:** 55,490 / 4,367 images
- **Classes:** Adipose · Lymphocytes · Normal colon mucosa · Cancer-associated stroma · Colorectal adenocarcinoma epithelium

## Models
- **Baseline:** Multinomial logistic regression (Scikit-learn) on flattened grayscale images — `67.2%` test accuracy
- **CNN:** Two conv layers + max-pooling + fully connected output, trained with PyTorch — `88.2%` test accuracy

## Results
- Best config: AdamW optimiser, lr = 0.001, 20 epochs
- CNN outperformed logistic regression by **21 percentage points**
- Minimal overfitting observed across training/validation loss curves

## Project structure
```
├── Histological Tissue Classification.ipynb   # Full pipeline: preprocessing, training, evaluation
```

## Setup
```bash
pip install numpy scikit-learn torch matplotlib
jupyter notebook Histological Tissue Classification.ipynb
```

## Reproducibility
Fixed seeds are set throughout: `np.random.seed(42)` and `torch.manual_seed(42)`.
