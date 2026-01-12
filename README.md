# RenalTransLSTM  
### Multi-Horizon Prediction of Acute Kidney Injury (AKI)

This repository contains the official implementation and experimental code for the paper:

> **RenalTransLSTM: Multi-Horizon Prediction of Acute Kidney Injury**  
> *S. M. Saiful Islam Badhon et al.*, 

The project focuses on early and reliable prediction of Acute Kidney Injury (AKI) using clinical time-series data by leveraging a hybrid **Transformer + LSTM** architecture and evaluating predictions across multiple future horizons.



## Abstract (Paper Summary)

Acute Kidney Injury (AKI) is a critical clinical condition associated with increased morbidity and mortality, particularly in hospitalized and ICU patients. Early prediction of AKI can significantly improve clinical decision-making and patient outcomes.

This work introduces **RenalTransLSTM**, a hybrid deep learning framework that integrates:

- Transformer-based attention mechanisms for capturing long-range temporal dependencies  
- LSTM networks for sequential modeling of physiological time-series data  

The model performs **multi-horizon prediction**, enabling AKI risk estimation at multiple future time points. Experimental results demonstrate that RenalTransLSTM consistently outperforms traditional machine learning models and standalone deep learning baselines across various prediction horizons.



## Repository Structure

aki-project  
- SVM/                - Support Vector Machine experiments  
- svm_xgboosting/     - SVM and XGBoost baselines  
- lstm/               - LSTM-based models  
- transformer/        - Transformer-only models  
- lstm-transformer/   - RenalTransLSTM and hybrid variants  
- tg_lstm/            - Time gated LSTM experiments  
- Scores/             - Evaluation plots and performance visualizations  
- .gitignore  
- README.md  



## Models Implemented

### Classical Machine Learning
- Support Vector Machine (SVM)  
- XGBoost  

### Deep Learning
- LSTM  
- Transformer  
- Time Gated LSTM (TG-LSTM)  
- **RenalTransLSTM (Transformer + LSTM) (Proposed Method)**  

All models are evaluated under identical preprocessing and feature settings to ensure fair comparison.



## Multi-Horizon AKI Prediction

RenalTransLSTM is designed to predict AKI risk at multiple future horizons, enabling proactive clinical intervention.

Typical prediction horizons include:

- Short-term prediction (6 Hours)  
- Mid-term prediction (12 Hours)  
- Long-term prediction (Up to 24 hours)  

The model leverages historical clinical measurements within a fixed observation window to generate horizon-specific risk estimates.



##  Evaluation Metrics

Model performance is assessed using standard clinical prediction metrics:

- Area Under the ROC Curve (AUROC)  
- Precision  
- Recall  
- F1-score  
- Confusion Matrix  
- Horizon-wise performance comparison  

Visualization scripts and plots are provided in the **Scores/** directory.



##  Data Description

Due to privacy and data-sharing restrictions, raw clinical datasets are **not included** in this repository.

- Experiments are conducted on structured clinical time-series data derived from ICU patient records  
- Large data files (e.g., `.npy`, raw features, intermediate tensors) are intentionally excluded  
- Feature engineering and preprocessing steps are implemented within the provided notebooks and scripts  

> ⚠️ **Important:**  
> Please ensure compliance with dataset usage agreements (e.g., MIMIC-III / MIMIC-IV) when reproducing experiments.


## Getting Started

### 1. Clone the repository
`git clone https://github.com/SaifulBadhon/aki-project.git`  
`cd aki-project`  

### 2. Create a virtual environment (recommended)
`python -m venv venv`  
`source venv/bin/activate`   (Linux / macOS)  
`venv\Scripts\activate`      (Windows)  

### 3. Install dependencies
`pip install -r requirements.txt`  
*(If `requirements.txt` is not available, generate one from your environment using `pip freeze > requirements.txt`.)*



##  Running Experiments

Each model directory contains scripts or Jupyter notebooks to train and evaluate models.

Example:

`python lstm-transformer/train_renaltranslstm.py`  

Or open notebooks directly:

`jupyter notebook`  

###  Reproducibility Notes
- Random seeds are fixed where applicable  
- Models are evaluated using identical train/validation/test splits  
- All reported results follow the experimental protocol described in the paper  



##  Author

**S. M. Saiful Islam Badhon**  
PhD Student, Information Science  
University of North Texas

