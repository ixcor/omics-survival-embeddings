# Omics Survival Embeddings
[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)]()
[![PyTorch](https://img.shields.io/badge/PyTorch-2.x-red.svg)](https://pytorch.org/)
[![TabNet](https://img.shields.io/badge/TabNet-PyTorch-lightgrey.svg)](https://dreamquark.ai/tabnet/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Benchmarking different embedding methods for survival prediction on omics data.

## Overview
This project explores how various dimensionality reduction and embedding techniques affect survival analysis on omics datasets.  
We compared classical linear methods with nonlinear and deep-learning approaches and combined them with modern predictive models.

## Methods
- **Embeddings**: PCA, ICA, Factor Analysis, UMAP, VAE, AutoEncoder, MOFA, NMF, CP/Tucker Tensor, Scikit-Fusion
- **Models**: TabNet, CatBoost, Ridge Regression
- **Evaluation metrics**:  
  - Concordance index (C-index)  
  - Mean Absolute Percentage Error (MAPE)  

## Key Results
- Best combination: **UMAP + TabNet (C-index = 0.568, MAPE = 79.26)** without clinical features.
- VAE + TabNet (with clinical features) also performed well (C-index = 0.541, MAPE = 75.71).
- TabNet consistently outperformed other models across embeddings.
- Clinical features sometimes improved performance, but not universally.
- PLS + Ridge minimized MAPE but had poor C-index → not suitable for survival tasks.

## Installation
```bash
git clone https://github.com/KonNik88/omics-survival-embeddings.git
cd omics-survival-embeddings
pip install -r requirements.txt

## Usage

Open the Jupyter notebooks in notebooks/ to reproduce experiments and visualizations.
All embeddings and models are implemented with scikit-learn, PyTorch, and PyTabNet.

## Visualizations

We provide comparisons of embedding spaces (UMAP, AE, VAE) and model performance metrics in results/.