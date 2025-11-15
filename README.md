[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17618590.svg)](https://doi.org/10.5281/zenodo.17618590)

# M-TriX: Dynamic Balance Architecture  
A Hybrid-Causal Neural Architecture for Stability, Efficiency, and Interpretability

Official implementation of **M-TriX**, a CNN architecture built on the concept of *dynamic balance* between the identity path and the representation path.  
M-TriX introduces a transparent gating mechanism that produces **spatial p-maps**, enabling stability under noise and interpretable decision pathways.

---

## 🚀 Key Features  
- **Dynamic balance** between identity and representation  
- **Strong noise stability** under corruptions  
- **Collapse-resistant behavior** (dual failure modes)  
- **Transparent decision fields** (*p-maps*)  
- **Deterministic training** (fixed seeds)

---

## 🔬 Paper  
**M-TriX: A Hybrid-Causal Neural Architecture for Stability, Efficiency, and Interpretability**  
Zenodo DOI → https://zenodo.org/records/17615922  

PDF available here:  
👉 [`docs/M-TriX.pdf`](docs/M-TriX.pdf)

---

## 🧪 Reproducibility Code (v0.6.1)

This repository contains the exact implementation used to reproduce all results in the paper:

- Noise-Augmented Training  
- Reinforced Dual Collapse (Sweep Test)  
- Noise Robustness Test (Dense vs M-TriX)  
- Visual Proof: Clean p-map under corrupted input  

Reproducibility Notes:  
👉 [`docs/M-TriX.txt`](docs/M-TriX.txt)

Master Proof Notebook (full implementation):  
👉 [`docs/M-TriX.ipynb`](docs/M-TriX.ipynb)

---

## 📦 Requirements

The implementation works on:

- Python ≥ 3.10  
- TensorFlow ≥ 2.12  
- NumPy  
- Matplotlib  
- GPU recommended (T4, A100)

Install dependencies:

```bash
pip install tensorflow numpy matplotlib
```

---

## 📊 Architecture Overview (Equation Form)

M-TriX is defined by four core equations:

```math
y_{act} = ReLU(BN(Conv(x)))
```

```math
p(x) = \sigma(W * y_{act} + b)
```

```math
p_{final} = p(x)(1 - P_{min}) + P_{min}
```

```math
y = p_{final} \cdot f(x) + (1 - p_{final}) \cdot x
```

---

## 🧠 Why M-TriX Works (Intuition)

The architecture forces the network to “justify” every deviation from the identity path:  
p>0.5 means *“this region deserves transformation”*.  
p<0.5 means *“pass the identity, don’t trust the representation”*.  

This creates:

- Natural stability  
- Resistance to collapse  
- Interpretability (p-maps act like transparent logic gates)

---

## 📥 Citation

If you use M-TriX in research, please cite:

```
Alanazi, Mohammed M. (2025).  
M-TriX: A Hybrid-Causal Neural Architecture for Stability, Efficiency, and Interpretability.  
Zenodo. https://zenodo.org/records/17615922
```

---

## 📬 Contact  
Maintainer: **Mohammed M. Alanazi (MTMA)**  
For questions or collaboration: open an issue or reach out via GitHub.

---
