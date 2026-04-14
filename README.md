# Hardware Trojan Detection — Siamese Deep Learning

**Reimplementation of:** Nasr et al. (2024)  
*A Siamese deep learning framework for efficient hardware Trojan detection using power side-channel data*  
Scientific Reports. DOI: https://doi.org/10.1038/s41598-024-62744-2

**Course:** CEG 7900 — Trustworthy AI Hardware  
**Wright State University — Spring 2026**  
**Instructor:** Dr. Fathi Amsaad  

---

## Overview

This repository reimplements the Siamese neural network framework from Nasr et al. (2024)
for Hardware Trojan detection using power side-channel signals. We replicate the three
baseline architectures (CNN, GRU, LSTM) and extend the work with a fourth model —
a Bidirectional LSTM with an attention mechanism.

---

## Our Improvements Over the Paper

| Improvement | Description |
|---|---|
| Bidirectional LSTM | Reads power signal both forward and backward |
| Attention Mechanism | Learns which of the 2,500 timesteps matter most |
| Optimal Threshold Search | Tests 500 threshold values vs paper's fixed threshold |
| Batch Normalization | More stable training convergence |
| Early Stopping | Prevents overfitting automatically |
| Multi-Trojan Training | Uses T400+T500+T600+T700 datasets combined |

---

## Results

| Model | Paper Accuracy | Our Accuracy |
|---|---|---|
| Siamese CNN | 73.54% | TBD |
| Siamese GRU | 83.59% | TBD |
| Siamese LSTM | 86.78% | TBD |
| BiLSTM + Attention (ours) | N/A | TBD |

*Results will be updated after full multi-dataset training*

---

## Dataset

Hardware Trojan Power & EM Side-Channel Dataset — IEEE DataPort  
DOI: https://dx.doi.org/10.21227/9fwb-8978

Download and place these zip files in the same folder as the notebook:
- AES-T400_power_Temp25C.zip
- AES-T500_power_Temp25C.zip
- AES-T600_power_Temp25C.zip
- AES-T700_power_Temp25C.zip

---

## How to Run

### Option 1 — Google Colab (recommended)
1. Open `siamese_ht_detection.ipynb` in Google Colab
2. Enable T4 GPU: Runtime → Change runtime type → T4 GPU
3. Upload your dataset zip files
4. Run all cells: Runtime → Run all

### Option 2 — Local Jupyter
```bash
pip install -r requirements.txt
jupyter notebook siamese_ht_detection.ipynb
```

---

## Project Structure
