# Koopman-Quantum-Fusion

# Validating a Koopman-Quantum Hybrid Paradigm for Real-world Fusion Diagnostic Denoising

This repository contains the source code and experimental data for the paper **"Validating a Koopman-Quantum Hybrid Paradigm for Real-world Fusion Diagnostic Denoising"**.

The project implements a physics-informed quantum machine learning framework (Koopman-PQNN) to detect anomalies in tokamak fusion diagnostic data.

## File Descriptions

The repository is organized as follows:

### 1. Data Preprocessing
* **`data_processing.ipynb`**: The main data pipeline. It handles:
    * Loading raw diagnostic data from EAST tokamak.
    * Performing Koopman operator approximation (DMD-like approach).
    * Calculating reconstruction residuals.
    * Extracting the 6-dimensional statistical feature vectors (mean, variance, skewness, etc.) used for the quantum classifier.


### 2. Model Training & Benchmarks
* **`koopman_data_our.ipynb`**: Implementation of the proposed **Koopman-PQNN** (Parallel Quantum Neural Network). This notebook contains the quantum circuit design, variational training loop, and evaluation metrics.
* **`raw_data_cnn.ipynb`**: Implementation of the **Raw-Data CNN** baseline. This deep 1D CNN model is trained directly on high-dimensional raw time-series inputs, serving as the high-accuracy (but parameter-heavy) performance ceiling mentioned in the manuscript.
* **`koopman_data_cnn.ipynb`**: Implementation of the classical benchmark: **CNN on Koopman sequences**. This serves as a baseline to compare performance against the quantum model using the same linearized data.
* **`koopman_data_our_c.ipynb`**: Additional experimental scripts for the proposed framework (e.g., classical counterparts or ablation studies on Koopman features).

### 3. Visualization & Results
* **`Fig3.ipynb`**: Generates **Figure 3** of the manuscript (Training Loss and Test Accuracy comparison curves). It reads the training logs and produces the final plots.


## Requirements
* Python 3.8+
* PyTorch / TensorFlow (depending on your backend)
* PennyLane / Qiskit (for quantum circuit simulation)
* Scikit-learn, Numpy, Matplotlib

## Citation
If you find this code useful for your research, please cite our paper:
> [Insert your ArXiv or Journal citation here once available]
