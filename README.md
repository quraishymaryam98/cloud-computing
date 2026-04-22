# ☁️ Cloud Computing Notebook

A **Google Colab notebook** that demonstrates core cloud computing concepts applied to data science and machine learning, using the classic Iris dataset as a practical example.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Notebook Structure](#notebook-structure)
- [Key Cloud Computing Concepts](#key-cloud-computing-concepts)
- [Requirements](#requirements)
- [How to Run](#how-to-run)

---

## Overview

This notebook walks through a complete ML workflow on a cloud VM — from system inspection and storage mounting to model training, evaluation, and deployment — while highlighting the cloud computing principles behind each step.

---

## Notebook Structure

### Cell 1 — System Information
- Checks the cloud VM's **CPU model** (Intel Xeon)
- Displays **RAM** (12GB total, ~11GB available)
- Shows **disk space** (108GB total, 88GB free)

### Cell 2 — GPU Check
- Attempts to detect GPU availability using `nvidia-smi`
- In this run, **no GPU was found** (runtime was not configured with GPU)
- GPU/TPU can be enabled via Colab's runtime settings

### Cell 3 — Google Drive Mounting
- Connects the Colab environment to **Google Drive**
- Mounts Drive at `/content/drive/MyDrive/`
- Enables direct reading and writing of files to cloud storage

### Cell 4 — Installing Libraries
- Installs [`yellowbrick`](https://www.scikit-yb.org/) — a machine learning visualization library
- Uses `pip install -q` for a quiet, minimal-output install

### Cells 5–6 — Loading and Exploring the Iris Dataset
- Loads the Iris dataset via `sklearn.datasets`
- Explores shape, feature names, and class labels
- Visualizes feature distributions and class separability

### Cells 7–8 — Preprocessing & Model Training
- Splits data into train/test sets using `random_state` for reproducibility
- Trains a **classifier** on the training split

### Cells 9–10 — Evaluation & Visualization
- Evaluates model accuracy on the test set
- Generates visualizations using `yellowbrick` (e.g., confusion matrix, classification report)

### Cell 11 — Model Deployment
- Saves the trained model to Google Drive using `joblib`
- Demonstrates cloud-based model persistence — the model can be loaded from anywhere

### Cell 12 — Prediction
- Makes a prediction on a new flower sample: `sepal: 5.1×3.5, petal: 1.4×0.2`
- Correctly identifies it as **setosa** with **100% confidence**

---

## Key Cloud Computing Concepts

| Concept | How It's Demonstrated |
|---|---|
| **Virtual Machine** | Colab provides a free cloud VM with CPU, RAM, and disk |
| **Cloud Storage** | Google Drive integration for persistent file storage |
| **Scalability** | GPU/TPU can be enabled in runtime settings |
| **Reproducibility** | `random_state` parameters ensure consistent results |
| **Model Deployment** | Model saved to cloud storage, loadable from anywhere |

---

## Requirements

```txt
scikit-learn
yellowbrick
joblib
google-colab
```

> All dependencies are available by default in Google Colab, except `yellowbrick` which is installed in Cell 4.

---

## How to Run

1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. *(Optional)* Enable GPU: **Runtime → Change runtime type → GPU**
3. Run all cells in order: **Runtime → Run all**
4. Authorize Google Drive mounting when prompted (Cell 3)

---

## 📁 Output Files

After running, the following file will be saved to your Google Drive:

- `MyDrive/cloud_computing_model.pkl` — trained classifier (joblib format)
