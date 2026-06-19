# Gene Expression Analysis in Breast Cancer
### Differential Expression + Machine Learning Classification using RNA-seq Data

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![R](https://img.shields.io/badge/R-4.3+-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## Overview

This project analyses publicly available RNA-seq gene expression data (GSE42568)
to identify differentially expressed genes between breast cancer and healthy tissue,
and builds a machine learning classifier to predict disease status from expression profiles.

**Skills demonstrated:** R/Bioconductor, DESeq2, Python, scikit-learn, data visualisation,
reproducible research, biological data interpretation.

## Biological Question

> Which genes are significantly up- or down-regulated in breast cancer compared to
> normal tissue, and can we use gene expression profiles to classify samples accurately?

## Dataset

- **Source:** NCBI Gene Expression Omnibus — [GSE42568](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE42568)
- **Samples:** 17 normal breast tissue + 121 primary breast tumour samples
- **Platform:** Affymetrix Human Genome U133 Plus 2.0 Array
- **Access:** Free, publicly available

## Methods

### 1. Differential Expression Analysis (R / DESeq2)
- Loaded and normalised raw count data using DESeq2
- Identified significantly differentially expressed genes (padj < 0.05, |log2FC| > 1)
- Visualised results with volcano plots and heatmaps

### 2. Machine Learning Classifier (Python / scikit-learn)
- Reduced dimensionality with PCA
- Trained and evaluated Logistic Regression and Random Forest classifiers
- Used 5-fold cross-validation to assess performance

## Results

| Model | Accuracy | AUC-ROC |
|-------|----------|---------|
| Logistic Regression | XX% | X.XX |
| Random Forest | XX% | X.XX |

*(fill in after running your analysis)*

**Top 10 upregulated genes:** *(fill in)*

**Top 10 downregulated genes:** *(fill in)*

## Repository Structure

```
├── data/
│   ├── raw/          # original GEO data (not uploaded — see download instructions)
│   └── processed/    # normalised count matrix
├── notebooks/
│   ├── 01_exploration.ipynb
│   ├── 02_differential_expression.Rmd
│   └── 03_ml_classifier.ipynb
├── scripts/
│   ├── deseq2_analysis.R
│   └── classifier.py
└── results/
    ├── figures/      # all plots
    └── tables/       # DE gene lists, model metrics
```

## How to Reproduce

### Requirements

**R packages:**
```r
BiocManager::install("DESeq2")
BiocManager::install("GEOquery")
install.packages(c("ggplot2", "pheatmap", "ggrepel", "dplyr"))
```

**Python packages:**
```
pip install -r requirements.txt
```

### Download the data

```r
# Run this in R to download the dataset automatically
library(GEOquery)
gse <- getGEO("GSE42568", GSEMatrix = TRUE)
```

### Run the analysis

1. Open `notebooks/02_differential_expression.Rmd` in RStudio and knit
2. Open `notebooks/03_ml_classifier.ipynb` in Jupyter and run all cells

## Key Visualisations

*(add screenshots of your volcano plot, heatmap, and PCA plot here once generated)*

## What I Learned

- How RNA-seq count data is structured and normalised
- Statistical methods for differential expression (Wald test, Benjamini-Hochberg correction)
- How to reduce high-dimensional biological data with PCA before ML
- The challenges of class imbalance in biological datasets

## About

Created during winter break 2026 as a self-directed bioinformatics project.  
BSc (Biochemistry & Molecular Biology / Data Science) — University of Sydney.

**Contact:** [klau0673@uni.sydney.edu.au] |[linkedin.com/in/kenny-lau-a41bbb3a9]
