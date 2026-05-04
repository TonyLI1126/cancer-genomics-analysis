# cancer-genomics-analysis
Multi-level genomic analysis of cancer risk using GWAS, Inverse-Variance Meta-Analysis, and VEGAS gene-based testing on 3,700+ SNPs

# Genomic Analysis of Cancer Risk: Multi-level Association Study 

**Context:** Master's Project in Mathematical Engineering and Biostatistics @ Université Paris Cité.  
**Language Note:** This project, including the final presentation and internal documentation, was originally conducted in **French**.

##  Project Summary
This project aims to identify genetic determinants of cancer risk by analyzing a dataset of **4,600 individuals** across two clinical centers. The study implements a comprehensive pipeline from raw SNP data to biological pathway interpretation.

##  Methodological Pipeline

### 1. SNP-level Association (GWAS)
*   **Method:** Logistic regression adjusted for Principal Components (stratification) and clinical covariates.
*   **Meta-Analysis:** Combined center-specific results using an **Inverse-Variance model** to maximize statistical power.
    *   *Formula:* $\beta_{combi} = \frac{w_1\beta_1 + w_2\beta_2}{w_1 + w_2}$ where $w_i = \frac{1}{se_i^2}$.

### 2. Gene-level Testing (VEGAS)
*   Accounted for **Linkage Disequilibrium (LD)** using the Versatile Gene-based Association Study (VEGAS) approach.
*   Implemented **Cholesky decomposition** ($\Sigma = CC^T$) to simulate the null distribution and estimate empirical p-values.

### 3. Pathway Enrichment Analysis
*   Conducted enrichment tests on 10 candidate pathways (e.g., DNA repair, xenobiotic metabolism) using **Fisher's Exact Test**..

---

## Key Findings
*   **Visualizations:** Produced Manhattan and QQ-plots to assess signal and inflation (available in the French presentation)..
*   **Results:** Identified top candidate genes such as **PARP2** and **AKR1C2** ($p < 0.05$ before correction).
*   **Critical Analysis:** Discussed the impact of multiple testing (Bonferroni) and sample size limitations on result robustness..

---

##  Repository Content
*   `genomic_analysis_pipeline.R`: R script for data processing and analysis.
*   `presentation/`: Final presentation slides (**FR**) including results and biological interpretation.
*   `docs/`: Original project guidelines and requirements (**FR**).
