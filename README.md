# Genotyping Data Quality Control Pipeline (GWASTools + SNPRelate)

A comprehensive R-based workflow for quality control (QC) of genotyping array data. The pipeline identifies and corrects inconsistencies, removes low-quality variants, and produces a high-confidence dataset for downstream genetic analyses.

---

## Overview

Genotyping arrays can contain technical artifacts, missing data, and annotation errors that bias downstream analyses. This workflow systematically evaluates sample quality, variant reliability, relatedness, and population structure to generate a robust dataset.

**Goals:**

- Perform QC on genotype and annotation data  
- Identify and correct sample-level inconsistencies  
- Filter low-quality SNPs using multiple criteria  
- Assess relatedness and pedigree structure  
- Evaluate population structure using PCA  

---

## Workflow

### 1. Data Exploration & Annotation
- Load genotype, SNP, and sample annotation data  
- Evaluate metadata:
  - Sample counts  
  - Family relationships  
  - Sex distribution  
  - Population groups  
  - Chromosome coverage  

### 2. Missingness Filtering
- Calculate SNP- and sample-level missingness  
- Remove SNPs exceeding thresholds  
- Verify sample completeness  

### 3. Sex Verification
- Compare reported sex with genotype-inferred sex  
- Use X/Y chromosome intensity and heterozygosity  
- Correct mislabeled samples  

### 4. BAF & LRR Analysis
- Examine allelic imbalance:
  - B allele frequency (BAF)  
  - Log R ratio (LRR)  
- Detect structural abnormalities:
  - Copy number variation (CNV)  
  - Loss of heterozygosity (LOH)  

### 5. Relatedness & Pedigree QC
- Estimate kinship using KING  
- Compare observed vs expected relationships  
- Identify:
  - Sample swaps  
  - Pedigree inconsistencies  
- Apply corrections to ensure data integrity  

### 6. Population Structure
- Perform LD pruning  
- Compute principal components  
- Visualize population clustering  

### 7. Duplicate Discordance
- Assess genotype consistency across duplicates  
- Identify unreliable SNPs based on discordance  
- Remove discordant variants  

### 8. Hardy-Weinberg Equilibrium (HWE)
- Test founder samples for HWE  
- Identify SNPs deviating from equilibrium  
- Filter variants based on statistical thresholds  

---

## Technologies

- R  
- GWASTools  
- SNPRelate  
- tidyverse  
- ggplot2  

---

## Key Features

- End-to-end genotype QC workflow  
- Multi-step filtering and validation  
- Pedigree and relatedness assessment  
- Population structure evaluation  
- Integration of statistical and biological QC metrics  

---

## Skills Demonstrated

- Genotype data quality control  
- Statistical filtering and validation  
- Population genetics analysis  
- Data cleaning and annotation management  
- Reproducible analysis using R  

---

## Notes

- QC steps are sequential to maintain data integrity  
- Multiple complementary metrics ensure robust filtering  
- Final dataset is suitable for downstream GWAS or other genetic analyses  

---

## Author

**Gagan Heda**
