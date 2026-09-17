# TMP/SMX Resistance in E. coli Urinary Isolates: Association with Age and Clinical Setting

## Overview

This repository contains the full analysis for a study examining whether patient age group and clinical setting (inpatient vs. outpatient) are independently associated with trimethoprim/sulfamethoxazole (TMP/SMX) resistance among *Escherichia coli* urinary isolates. The analysis uses the **Antibiotic Resistance Microbiology Dataset (ARMD)**, a de-identified, EHR-derived antimicrobial resistance resource.

This is an original research project conducted end-to-end — from dataset exploration and cleaning through hypothesis testing, logistic regression, stratified analysis, and reporting. It's shared here as a portfolio piece demonstrating applied statistical analysis and reproducible reporting workflow (R, Quarto) on a real-world life-science dataset.

## Data Source

- **Dataset:** Antibiotic Resistance Microbiology Dataset (ARMD)
- **Citation:** Nateghi Haredasht et al., *Scientific Data*, 2025
- **Access:** [datadryad.org/dataset/doi:10.5061/dryad.jq2bvq8kp](https://datadryad.org/dataset/doi:10.5061/dryad.jq2bvq8kp)
- Raw data files are **not included** in this repository due to size/licensing; see the Dryad link above to download them directly.

## Research Question

Among E. coli urinary isolates, are patient age group and clinical setting independently associated with TMP/SMX resistance, and do age and clinical setting interact in their effect on resistance?

## Methods Summary

- **Outcome:** Non-susceptible (Resistant + Intermediate) vs. Susceptible to TMP/SMX
- **Predictors:** Age group (9 categories), clinical setting (`ordering_mode`: Inpatient/Outpatient)
- **Statistical approach:**
  - Chi-square tests for bivariate associations
  - Multivariable logistic regression (main effects)
  - Age × clinical setting interaction term (likelihood ratio test)
  - Age-stratified odds ratios by clinical setting
  - Variance Inflation Factor (VIF) check for multicollinearity
- **Tools:** R (tidyverse, gtsummary, ggplot2), Quarto for reproducible reporting

## Files 
- `TMPSMX_ARMD_analysis.qmd` — full reproducible analysis (R code + interpretation)
- `TMPSMX_ARMD_analysis.html` — rendered report ([view live report](https://sammerfatima.github.io/TMP-SMX-Resistance-in-E.-coli-Urinary-Isolates-Association-with-Age-and-Clinical-Setting/TMPSMX_ARMD_analysis.html)

## Key Findings

- 56,379 TMP/SMX susceptibility tests were analyzed; 28.2% were non-susceptible.
- Age group and clinical setting were both significantly associated with resistance (p < 0.001).
- The effect of age on resistance was concentrated among inpatients, peaking at 55–64 years (OR = 1.35, 95% CI 1.21–1.52), while outpatient resistance remained largely flat across age groups.
- A significant age × clinical setting interaction (p < 0.001) confirmed that age and setting do not act independently.
