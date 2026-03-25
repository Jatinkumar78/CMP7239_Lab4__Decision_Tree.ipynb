# 🚀 ANDROID MALWARE DETECTION SYSTEM

<p align="center">
  <img src="https://img.shields.io/github/stars/nishu2402/android-malware-detection-ml?style=for-the-badge&color=00f5ff"/>
  <img src="https://img.shields.io/github/forks/nishu2402/android-malware-detection-ml?style=for-the-badge&color=7209b7"/>
  <img src="https://img.shields.io/github/issues/nishu2402/android-malware-detection-ml?style=for-the-badge&color=ff4d4d"/>
  <img src="https://img.shields.io/github/license/nishu2402/android-malware-detection-ml?style=for-the-badge&color=00ffcc"/>
  <img src="https://img.shields.io/github/last-commit/nishu2402/android-malware-detection-ml?style=for-the-badge&color=72efdd"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9+-blue?style=for-the-badge&logo=python"/>
  <img src="https://img.shields.io/badge/XGBoost-Dominant-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/F1%20Score-98.47%25-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Dataset-Drebin-purple?style=for-the-badge"/>
</p>

## 📑 Table of Contents

- [👾 Authors](#-authors)
- [📌 Project Summary](#-project-summary)
- [🧠 Core Idea](#-core-idea)
- [📊 Dataset](#-dataset)
- [⚙️ Complete Pipeline](#️-complete-pipeline)
- [⚙️ Feature Selection Strategies](#️-dimensionality-reduction--feature-selection-strategies)
- [🤖 Models Explained](#-models-explained)
- [📏 Metrics](#-metrics)
- [🏆 Complete Performance](#-complete-performance)
- [🚀 Final Result](#-final-result)
- [📈 Why XGBoost Wins](#-why-xgboost-wins)
- [📂 Project Structure](#-project-structure)
- [💻 Installation](#-installation)
- [🔮 Future Roadmap](#-future-roadmap)
- [⚠️ Disclaimer](#️-disclaimer)

---

## 🛠️ Tech Stack

- Python  
- Pandas, NumPy, Scikit-learn, XGBoost  
- Matplotlib, Seaborn  
- Joblib  
- Cybersecurity + Machine Learning  

---

## 🎬 Quick Demo

<p align="center">
<img src="https://media.giphy.com/media/3o7TKsQ8UQkHhF5zCE/giphy.gif" width="600"/>
</p>

---


<p align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&height=300&color=0:020024,15:090979,30:3a0ca3,45:7209b7,60:00f5ff,75:00ffcc,90:72efdd,100:020024&text=ANDROID%20MALWARE%20DETECTION&fontSize=44&fontAlignY=38&fontColor=ffffff&animation=twinkling&desc=AI-Powered%20Static%20Malware%20Analysis%20Pipeline&descAlignY=65&descSize=20"/>
</p>

<p align="center">
<img src="https://readme-typing-svg.herokuapp.com?font=Orbitron&weight=700&size=28&duration=2600&pause=700&color=72EFDD&center=true&vCenter=true&width=1200&lines=Enterprise-Grade+Cybersecurity+Platform;Static+Analysis+%2B+Machine+Learning;High-Dimensional+Threat+Modeling;XGBoost+Dominant+Detection+Engine;98.47%25+F1-Score+%7C+Near-Perfect+ROC-AUC"/>
</p>

<p align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&height=6&color=0:00f5ff,25:7209b7,50:00ffcc,75:72efdd,100:00f5ff"/>
</p>

<p align="center">
<strong>
Enterprise-grade Android malware detection system using static API and permission analysis with machine learning.
</strong>
</p>

---

## 👾 Authors

### Nisarg Chasmawala (Shroff)

---

## 📌 PROJECT SUMMARY

This project implements a **high-performance Android malware detection system** using static analysis of:

- Permissions  
- API Calls  

It leverages **machine learning** to classify applications before execution.

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/716ada12-fc4c-4e62-822a-2266aba1b1f1" />

---

## 🧠 CORE IDEA

Traditional antivirus = Signature-based ❌  
This system = Behavior-based ML ✔  

👉 Detects unknown threats using patterns, not signatures.

---

## 📊 DATASET

- **Dataset:** `drebin-215-dataset-5560malware-9476-benign.csv`  
- **Source:** [link](https://www.kaggle.com/datasets/shashwatwork/android-malware-dataset-for-machine-learning?select=drebin-215-dataset-5560malware-9476-benign.csv)
- **Total Records:** 15,036  

- **Class Distribution:**  
  - Malware (S): 5,560 (37.0%)  
  - Benign (B): 9,476 (63.0%)  

- **Features:** 215 binary attributes representing Android permissions and API calls  

- **Target Variable:**  
  - Benign (B) → 0  
  - Malware (S) → 1

---

## ⚙️ COMPLETE PIPELINE

<img width="4014" height="8192" alt="DFD" src="https://github.com/user-attachments/assets/30b38f05-65b5-4596-be19-f8124ff69852" />

---

## ⚙️ Dimensionality Reduction & Feature Selection Strategies

To optimize model convergence and mitigate noise, the pipeline evaluates 4 distinct feature spaces:

* **`Baseline`**
  > The raw, unadulterated 215-feature dataset.
* **`Chi-Square`**
  > Statistical extraction isolating the top 150 features designed for binary data.
* **`Tree Importance`**
  > Algorithmic feature isolation utilizing a Random Forest selector.
* **`L1 Regularization`**
  > A strict Lasso penalization metric to identify only the absolute most critical behavioral indicators.

---

## 🤖 MODELS EXPLAINED

| Model | Strength |
|---|---|
| KNN | Simple & distance-based |
| LR | Interpretable baseline |
| RF | Handles non-linearity |
| XGBoost | Best performance |

---

## 📏 METRICS

- Accuracy  
- Precision  
- Recall  
- F1 Score  
- ROC-AUC
- Confusion Matrix

---

# 🏆 COMPLETE PERFORMANCE

## 🔹 Scenario A (215 Features)

| Model | Accuracy | Precision | Recall | F1 | ROC |
|---|---|---|---|---|---|
| KNN | 98.67 | 98.64 | 97.75 | 98.19 | 0.9971 |
| LR | 97.81 | 97.29 | 96.76 | 97.02 | 0.9960 |
| RF | 98.80 | 99.00 | 97.75 | 98.37 | 0.9989 |
| XGB | **98.87** | **98.82** | **98.11** | **98.47** | **0.9988** |

---

## 🔹 Scenario B (Chi-Square)

| Model | Accuracy | Precision | Recall | F1 | ROC |
|---|---|---|---|---|---|
| KNN | 98.47 | 98.19 | 97.66 | 97.93 | 0.9953 |
| LR | 97.61 | 97.27 | 96.22 | 96.75 | 0.9958 |
| RF | 98.64 | 98.73 | 97.57 | 98.15 | 0.9987 |
| XGB | **98.67** | **98.55** | **97.84** | **98.19** | **0.9987** |

---

## 🔹 Scenario C (RF Importance)

| Model | Accuracy | Precision | Recall | F1 | ROC |
|---|---|---|---|---|---|
| KNN | 98.54 | 98.28 | 97.75 | 98.02 | 0.9920 |
| LR | 96.01 | 95.42 | 93.71 | 94.56 | 0.9894 |
| RF | 98.44 | 98.54 | 97.21 | 97.87 | 0.9975 |
| XGB | **98.50** | **98.11** | **97.84** | **97.97** | **0.9980** |

---

## 🔹 Scenario D (L1)

| Model | Accuracy | Precision | Recall | F1 | ROC |
|---|---|---|---|---|---|
| KNN | 98.67 | 98.46 | 97.93 | 98.20 | 0.9959 |
| LR | 97.74 | 97.45 | 96.40 | 96.93 | 0.9963 |
| RF | 98.80 | 99.00 | 97.75 | 98.37 | 0.9985 |
| XGB | **98.84** | **98.47** | **98.38** | **98.43** | **0.9986** |

---

# 🚀 FINAL RESULT

🏆 Best Model → **XGBoost**  
📊 Best F1 → **98.47%**  
📐 Dimensionality Strategy: 1_Baseline_Maximum_Performance (215 independent variables)


---

## 📈 WHY XGBOOST WINS

- Handles tabular data perfectly  
- Captures non-linear patterns  
- Robust against overfitting  
- High precision + recall  

---

## 📂 PROJECT STRUCTURE

```
ANDROID_MALWARE_CLASSIFICATION_PIPELINE/
│
├── ANDROID_MALWARE_CLASSIFICATION_PIPELINE.ipynb
├── android_malware_classification_pipeline.py
├── drebin-215-dataset-5560malware-9476-benign.csv
│
└── saved_models/
    │
    ├── 0_MASTER_MODEL/
    │   └── Ultimate_Master_Pipeline.pkl  
    │
    ├── 1_Baseline_Maximum_Performance/
    │   ├── K-Nearest_Neighbors.pkl
    │   ├── Logistic_Regression.pkl
    │   ├── Random_Forest.pkl
    │   ├── XGBoost.pkl
    │   ├── scaler.pkl
    │   └── selected_features.pkl
    │
    ├── 2_Chi_Square_Top150/
    │   └── [Iteration Artifacts...]
    │
    ├── 3_RF_Importance/
    │   └── [Iteration Artifacts...]
    │
    └── 4_L1_Regularization/
        └── [Iteration Artifacts...]
```

---

## 💻 Installation

Clone the repository to your local machine:

```bash
git clone [[https://github.com/your-username/android-malware-classification.git](https://github.com/your-username/android-malware-classification.git)](https://github.com/nishu2402/android-malware-detection-ml.git)
cd android-malware-detection-ml
```

```
# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost joblib
```

## 🔮 FUTURE ROADMAP

- **Hybrid profiling**: Combine static + dynamic analysis for deeper threat detection  
- **Deep learning**: Use RNN/LSTM for sequential API behavior modeling  
- **Explainable AI**: Integrate SHAP/LIME for transparent predictions  
- **Adversarial defense**: Strengthen models against evasion techniques  
- **Edge deployment**: Enable lightweight on-device malware detection  
- **MLOps automation**: Continuous model retraining with new threat data  

---

## ⚠️ DISCLAIMER

For academic & research use only.
