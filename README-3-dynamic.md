<div align="center">

# 🛡️ Adaptive Vulnerability Risk Scoring Framework

### Transitioning from Static CVSS to Dynamic, Data‑Driven Cyber Threat Assessment

<p>
  <img src="https://img.shields.io/badge/python-3.8%2B-blue.svg" alt="Python" />
  <img src="https://img.shields.io/badge/scikit--learn-1.6.1-orange.svg" alt="Scikit-Learn" />
  <img src="https://img.shields.io/badge/xgboost-latest-green.svg" alt="XGBoost" />
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License" />
</p>

<p>
  <a href="#overview"><img src="https://img.shields.io/badge/Project-Overview-0A66C2?style=for-the-badge" alt="Overview" /></a>
  <a href="#methodology-architecture"><img src="https://img.shields.io/badge/View-Architecture-6A5ACD?style=for-the-badge" alt="Architecture" /></a>
  <a href="#future-roadmap"><img src="https://img.shields.io/badge/Future-Roadmap-2E8B57?style=for-the-badge" alt="Roadmap" /></a>
</p>

</div>

---

<table>
<tr>
<td width="50%" valign="top">

## 📑 Table of Contents

1.  [Overview](#overview)
2.  [Authors](#authors)
3.  [Abstract](#abstract)
4.  [The Challenge](#the-challenge)
5.  [Proposed Solution](#proposed-solution)
6.  [Methodology & Architecture](#methodology-architecture)
7.  [Installation](#installation)
8.  [Using Pre-Trained Models](#using-pre-trained-models)
9.  [Project Structure](#project-structure)
10. [Future Roadmap](#future-roadmap)
11. [References](#references)
12. [License](#license)

</td>
<td width="50%" valign="top">

## 🚀 Quick Navigation

- [📌 Go to Overview](#overview)
- [👨‍💻 Go to Authors](#authors)
- [🧠 Go to Abstract](#abstract)
- [⚠️ Go to The Challenge](#the-challenge)
- [💡 Go to Proposed Solution](#proposed-solution)
- [⚙️ Go to Methodology & Architecture](#methodology-architecture)
- [💻 Go to Installation](#installation)
- [▶️ Go to Using Pre-Trained Models](#using-pre-trained-models)
- [📂 Go to Project Structure](#project-structure)
- [🚀 Go to Future Roadmap](#future-roadmap)
- [📚 Go to References](#references)
- [📜 Go to License](#license)

</td>
</tr>
</table>

---

## <a id="overview"></a>📌 Overview

> The **Adaptive Vulnerability Risk Scoring Framework** introduces a machine learning-based approach for evaluating cybersecurity risk using real network traffic features.
>
> Traditional vulnerability scoring systems such as **CVSS** provide standardized severity scores but often fail to reflect dynamic network behavior or environment-specific threats.
>
> This project bridges that gap by applying **supervised regression models** to convert contextual network data into **dynamic risk scores ranging from 0--10**.

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="authors"></a>👨‍💻 Authors

- **Nisarg Chasmawala (Shroff)**
- **Madhur Kadam**

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="abstract"></a>🧠 Abstract

> Traditional vulnerability scoring systems such as CVSS provide generalized severity ratings. While useful, they do not always reflect real-time network conditions or the local infrastructure context.
>
> This project introduces a **machine learning-driven risk scoring framework** that generates adaptive vulnerability scores using network traffic features. Instead of relying solely on static metrics, the system synthesizes contextual network data into a dynamic **0--10 risk scale** using regression algorithms.
>
> The framework demonstrates how AI-assisted security analytics can enhance vulnerability prioritization and threat response strategies.

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="the-challenge"></a>⚠️ The Challenge

Modern cyber threats evolve rapidly, and static global scoring models struggle to represent:

- Real-time network behavior
- Protocol-level activity
- Port-based attack vectors
- Active exploitation patterns

Traditional scoring systems provide **generic severity ratings**, which may not accurately reflect **actual operational risk**.

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="proposed-solution"></a>💡 Proposed Solution

This framework implements a **data-driven vulnerability scoring engine** that:

- Processes network traffic features
- Applies machine learning regression models
- Generates adaptive vulnerability risk scores
- Provides a numerical **risk value between 0 and 10**

The goal is to create a **dynamic and context-aware vulnerability assessment approach**.

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="methodology-architecture"></a>⚙️ Methodology & Architecture

<table>
<tr>
<td width="50%" valign="top">

### 1️⃣ Feature Engineering & Risk Synthesis

Network traffic features from **`cyberthreat.csv`** are weighted using a foundational risk equation to generate a normalized synthetic risk score.

### 2️⃣ Data Preprocessing

Categorical variables such as:

- Protocol
- TCP Flags
- Port Categories

are transformed using **One-Hot Encoding**.

</td>
<td width="50%" valign="top">

### 3️⃣ Model Training

Four regression models were trained:

- K-Nearest Neighbors Regressor
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor

### 4️⃣ Model Evaluation

Model performance is evaluated using:

- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R² Score

</td>
</tr>
</table>

<div align="center">

```mermaid
flowchart LR
    A[cyberthreat.csv] --> B[Feature Engineering & Risk Synthesis]
    B --> C[Data Preprocessing]
    C --> D[One-Hot Encoding]
    D --> E[Regression Models]
    E --> F[KNN Regressor]
    E --> G[Decision Tree Regressor]
    E --> H[Random Forest Regressor]
    E --> I[XGBoost Regressor]
    F --> J[Model Evaluation]
    G --> J
    H --> J
    I --> J
    J --> K[Dynamic Risk Score 0--10]
```

</div>

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="installation"></a>💻 Installation

Clone the repository and install required dependencies.

```bash
git clone https://github.com/nishu2402/adaptive-vulnerability-risk-scoring.git
cd adaptive-vulnerability-risk-scoring

pip install pandas numpy scikit-learn xgboost matplotlib seaborn joblib
```

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="using-pre-trained-models"></a>▶️ Using Pre-Trained Models

All trained models were serialized using **joblib** and can be loaded for inference.

```python
import joblib

knn_model = joblib.load("knn_model.pkl")
decision_tree_model = joblib.load("decision_tree_model.pkl")
random_forest_model = joblib.load("random_forest_model.pkl")
xgboost_model = joblib.load("xgboost_model.pkl")

# Example prediction
knn_predictions = knn_model.predict(X_new)
dt_predictions = knn_model.predict(X_new)
rf_predictions = knn_model.predict(X_new)
xgb_predictions = knn_model.predict(X_new)

print("KNN:", knn_predictions)
print("Decision Tree:", dt_predictions)
print("Random Forest:", rf_predictions)
print("XGBoost:", xgb_predictions)
```

Ensure that **X_new** follows the same preprocessing pipeline used during training.

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="project-structure"></a>📂 Project Structure

```text
adaptive-vulnerability-risk-scoring
│
├── cyberthreat.csv
│
├── saved models/
│   ├── knn_model.pkl
│   ├── decision_tree_model.pkl
│   ├── random_forest_model.pkl
│   └── xgboost_model.pkl
│
├── model_training.ipynb
│
├── risk_scoring_engine.py
│
└── README.md
```

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="future-roadmap"></a>🚀 Future Roadmap

Planned improvements for the framework:

- Reduce dummy variable redundancy using **drop_first=True**
- Integrate **SHAP** for explainable AI
- Align predictions with **CVSS 4.0 metrics**
- Implement **k-Fold Cross Validation**
- Build **REST API deployment**
- Add **real-time network traffic ingestion**

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="references"></a>📚 References

**Research Paper**  
Lim, J. and Muhammad, N., 2024.  
*Developing a New Feature for Vulnerability Risk Scoring Model for Enhanced Cybersecurity.*  
Journal of Statistical Modeling and Analytics (JOSMA), 6(2).

**Dataset Source**  
Zunxhi Samniea.  
Network Traffic Analysis Dataset for Cybersecurity.

Dataset Link:  
https://www.kaggle.com/datasets/zunxhisamniea/cyber-threat-data-for-new-malware-attacks

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>

---

## <a id="license"></a>📜 License

This project is licensed under the **MIT License**.

You are free to use, modify, and distribute this project with proper attribution.

<div align="right"><a href="#-table-of-contents">⬆ Back to top</a></div>
