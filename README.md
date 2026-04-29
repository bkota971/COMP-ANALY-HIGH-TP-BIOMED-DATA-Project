# High-Throughput Biology – Final Project

**Author:** Bhanu Tejaswi Kota  
**Date:** 29 April 2026

---

## Languages, Tools, and Packages

**Language**  
- Python 3.12

**Packages**  
- pandas 2.3.3  
- numpy 2.0.2  
- scipy 1.16.3  
- scanpy 1.12.1  
- anndata 0.12.11  
- matplotlib 3.10.0  
- seaborn 0.13.2  

**Tools**  
- Google Colab  
- Jupyter Notebook  
- Scanpy

---

## Program Overview

This project performs an integrative transcriptomic analysis of Alzheimer’s disease using gene expression count data and single-nucleus RNA sequencing data.

The program performs the following tasks:

- Loads Alzheimer’s disease gene expression count data and metadata  
- Performs exploratory expression comparison between AD and control observations  
- Computes log2 fold changes and Welch’s t-test statistics  
- Identifies top upregulated and downregulated genes  
- Generates volcano plots and heatmaps  
- Loads a subset of the SEA-AD single-nucleus atlas  
- Identifies subtype-specific marker genes using Wilcoxon rank-sum testing  
- Generates marker gene dot plots  
- Integrates differential expression results with marker gene overlap analysis

---

## Inputs

- `GSE138852_counts.csv.gz`  
  Contains gene expression count matrix

- `GSE138852_covariates.csv.gz`  
  Contains metadata and condition labels

- `SEA-AD_Microglia-and-Immune_multi-regional_final-nuclei_AAIC-pre-release.2025-07-24.h5ad`  
  Single-nucleus RNA-seq dataset

- Exploratory subset used: 1,000 cells from SEA-AD atlas

---

## Outputs

- `deg_results.csv`  
  Differential expression results

- `final_deg_results.csv`  
  Ranked DEG results by significance

- `top_upregulated_genes.csv`  
  Top upregulated genes

- `top_downregulated_genes.csv`  
  Top downregulated genes

- `marker_genes.csv`  
  Marker genes for all cell subtypes

- `top_marker_genes.csv`  
  Top subtype marker genes

---

## Results Summary

- Expression matrix dimensions: 10,850 genes × 13,214 observations

### Key Results

- Upregulated genes include:
  - LINGO1  
  - NEAT1  
  - HSPA1A  
  - SPP1  
  - GFAP

- Downregulated genes include:
  - NRXN1  
  - SLC1A2  
  - LSAMP  
  - DPP10

- Differential expression patterns suggest:
  - Neuroinflammation  
  - Cellular stress responses  
  - Mitochondrial dysfunction

---

## Single-Nucleus Marker Analysis

- SEA-AD subset analyzed:
  - 1,000 cells  
  - 36,601 genes

### Major Cell Subtypes

- Micro-PVM_2  
- Micro-PVM_2_3-SEAAD  
- Micro-PVM_3-SEAAD  
- Micro-PVM_1  
- Lymphocyte

---

## Integration Analysis

### Key Result

- Top 50 AD-upregulated genes compared with subtype marker genes  
- 49 of 50 genes overlapped with marker genes

### Representative Overlap Genes

- FKBP5  
- NEAT1  
- SPP1  
- PSAP  
- MT-ND4  
- MT-CO3

### Biological Interpretation

Overlap signals suggest associations with:

- Neuroinflammation  
- Stress response pathways  
- Mitochondrial dysfunction  
- Micro-PVM-related cellular states

---

## Figures Generated

1. Top Upregulated Genes in AD  
2. Volcano Plot of Differential Expression  
3. Heatmap of Top Differentially Expressed Genes  
4. Dot Plot of Marker Genes Across Cell Subtypes

---

## Method Summary

1. Loaded and aligned count matrix with metadata  
2. Calculated mean expression and log2 fold changes  
3. Performed Welch’s t-tests for each gene  
4. Generated differential expression visualizations  
5. Loaded and subsetted SEA-AD single-cell dataset  
6. Identified marker genes using `rank_genes_groups` (Wilcoxon method)  
7. Generated subtype marker gene dot plots  
8. Performed overlap analysis between top AD genes and subtype markers  
9. Saved all outputs as CSV files

---

## Reproducibility Notes

- Run notebook cells in sequence  
- File paths assume Google Colab / Google Drive environment  
- Large count matrices may require increased memory  
- Results are exploratory and based on Welch’s t-test screening  
- False discovery rate correction was not applied  
- 1,000-cell subset was used for computational feasibility

---

## Package Versions

- Python 3.12  
- pandas 2.3.3  
- numpy 2.0.2  
- scipy 1.16.3  
- scanpy 1.12.1  
- anndata 0.12.11  
- matplotlib 3.10.0  
- seaborn 0.13.2

---

## References

Gabitto, M. I., et al. (2024). *Integrated multimodal cell atlas of Alzheimer’s disease.* Nature Neuroscience, 27(12), 2366–2383. https://doi.org/10.1038/s41593-024-01774-5

Mathys, H., et al. (2024). *Single-cell multiregion dissection of Alzheimer’s disease.* Nature, 632(8026), 174–185. https://doi.org/10.1038/s41586-024-07606-7

Gene Expression Omnibus. (n.d.). *GSE138852: Gene expression dataset for Alzheimer’s disease analysis.* National Center for Biotechnology Information. https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE138852

Seattle Alzheimer’s Disease Brain Cell Atlas Consortium. (n.d.). *SEA-AD atlas dataset.* Allen Institute for Brain Science. https://sea-ad.org

---

## Generative AI Disclosure

Generative AI tools were used for debugging.
