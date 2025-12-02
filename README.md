# Portfolio Optimization with Frank-Wolfe Variants

This project compares several first-order optimization algorithms applied to the classical Markowitz portfolio optimization problem:

- Frank-Wolfe (FW)
- Away-Step Frank-Wolfe (AFW)
- Pairwise Frank-Wolfe (PFW)
- Projected Gradient (PG)

The goal is to evaluate convergence speed, efficiency, and the sparsity of the resulting portfolios.

---

## Problem Description

We solve the Markowitz mean–variance portfolio optimization problem.  
The objective is to:

- Minimize portfolio risk (variance)
- Maximize expected return
- Under the constraints:
  - The sum of asset weights equals 1  
  - No short-selling (weights must be ≥ 0)

This defines a convex optimization problem over the **unit simplex**, making it ideal for Frank-Wolfe–type algorithms.

---

##  Algorithms Compared

### **Frank-Wolfe (FW)**
Projection-free, simple to implement, but slower near boundaries.

### **Away-Step Frank-Wolfe (AFW)**
Adds "away steps" for faster convergence and better correction of bad vertices.

### **Pairwise Frank-Wolfe (PFW)**
Transfers weight between good and bad vertices, often the fastest variant.

### **Projected Gradient (PG)**
Uses gradient descent followed by projection onto the simplex; slower in practice.

---

##  Summary of Results

The algorithms were tested on four financial datasets: **FTSE100, NASDAQ100, DOW JONES, and S&P500**.

Key findings:

- **PFW and AFW are the fastest** (≈40–50 iterations, <0.01s runtime)
- **Projected Gradient is slowest** (often reaches 1000 iterations)
- **All methods reach similar optimal objective values**
- **PFW and AFW produce the sparsest portfolios** (4–5 assets selected)

Overall, PFW and AFW provide the best balance of speed, stability, and sparsity.

---

##  Datasets

The project uses real-world weekly return datasets from major market indices:

- FTSE100  
- NASDAQ100  
- DOW JONES  
- S&P500  

Source: *Bruni et al., 2015*.

---

## 🔧 Technologies Used

- Python  
- NumPy  
- SciPy  
- Matplotlib  

---

##  How to Run

Run the notebook or use:

```bash
python run_experiments.py
