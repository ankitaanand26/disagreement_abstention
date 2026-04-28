# Disagreement-Based Selective Prediction for Group Robustness

This repository contains the implementation and experiments for our project on disagreement-based selective prediction, aimed at improving worst-group accuracy without requiring group annotations at training or inference time.

---

##  Course Information
**Course:** Topics in Deep Learning  

---

##  Overview

In this project, we propose a simple post-hoc abstention method based on **model disagreement**. We use two models with different training biases:

- An ERM (Empirical Risk Minimization) model trained on the full dataset  
- A class-balanced, last-layer retrained model (FL)

At inference time, we abstain on samples where the two models disagree.

### Key Idea
Instead of relying on confidence or entropy, we show that **disagreement captures structurally different failure patterns**, often aligning with samples that hurt worst-group accuracy the most.

---

##  Datasets

We evaluate our method on:

- **Waterbirds**
- **CelebA**
- **HAM10000**

These datasets are commonly used to study spurious correlations and subgroup robustness.

---

##  Method Summary

1. Train ERM model on full dataset  
2. Train FL model via last-layer retraining on class-balanced subset  
3. At test time:
   - Compute predictions from both models  
   - Abstain when predictions disagree  

---

##  Results

- Disagreement improves **worst-group accuracy (WGA)** at matched coverage  
- Outperforms entropy and confidence on datasets with strong spurious correlations  
- Shows that **which samples are removed matters more than how well errors are detected**

---

##  Reproducibility

All experiments were conducted using:

- **Google Colab**
- **Kaggle Notebooks**

As a result:

- Execution environments were **not fully standardized**
- Some runs may depend on session-specific settings (GPU availability, paths, etc.)

 **Reproducibility is limited**, and results may vary slightly across runs.

---


---

##  Requirements

Typical dependencies include:

- Python 3.x  
- PyTorch  
- NumPy  
- Pandas  
- Matplotlib  

(Exact versions may vary due to Colab/Kaggle environments)

---

##  Notes

- This project focuses on **post-hoc selective prediction**, not model retraining from scratch  
- Group labels are **not used during training or inference**, only optionally for evaluation  

---

##  Acknowledgements

This project was completed as part of the *Topics in Deep Learning* course.

---

