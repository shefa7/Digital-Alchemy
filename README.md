This repository contains Digital-Alchemy Project(WiSe25/26) using WS22 Dataset

# Project Title: "Molecular Energy and Force Prediction using Message Passing Neural Networks"
## Overview
This project focuses on predicting **molecular energy** and **atomic force fields** using a deep
learning approach based on a **message passing neural network inspired by PaiNN**.
The model is trained on the **WS22 dataset**, which contains molecular conformations along
with quantum-mechanical energy and force values.
In addition to prediction, the project also analyzes **chemical behavior**, specifically the
**cis/trans isomer energy ordering**, to evaluate whether the model captures meaningful
molecular properties.
---
## Objectives
- Predict molecular **energy** from atomic structures
- Predict atomic **forces** using energy gradients
- Evaluate model performance using **MAE metrics**
- Analyze **cis/trans isomer energy differences**
- Visualize training behavior and prediction results
---
## Dataset
- Dataset: **WS22**
- Molecules used:
- Acrolein
- o-HBDI
- SMA
Each sample includes:
- Atomic numbers (Z)
- Atomic coordinates (R)
- Energy (E)
- Forces (F)
---
## Methodology
### Model
A **simplified PaiNN-inspired Message Passing Neural Network (MPNN)** is implemented.
Key components:
- Atom embedding layer
- Distance-based message passing
- Multiple interaction layers
- Energy prediction head
- Forces computed via gradients
---
### Training Setup
- Optimizer: Adam
- Learning rate: `1e-4`
- Batch size: `32`
- Epochs: `50`
- Scheduler: ReduceLROnPlateau
- Hardware: **Google Colab (T4 GPU)**
---
### Loss Function
Loss = Energy Loss + 0.1 × Force Loss
---
### Evaluation Metrics
- Energy MAE (normalized)
- Force MAE (normalized)
---
## Results
| Molecule | Energy MAE | Force MAE | Cis/Trans Correct |
|----------|-----------|-----------|-------------------|
| Acrolein | 4.5905 | 14.8968 | YES |
| o-HBDI | 0.7245 | 46.2523 | Maybe |
| SMA | 3.2064 | 24.8681 | YES |
---
## Visualizations
The project includes:
- Training vs Validation Loss curves
- Energy prediction plots
- Force parity plots
- Multi-molecule comparison graphs
---
## Key Findings
- The model performs **better for energy prediction** than force prediction
- Force prediction is more **complex and sensitive**
- The model successfully captures **cis/trans energy ordering** for some molecules
- Performance varies depending on **molecular complexity**
---
## Limitations
- Force prediction accuracy is lower than energy prediction
- Performance varies across molecules
- Simplified model (not fully equivariant)
- Sensitive to preprocessing (dihedral angle selection)
---
## Future Work
- Use advanced models (e.g., **DimeNet, GemNet, full PaiNN**)
- Improve force prediction accuracy
- Increase dataset size and diversity
- Improve feature engineering and preprocessing
---
## 🛠️ Tech Stack
- Python
- PyTorch
- NumPy
- Matplotlib
- RDKit
- Google Colab
---
