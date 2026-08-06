# Robust Portfolio Construction using Ledoit-Wolf Shrinkage and Hierarchical Risk Parity

A quantitative finance project demonstrating how statistical and structural regularization techniques improve the stability, robustness, and real-world deployability of portfolio optimization.

This project investigates two complementary approaches:

- **Ledoit-Wolf Covariance Shrinkage** for reducing estimation error.
- **Hierarchical Risk Parity (HRP)** for topology-aware portfolio allocation without matrix inversion.

The study shows how these methods mitigate the shortcomings of classical Markowitz optimization under limited historical data.

---

## Motivation

Traditional Mean-Variance Optimization relies heavily on the sample covariance matrix.

When the number of observations is limited relative to the number of assets, covariance estimation becomes unstable, leading to:

- Ill-conditioned covariance matrices
- Extreme portfolio weights
- High turnover
- Poor out-of-sample performance

This project applies statistical and structural regularization techniques to build portfolios that are more suitable for practical investment management.

---

## Project Objectives

- Analyze instability in the sample covariance matrix
- Implement Ledoit-Wolf covariance shrinkage
- Construct portfolios using Hierarchical Risk Parity
- Compare HRP against classical Mean-Variance Optimization
- Evaluate portfolio robustness under stressed market conditions

---

## Dataset

- 12 NSE-listed stocks
- 48 months of historical log returns
- Multiple sectors including:
  - Information Technology
  - Banking
  - Metals
  - FMCG

---

## Methodology

### Part 1 — Statistical Regularization

Implemented:

- Sample Covariance Matrix
- Condition Number Analysis
- Bootstrap Stability Analysis
- Ledoit-Wolf Shrinkage (Oracle Approximating Shrinkage)

Key observations:

- Reduced covariance condition number
- More stable maximum Sharpe portfolios
- Lower concentration risk
- Improved numerical conditioning

---

### Part 2 — Structural Regularization

Implemented:

- Correlation Distance Matrix
- Hierarchical Clustering
- Dendrogram Construction
- Quasi-Diagonalization
- Recursive Bisection
- Hierarchical Risk Parity Allocation

HRP avoids direct covariance matrix inversion while allocating capital according to the hierarchical structure of asset correlations.

---

## Results

### Ledoit-Wolf Shrinkage

| Metric | Sample Covariance | Ledoit-Wolf |
|---------|------------------:|------------:|
| Condition Number | 20.6 | 8.9 |
| Shrinkage Intensity | — | 0.23 |
| Maximum Single Stock Weight | ~74% | ~42% |
| Bootstrap Weight Std. Dev. | ~17% | ~9% |

---

### HRP Performance

Compared with classical Minimum Variance Portfolio:

- ~53% lower portfolio turnover
- More stable allocations
- Better diversification
- Improved robustness under correlation shocks
- Lower transaction costs

---

## Stress Testing

A simulated banking-sector correlation shock was introduced to compare portfolio sensitivity.

Results showed:

- Mean-Variance Optimization produced concentrated allocation shifts.
- HRP distributed the impact smoothly across the portfolio.

This demonstrates the robustness of topology-aware portfolio construction.

---

## Visualizations

The project includes:

- Covariance Matrix Heatmaps
- Ledoit-Wolf Shrunk Covariance
- Hierarchical Clustering Dendrogram
- Portfolio Weight Comparison
- Banking Stress Test
- HRP vs MPT Allocation Analysis

---

## Technologies Used

- Python
- NumPy
- Pandas
- SciPy
- scikit-learn
- Matplotlib
- Seaborn

---

## Repository Structure

```
robust-portfolio-construction/
│
├── README.md
├── portfolio_construction.ipynb
├── report.pdf
├── requirements.txt
└── figures/
```

---

## Key Takeaways

- Covariance regularization significantly improves numerical stability.
- Ledoit-Wolf shrinkage reduces estimation error without discarding correlation structure.
- Hierarchical Risk Parity produces more stable allocations by respecting the natural hierarchy among assets.
- Regularization is essential for translating theoretical portfolio optimization into practical investment strategies.

---

## References

- Ledoit, O., & Wolf, M. (2004). A Well-Conditioned Estimator for Large-Dimensional Covariance Matrices.
- López de Prado, M. (2016). Building Diversified Portfolios that Outperform Out of Sample.
- Modern Portfolio Theory — Harry Markowitz.
