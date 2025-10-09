# ML Model Evaluation and Optimization on SARS-CoV-2 Genomic Data 
---
### 🚀 Third Place Winner – CEB SOLE Biohackathon Track

---

## 📖 Introduction
This project was developed as part of the **CEB SOLE Biohackathon**, held in Egypt 🇪🇬.  
The original task was purely **Metagenomics analysis**, but on the day of the competition, we were surprised to find that the **Metagenomics Track** was merged with the **Artificial Intelligence (AI) Track)**.

That meant we had to design a complete **AI-based pipeline** to analyze genomic data and predict **Clades (genomic lineages)** using machine learning — all within the limited time of the hackathon!

As this was **my very first experience with AI and Machine Learning**, I relied heavily on **ChatGPT** as a learning and technical assistant — to understand the task, explore the data, and implement the required models step by step.

---

## 🎯 Project Objective
The main goal was to **predict the clade (genetic lineage)** of each genomic sample using features extracted from metagenomic data.  
We aimed to build an **accurate and efficient classification model** capable of generalizing to unseen genomic sequences.

---

## 🧠 Dataset Description
The dataset was provided by the competition organizers and consisted of three main files:

| File | Description | Purpose |
|------|--------------|----------|
| `train.csv` | Genomic samples with their corresponding `Clade` labels | Used for training the model |
| `val.csv` | Validation samples (not seen during training) | Used for performance evaluation |
| `test_features.csv` | Unlabeled genomic samples | Used for final prediction submission |

Each row represents a genomic sample, and each column represents numerical or derived **metagenomic features** (such as abundance ratios, diversity indices, or encoded genomic signatures).

---

## ⚙️ Workflow Overview

### 1️⃣ Data Preprocessing
- Checked for missing values and removed irrelevant columns (like IDs).  
- Encoded categorical columns (e.g., `Clade`) using `LabelEncoder`.  
- Ensured balanced representation of each clade using stratified sampling.

### 2️⃣ Data Splitting
- Training and validation sets were created with equal representation from all clades.  
- This ensured fair learning and avoided class imbalance.

### 3️⃣ Model Training
We experimented with multiple algorithms:

| Algorithm | Highlights | F1 Score | AUC-ROC |
|------------|-------------|-----------|----------|
| Random Forest | Simple, stable, and interpretable | 0.838 | 0.976 |
| XGBoost | Strong learner, good for tabular data | 0.854 | 0.981 |
| **LightGBM** | **Fastest and most accurate** | **0.857** | **0.9818** |

The **LightGBM model** achieved the best performance and was selected for the final submission.

### 4️⃣ Handling Class Imbalance
- Some clades had fewer samples.  
- We used **SMOTE (Synthetic Minority Oversampling Technique)** to oversample minority classes.  
- This improved model balance and reduced bias.

### 5️⃣ Model Evaluation
Performance metrics on the validation set:
- **Weighted F1 Score:** `0.857`  
- **AUC-ROC:** `0.9818`  

Both metrics indicated excellent generalization and robust classification.

### 6️⃣ Prediction on Test Data
- The final LightGBM model was applied to `test_features.csv`.  
- Generated predictions were stored as `test_predictions.csv` for submission.

---

## 🧬 Model Foundation & Research

The machine learning methodology in this project is inspired by published research from **Nile University, Egypt**, specifically the **GenoSig** framework.

> “Utilizing genomic signatures to gain insights into the dynamics of SARS‐CoV‐2 through Machine and Deep Learning techniques.”  
> *BMC Bioinformatics (2024)*  
> **[[Read the publication here](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-024-05648-2)]**

This research served as the **conceptual foundation** for representing genomic data through signature-based feature encoding, enabling machine learning models to identify genomic relationships and predict clades efficiently.

---

## 📊 Results Summary

| Model | F1 Score | AUC-ROC |
|--------|-----------|----------|
| Random Forest | 0.838 | 0.976 |
| XGBoost | 0.854 | 0.981 |
| **LightGBM** | **0.857** | **0.9818** |

✅ **LightGBM** provided the best trade-off between accuracy, training speed, and model interpretability.

---

## 🛠️ Tools and Technologies
- **Python 3.10+** 🐍  
- **Pandas & NumPy** – Data preprocessing and manipulation  
- **Scikit-learn** – Encoding, evaluation metrics, and SMOTE balancing  
- **LightGBM / XGBoost / RandomForest** – Model training  
- **Google Colab** – Execution environment  
- **ChatGPT** – AI assistant for understanding and writing code  

---

## 💬 Personal Reflection
> This project marked **my very first practical experience with Artificial Intelligence**.  
> When the track was suddenly merged with AI, it was an unexpected challenge — but also a great opportunity to explore how machine learning can empower bioinformatics research.  
> Using ChatGPT as a mentor, I managed to learn, design, and implement a full end-to-end AI pipeline from scratch.  
> It was a tough but inspiring experience that opened the door for me to integrate **AI into biological data science** in the future.  

---

## 🏆 Achievements
- Built a complete AI pipeline for genomic classification in less than 48 hours.  
- Achieved high accuracy and robust performance on validation and test datasets.  
- **Awarded Third Place** in the **CEB SOLE Biohackathon 2025** 🎉  

---

## 🔗 Resources
📓 Google Colab Notebook (Full Implementation):  

[`Metagenomics & AI Software Team 3.ipynb.ipynb`](Metagenomics & AI Software Team 3.ipynb.ipynb)


---

## 🙏 Acknowledgments
A big thank you to:
- **CEB SOLE organizers** for hosting such an inspiring biohackathon.  
- **Judges and mentors** for their valuable guidance and feedback.  
- **Nile University research team** for providing a foundational framework (GenoSig).  
- And to the **team members and participants** for creating a collaborative, educational, and innovative environment.

---

**Author:** *Mohamed Ahmed*  
📅 *CEB SOLE Biohackathon 2025 – AI & Metagenomics Track*  
