# Seasonal Agriculture Performance Analysis

A Data Analytics project (VOIS AICTE Batch 2026-2027) analyzing how agricultural
performance — yield, resource use, and economic outcomes — varies across the three
Indian cropping seasons: **Kharif, Rabi and Zaid**.

## Problem Statement

Agricultural activities are influenced by seasonal variations in environmental
conditions, farming practices, resource availability and market conditions. This
project analyzes a farm-level dataset to identify meaningful seasonal patterns,
trends and differences in agricultural performance, and to turn them into
evidence-based insights and recommendations.

## Dataset

- **4,000 farm records** across **8 crops**, **8 states**, and **3 seasons**
- 28 columns covering environmental conditions (rainfall, temperature, humidity,
  sunlight, soil), resource usage (fertilizer, NPK, irrigation, water), and
  economic outcomes (cost, revenue, profit)
- Source file: `data/seasonal_agriculture_performance_dataset.csv`

> Note: the State–District pairing in this dataset does not correspond to real
> Indian geography, so `District` is treated only as a category label, not a
> validated location, in the analysis.

## Repository Structure

```
seasonal-agriculture-performance-analysis/
├── data/
│   └── seasonal_agriculture_performance_dataset.csv
├── notebooks/
│   └── seasonal_agriculture_analysis.ipynb
├── reports/
│   └── figures/                # exported chart images (.png)
├── ppt/
│   └── Seasonal_Agriculture_Performance_Analysis.pptx
├── requirements.txt
├── .gitignore
└── README.md
```

## Key Findings

| Finding | Supporting Analysis | Actual Value |
|---|---|---|
| Kharif is the most profitable season | Mean profit by season | ₹178,915 (Kharif) vs ₹87,689 (Rabi) vs -₹24,805 (Zaid) |
| Yield differs significantly by season, even after accounting for crop type | One-way ANOVA on crop-normalised yield | F = 127.4, p < 0.001 |
| Profit differs significantly across seasons | One-way ANOVA on profit | F = 34.3, p < 0.001 |
| Water efficiency is the strongest correlate of yield — far more than fertilizer or NPK | Pearson correlation vs yield | r = 0.92 (water efficiency) vs r ≈ 0.00–0.05 (fertilizer, N, P, K) |
| Nearly half of all farms operate at a loss, worsening in Zaid | % of farms with negative profit, by season | 49% overall — 42% (Kharif) → 51% (Rabi) → 64% (Zaid) |
| Drip irrigation is the most water-efficient method | Mean water efficiency & yield by irrigation method | 6.27 t/1000m³ (Drip) vs 3.44 (Flood), highest yield among methods |

## Tools Used

Python 3 · Pandas · NumPy · Matplotlib · Seaborn · SciPy · Jupyter Notebook

## How to Run

```bash
git clone https://github.com/<your-username>/seasonal-agriculture-performance-analysis.git
cd seasonal-agriculture-performance-analysis
pip install -r requirements.txt
jupyter notebook notebooks/seasonal_agriculture_analysis.ipynb
```

## Author

Siddhi Santosh Jagtap — Army Institute of Technology, Pune

VOIS AICTE Data Analytics Internship, Batch 2026-2027
