# # Transcriptomic and Gene Length Analysis in Parkinson's Disease by Severity

This repository contains R scripts for RNA-seq and gene length analysis in differential expression studies related to Parkinson's Disease (PD).

## Description

Script Overview

1. 1_deseq2_analysis.R
Purpose: Load Salmon quantifications, perform normalization using DESeq2, and identify differentially expressed genes (DEGs) between sample groups (e.g., iPD vs. Control).

Key Steps:

Loads transcript-to-gene annotation and metadata
Performs length-scaled TPM normalization using tximport
Constructs DESeq2 object and adjusts for covariates (e.g., gender)
Runs DESeq2, filters and shrinks log fold changes
Outputs differential expression results (DE.xlsx)
2. 2_gsea_analysis.R

Key Steps:

Calculates gene-level statistics from p-values and log2FC
Maps Ensembl IDs to gene symbols using org.Hs.eg.db
Loads hallmark, KEGG, Reactome, WikiPathways, and GO gene sets
Performs GSEA using the fgsea package
Saves results for each gene set collection to Excel files
3. 3_gene_length_plotting_PD_severity.R

Key Steps:

Loads precomputed DE results and gene lengths
Merges gene length data with DEGs
Splits genes into up/downregulated sets
Comparing gene length distributions between:
   - Upregulated and downregulated genes (e.g., Wilcoxon, Shapiro)
Generates density plots of log10 gene length for each condition



## Requirements

### Software
- R (version 4.0 or higher)

### R Packages

-DESeq2, tximport, tidyverse, ggplot2, ggrepel, dplyr, readxl, readr, plyr
-fgsea, org.Hs.eg.db, AnnotationDbi, openxlsx, plyr, data.table


Install required packages with:
```R

install.packages(c("tidyverse", "ggplot2", "readxl", "openxlsx", "data.table", "plyr", "readr", "dplyr"))
BiocManager::install(c("DESeq2", "tximport", "fgsea", "org.Hs.eg.db", "AnnotationDbi"))


### File Structure

.
├── 1_deseq2_analysis.R
├── 2_gsea_analysis.R
├── 3_gene_length_plotting_PD_severity.R
├── 4_gene_length_plotting_PD_severity_alt.R
├── tx2gene_grch38_ens94.txt
├── metasummary.xlsx
├── GenelengthAll.xlsx
├── PDSeverityGroups/      # Contains DESeq2 results as .xlsx files
└── outputs/


PD_Severity_Analysis/
├── Data/
│   ├── GenelengthAll.xlsx          # Gene length reference data
│   └── PDSeverityGroups/           # DESeq2 results by patient group
├── Results/                        # Output figures and results
└── Scripts/
    └── PD_GeneLength_Analysis.R    # Main analysis script

### Output
DE.xlsx: Final DESeq2 results with Ensembl and gene symbols

GSEA_*.xlsx: GSEA results for each gene set collection

Density distributions of log10 gene lengths

Statistical comparisons between groups

Mean gene lengths with significance indicators


## License
This project is licensed under the MIT License.

## Contact
Principal Investigator
Pier Giorgio Mastroberardino, PhD
Email: piergiorgio.mastroberardino@univaq.it

## Affiliation
Department of Life, Health, and Environmental Sciences, University of L'Aquila, L'Aquila, Italy.

For scientific inquiries about this project, please contact Dr. Mastroberardino directly. For technical issues with the code, please open an issue in this repository.

Note: The metadata file is not included in this repository due to patient privacy concerns. These data can be requested from the PPMI website.
