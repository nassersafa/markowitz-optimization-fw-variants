# Semi-Supervised Learning: Optimization Methods Comparison

This project compares several optimization algorithms applied to a semi-supervised learning task using both synthetic data and the Breast Cancer Wisconsin dataset.

The goal is to predict labels for unlabeled data by minimizing a graph-based loss function and to evaluate how different optimization methods perform in terms of speed, stability, and accuracy.

---

##  Methods Implemented

- **Fixed Step Size Gradient Descent**
- **Lipschitz-Based Gradient Descent**
- **Armijo Rule Gradient Descent**
- **Block Coordinate Gradient Descent (Gauss–Southwell Rule)**
- **Coordinate Minimization**

---

## Summary of Findings

### Synthetic Data
- **Armijo Rule GD** → *best performer*: fastest and most stable  
- Fixed Step GD → fast but requires tuning  
- Lipschitz GD → very stable but slow  
- BCGD → steady but slow  
- Coordinate Minimization → efficient updates, moderate accuracy  

### Breast Cancer Dataset
| Method | Accuracy | Runtime |
|--------|----------|---------|
| Fixed Step GD | 81.6% | 81 s |
| **Armijo Rule GD** | **93.9%** | 38 s |
| BCGD (GS) | 84.4% | 350 s |
| Coordinate Min. | 67.5% | **3.8 s** |

**Armijo Rule GD gave the best overall performance** (highest accuracy + fast convergence).

---

##  Tools Used
Python, NumPy, SciPy, Matplotlib, scikit-learn

---

##  Group Members
Safa Lazzari  
Tommaso Ludergnani  
Nasser  
Brenno Movila  
