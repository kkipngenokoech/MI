# Offline Decoding of Four-Class Motor Imagery EEG

This repository contains the code and analysis for the project **"Offline Decoding of Four-Class Motor Imagery EEG for Improved SMR-BCI Performance."** The project evaluates multiple decoding pipelines—ranging from classical feature engineering (CSP + LDA) to end-to-end Deep Learning (1D-CNN, EEGNet)—to improve the classification accuracy of a 4-class Sensorimotor Rhythm (SMR) Brain-Computer Interface.

## 🧠 Project Overview
* **Task:** 4-Class Motor Imagery (Left Hand, Right Hand, Both Hands [Up], Rest [Down]).
* **Data:** 68-channel EEG (27 used), sampled at 1000 Hz (downsampled for analysis).
* **Goal:** Surpass the baseline performance of the online linear decoder used during data collection.
* **Best Result:** The **1D-CNN** achieved **65.69%** accuracy, a statistically significant improvement over the online baseline (~50.9%).

## 📂 Repository Structure
The entire analysis is contained within a single Jupyter Notebook:

* **`MI.ipynb`**: This notebook performs the complete end-to-end pipeline:
    1.  **Data Loading:** Parses `.mat` files and extracts trial markers.
    2.  **Preprocessing:** Applies Bandpass filtering (8-30Hz), CAR, and Epoching (-2s to +2s).
    3.  **Label Mapping:** Maps Left/Right/Up/Down tasks to unique integer classes (0-3).
    4.  **Model Training:** Defines and trains 1D-CNN and EEGNet models using Keras/TensorFlow.
    5.  **Evaluation:** Runs 5-Fold Stratified Cross-Validation and generates Confusion Matrices.

## 🛠️ Requirements
To run the notebook, you will need Python 3.8+ and the following libraries:

```bash
pip install numpy scipy tensorflow scikit-learn matplotlib seaborn
