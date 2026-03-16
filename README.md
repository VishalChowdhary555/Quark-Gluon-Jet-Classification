# Quark-Gluon-Jet-Classification
Machine learning pipeline for classifying particle jets as quark- or gluon-initiated using simulated collider data. Implements feature engineering, Random Forest, XGBoost, and CNN-based jet image models with evaluation via ROC curves, AUC, and confusion matrices.

## Overview

This project builds a complete machine learning pipeline to classify particle jets as **quark-initiated** or **gluon-initiated** using simulated particle collision data.

Jets are sprays of particles produced in high-energy collisions such as those at the Large Hadron Collider (LHC). Distinguishing quark and gluon jets is an important problem in particle physics and has applications in jet substructure studies, precision measurements, and new physics searches.

This repository implements both **classical machine learning models** and **deep learning models** for jet classification.

---

## Dataset

The dataset used in this project is the **EnergyFlow Quark–Gluon Jets dataset**, generated using the **PYTHIA Monte Carlo event generator**.

Each jet contains particle-level information:
- transverse momentum (`pT`)
- rapidity (`y`)
- azimuthal angle (`phi`)
- particle ID (`PID`)

Labels:
- **1 = Quark jet**
- **0 = Gluon jet**

---

## Project Pipeline

The notebook performs the following steps:

1. Load simulated jet data
2. Preprocess particle-level jet information
3. Engineer physics-inspired jet features
4. Train baseline ML models:
   - Random Forest
   - XGBoost
5. Convert jets into jet images
6. Train a CNN on jet images
7. Evaluate models using:
   - Accuracy
   - ROC curve
   - AUC
   - Confusion matrices
8. Visualize feature distributions and feature importance

---

## Physics Motivation

In Quantum Chromodynamics (QCD), gluons carry a larger color factor than quarks. As a result:

- gluon jets tend to have **higher particle multiplicity**
- gluon jets are generally **broader**
- quark jets tend to be **narrower with harder cores**

The machine learning models learn these differences from jet observables and particle-level structure.

---

## Models Used

### Classical ML
- Random Forest
- XGBoost

### Deep Learning
- Convolutional Neural Network (CNN) on jet images

---

## Features Engineered

The following jet-level features are extracted:

- jet mass
- jet transverse momentum
- number of particles in the jet
- girth / angular spread
- pTD
- radial energy fractions
- constituent momentum statistics

---

## Evaluation Metrics

The models are evaluated using:

- Accuracy
- ROC Curve
- AUC Score
- Confusion Matrix
- Feature Importance

---

## Expected Performance

Typical results for this pipeline are in the following range:

| Model | Accuracy | AUC |
|------|------:|------:|
| Random Forest | 0.72–0.77 | 0.78–0.82 |
| XGBoost | 0.75–0.80 | 0.82–0.86 |
| CNN Jet Images | 0.79–0.85 | 0.86–0.90 |

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- TensorFlow / Keras
- EnergyFlow

---

## Future Improvements

Possible next steps:

- Graph Neural Networks for particle-level jets
- ParticleNet-style architectures
- comparison of PYTHIA vs HERWIG
- advanced jet substructure observables

---

## Author

**Vishal Chowdhary**
