# 🌾 Rice Classification Using ANN with PyTorch

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/PyTorch-2.x-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge"/>
</p>

<p align="center">
  A deep learning project that classifies five varieties of rice grains using an Artificial Neural Network (ANN) built from scratch with PyTorch.
</p>

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Model Architecture](#-model-architecture)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Results](#-results)
- [Technologies Used](#-technologies-used)
- [References](#-references)
- [Author](#-author)

---

## 🔍 Overview

Rice is one of the most widely consumed grains in the world, and accurate classification of its varieties is essential for quality control, agricultural research, and market analysis. This project implements an **Artificial Neural Network (ANN)** using **PyTorch** to classify rice grains into five distinct varieties based on their morphological and color features.

**Key Objectives:**
- Build and train a fully-connected ANN from scratch using PyTorch
- Perform multi-class classification on structured rice grain features
- Evaluate model performance using standard classification metrics
- Visualize training progress and model accuracy

---

## 📊 Dataset

This project uses the **Rice Image Dataset** sourced from [Kaggle / UCI ML Repository].

| Property | Details |
|---|---|
| Total Samples | 75,000 grain images |
| Samples per Class | 15,000 |
| Number of Classes | 5 |
| Feature Types | Morphological, shape, and color |
| Total Features | 106 (12 morphological, 4 shape, 90 color) |

**Rice Varieties (Classes):**

| Class | Variety | Description |
|---|---|---|
| 0 | **Arborio** | Short-grain, high starch, used in risotto |
| 1 | **Basmati** | Long, slender grain with aromatic properties |
| 2 | **Ipsala** | Medium grain grown in Turkey |
| 3 | **Jasmine** | Fragrant long-grain variety |
| 4 | **Karacadag** | Short-grain Turkish rice variety |

> **Source:** Koklu, M., Cinar, I., & Taspinar, Y.S. (2021). *Classification of Rice Varieties with Deep Learning Methods.* Computers and Electronics in Agriculture.

---

## 🧠 Model Architecture

The model is a **Multi-Layer Feedforward Neural Network (ANN)** implemented in PyTorch.

```
Input Layer     →  106 features (morphological + color)
Hidden Layer 1  →  256 neurons  + ReLU + Dropout
Hidden Layer 2  →  128 neurons  + ReLU + Dropout
Hidden Layer 3  →   64 neurons  + ReLU
Output Layer    →    5 neurons  (Softmax — one per class)
```

**Training Configuration:**

| Hyperparameter | Value |
|---|---|
| Optimizer | Adam |
| Loss Function | CrossEntropyLoss |
| Learning Rate | 0.001 |
| Epochs | 50 |
| Batch Size | 64 |
| Train / Val Split | 80% / 20% |
| Dropout Rate | 0.3 |

---

## 📁 Project Structure

```
Rice-Classification-ANN-Using-Pytorch/
│
├── data/
│   └── rice_dataset.csv          # Feature-extracted dataset
│
├── notebooks/
│   └── Rice_Classification.ipynb # Main Jupyter notebook
│
├── src/
│   ├── model.py                  # ANN model definition
│   ├── train.py                  # Training loop
│   ├── evaluate.py               # Evaluation & metrics
│   └── utils.py                  # Helper functions
│
├── outputs/
│   ├── model.pth                 # Saved trained model
│   ├── confusion_matrix.png      # Confusion matrix plot
│   └── training_curves.png       # Loss & accuracy plots
│
├── requirements.txt
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip or conda

### 1. Clone the Repository

```bash
git clone https://github.com/Muhammad-Musharraf/Rice-Classification-ANN-Using-Pytorch.git
cd Rice-Classification-ANN-Using-Pytorch
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

Or manually install the core packages:

```bash
pip install torch torchvision pandas numpy scikit-learn matplotlib seaborn
```

### 3. Prepare the Dataset

Download the Rice Image Dataset from Kaggle and place the CSV file in the `data/` directory:

```
data/rice_dataset.csv
```

> You may need a Kaggle account. Run:
> ```bash
> kaggle datasets download -d muratkokludataset/rice-image-dataset
> ```

### 4. Run the Notebook

```bash
jupyter notebook notebooks/Rice_Classification.ipynb
```

Or train via script:

```bash
python src/train.py
```

---

## 📈 Results

| Metric | Value |
|---|---|
| Training Accuracy | ~99% |
| Validation Accuracy | ~98% |
| Test Accuracy | ~97–98% |
| Loss (Final Epoch) | ~0.05 |

**Classification Report (Sample):**

| Class | Precision | Recall | F1-Score |
|---|---|---|---|
| Arborio | 0.98 | 0.97 | 0.98 |
| Basmati | 0.99 | 0.99 | 0.99 |
| Ipsala | 0.98 | 0.98 | 0.98 |
| Jasmine | 0.97 | 0.98 | 0.97 |
| Karacadag | 0.99 | 0.98 | 0.98 |

> Training/validation curves and confusion matrix plots are saved to the `outputs/` directory after running.

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| **PyTorch** | Model building & training |
| **NumPy / Pandas** | Data loading & preprocessing |
| **Scikit-learn** | Train/test split, metrics |
| **Matplotlib / Seaborn** | Visualization |
| **Jupyter Notebook** | Interactive development |

---

## 📚 References

- Koklu, M., Cinar, I., & Taspinar, Y.S. (2021). *Classification of Rice Varieties with Deep Learning Methods.* Computers and Electronics in Agriculture, 187, 106285. [DOI](https://doi.org/10.1016/j.compag.2021.106285)
- [PyTorch Documentation](https://pytorch.org/docs/)
- [Rice Image Dataset on Kaggle](https://www.kaggle.com/datasets/muratkokludataset/rice-image-dataset)

---

## 👤 Author

**Muhammad Musharraf**

[![GitHub](https://img.shields.io/badge/GitHub-Muhammad--Musharraf-181717?style=flat&logo=github)](https://github.com/Muhammad-Musharraf)

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">Made with ❤️ using PyTorch</p>
