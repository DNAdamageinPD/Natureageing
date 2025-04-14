# # Gene Length Analysis in Parkinson's Disease by Severity

This repository contains R scripts for analyzing gene length distributions in differential expression studies related to Parkinson's Disease (PD).

## Description

This R script performs comparative analysis of gene lengths in Parkinson's disease patients classified by disease severity (mild vs severe) and timepoint (baseline vs V08), including:

1. Reading and processing gene length information from Excel files
2. Analyzing differential expression results from DESeq2 outputs.
3. Comparing gene length distributions between:
   - Upregulated and downregulated genes
4. Generating publication-quality figures and statistical reports

## Key Features

- Comparative analysis of gene lengths in differentially expressed genes
- Statistical testing including:
  - Shapiro-Wilk test for normality
  - Wilcoxon rank-sum test for group comparisons
- Visualization of log10 gene length distributions

## Requirements

### Software
- R (version 4.0 or higher)

### R Packages
- `readxl`
- `dplyr`
- `plyr`
- `readr`

Install required packages with:
```R
install.packages(c("readxl", "dplyr", "plyr", "readr"))

### File Structure

PD_Severity_Analysis/
├── Data/
│   ├── GenelengthAll.xlsx          # Gene length reference data
│   └── PDSeverityGroups/           # DESeq2 results by patient group
├── Results/                        # Output figures and results
└── Scripts/
    └── PD_GeneLength_Analysis.R    # Main analysis script

### Output
Output
The script generates high-resolution TIFF format plots (3500×3500 px, 600 dpi) showing:

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


