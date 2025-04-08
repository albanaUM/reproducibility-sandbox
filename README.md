# README
# Acute Myeloid Leukemia Heatmap Analysis

Analysis of RNA-seq data from acute myeloid leukemia samples using clustering heatmaps.

## Overview

This repository contains an analysis pipeline for visualizing gene expression patterns in acute myeloid leukemia (AML) samples. The analysis uses RNA-seq data from Shih et al., 2017 
, focusing on treatment responses in AML model mice.

## Dataset Description

* Source: [refine.bio](https://www.refine.bio/) experiment SRP070849
* Contains 19 AML model mouse samples
* Includes RNA-seq expression data with quantile normalization
* Samples represent different mutation types (IDH2, TET2) and treatments

## Dependencies

Required R packages:
```r
library(pheatmap)
library(magrittr)
library(readr)
library(dplyr)
library(tibble)
library(sessioninfo)
```

## Analysis Pipeline

The analysis follows these main steps:

1. Data organization and preprocessing
2. Gene expression matrix loading
3. Sample ordering synchronization
4. Variance-based gene selection
5. Clustering heatmap generation

## Directory Structure

```markdown
project_root/
??? data/
?   ??? SRP070849/
?       ??? SRP070849.tsv      # Expression data
?       ??? metadata_SRP070849.tsv  # Sample information
??? plots/
?   ??? aml_heatmap.png        # Generated heatmap
??? results/
    ??? top_90_var_genes.tsv   # Selected genes
```

## Key Features

* **Variance-based filtering**: Selects genes in upper quartile of variance
* **Treatment comparison**: Compares vehicle vs. treatment responses
* **Mutation status tracking**: Includes IDH2 and TET2 mutation information
* **Reproducible analysis**: Uses fixed random seed for clustering consistency

## Usage Instructions

1. Clone the repository
2. Create required directories using setup script
3. Download data files from refine.bio
4. Run analysis pipeline
5. Generate visualization

## Output Files

* `aml_heatmap.png`: Clustered heatmap showing expression patterns
* `top_90_var_genes.tsv`: List of selected high-variance genes
* Session information report for reproducibility tracking

## Citation Information

This analysis adapts methods from [refine.bio-examples](https://alexslemonade.github.io/refinebio-examples/03-rnaseq/clustering_rnaseq_01_heatmap.html) and uses data from Shih et al., 2017 
.