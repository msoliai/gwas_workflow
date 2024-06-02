# GWAS Workflow Example with PLINK

This repository provides a comprehensive workflow for conducting a genome-wide association study (GWAS) using sample data and the PLINK toolset. The workflow includes essential steps such as data inspection, quality control (QC), association testing, and visualization of results. Although PLINK is used for the GWAS, the output of the QC workflow portion can potentially be used as input for other GWAS methods.

This workflow is an adaptation of [Hailian Huang's GWAS tutorial](https://github.com/thehuanglab/gwas-tutorial/tree/master), tailored to provide a clear and practical understanding of conducting a GWAS with proper quality control and result interpretation.

## Prerequisites
- **PLINK**: A widely used toolset for GWAS and population genetics. Download it from [here](https://www.cog-genomics.org/plink2).
- **R**: A programming language and environment for statistical computing and graphics. Available [here](https://www.r-project.org).
- **'qqman' package in R**: For creating Manhattan and Q-Q plots for visualization of GWAS results. Install it using the command `install.packages("qqman")`.
- **renv**: An R package for managing project-specific environments. A `.lock` file is provided to ensure all required dependencies are installed.

## Workflow Overview
1. **Data Inspection**: Check the initial structure and content of the GWAS sample data.
2. **Conversion to Binary Files**: Convert the dataset to binary format for efficient processing.
3. **Missing Rate Calculation**: Identify and exclude SNPs and individuals with high missing rates.
4. **Heterozygosity Rate Calculation**: Detect and remove individuals with abnormal heterozygosity rates.
5. **Differential Missing Rate Test**: Exclude SNPs with significantly different missing rates between cases and controls.
6. **Hardy-Weinberg Equilibrium (HWE) Test**: Remove SNPs that deviate from HWE in controls.
7. **Linkage Disequilibrium (LD) Pruning**: Prune SNPs to remove those in high LD, reducing redundancy.
8. **Relatedness Check**: Identify and remove related individuals to ensure the independence of samples.
9. **Principal Component Analysis (PCA)**: Generate principal components to correct for population structure.
10. **GWAS**: Perform association testing to identify SNPs associated with the trait of interest.
11. **Visualization**: Create figures (e.g., Manhattan and Q-Q plots) to visualize the GWAS results.

Each step is demonstrated with corresponding commands and scripts to guide you through the entire process, from raw data to final results and visualizations. The goal is to provide a clear and practical understanding of conducting a GWAS with proper quality control and result interpretation. Users may need to make necessary adjustments with larger datasets.

## How to Use This Workflow
1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/msoliai/gwas_workflow.git
   cd gwas_workflow
   ```

2. Ensure that PLINK and R are installed on your machine. Follow the installation instructions on their respective websites.

3. Install the required R packages by initializing the environment with `renv`:
   ```R
   renv::restore()
   ```
4. Unzip Archive.zip in the data directory:
   ```
   unzip Archinve.zip -d data
   ```

5. Follow the steps in the provided Jupyter Notebook or R scripts to perform the GWAS workflow.

## Conclusion
This notebook provides a comprehensive guide to conducting a GWAS using sample data. By following the outlined steps, users can ensure high-quality data for their analysis and gain valuable insights from their GWAS results. Adjustments may be necessary when working with larger datasets or different GWAS methods.
