# Mendelian-Randomization (MR)
Statistical method that uses genetic variants (Instrumental Variables) as proxies for environmental and lifestyle exposure to find evidence of causal inference between a risk factor and a disease

<p align="center">
  <img src="MR.png" width="400" height="300" alt="Alt Text">
</p>

**Assumptions of MR :**
1. The genetic variant is associated with the risk factor.
2. The effect of the genetic variant on the risk factor is independent of the confounding factors.
3. There are no direct pathways through which the genetic factor is directly related to the outcome being studied.

A genetic variant becomes an **Instrumental Variable (IV)** when all the above assumptions are satisfied. These IV's are used to study the causal relation between the risk factor and the outcome using MR methods.

## Pleiotropy 

It is a phenomenon where a single genetic variant influences multiple traits.
There are two types of pleiotropy:
1. **Vertical Pleiotropy**: This occurs when a genetic variant (SNP) influences one trait, which subsequently affects another trait along a downstream pathway to the outcome. However, it's important to note that it's not necessarily the SNP itself that influences the second trait, but rather the first trait affected by the SNP that influences the second trait.
2. **Horizontal Pleiotropy**: This occurs when a genetic variant affects the outcome through pathways independent of the risk factor. This violates assumption 3 of Mendelian Randomization, which assumes there are no direct pathways between the genetic variant and the outcome, except through the risk factor.
<br>
<p align="center">
  <img src="Schematic-of-different-types-of-pleiotropy-Previous-studies-distinguish-between-vertical.png" width="400" height="200" alt="Alt Text">
</p>

## Types of MR
There are two different types of Mendelian Randomization :

**One Sample MR**: This occurs when both the risk factor and the outcome are derived from the same sample population.

_Advantages :_
- Allows for direct assessment of the relationship between the genetic variant, risk factor, and outcome within the same population, minimizing potential biases introduced by population heterogeneity.

_Disadvantages :_
- Limited Generalizability: Findings may be specific to the population from which the data is derived, limiting the applicability of results to other populations.
- Susceptible to Population Stratification: Population stratification within a single sample can introduce bias if not properly accounted for, potentially confounding the relationship between the genetic variant, risk factor, and outcome.
<br>
<p align="center">
  <img src="One-sample-and-two-sample-Mendelian-randomization-study-designs-A-One-sample.png" width="400" height="200" alt="Alt Text">
</p>
<br>

**Two Sample MR**: In this scenario, the risk factor and the outcome are obtained from two separate sample populations.

_Advantages :_
- Offers the advantage of leveraging large-scale genetic data from different cohorts, potentially increasing statistical power and generalizability of findings across diverse populations. Additionally, it allows for validation of results across independent datasets, enhancing the robustness of the analysis.
  
_Disadvantages :_
- Potential for Bias: Differences in study design, measurement methods, and population characteristics between the two samples can introduce bias if not adequately controlled for, potentially impacting the validity of causal inference.
- Difficulty in Harmonization: Integrating data from different sources may pose challenges in standardizing variables, matching populations, and accounting for confounding factors, leading to methodological complexities and potential errors in analysis.



## Methods for MR

There are different classes of methods to run the MR analysis :

1. IVW-class ( Inverse variance weighted ) - efficient analysis method when all the genetic variants are valid IV's (Primary analysis) (eg:- IVW (fixed), IVW (random))
2. Outlier detection and removal - identify invalid IV's and remove them from the analysis (eg :- MR-PRESSO etc)
3. Model-based - probabilistic models to correct for different types of pleiotropy and mixture component models to charecterize valid and invalid signals (eg :- Egger, MR-APSS etc)
4. Outlier robust - mitigate the effects of invalid IV's (eg:- Weighted-median, Weighted-mode)

## References 

1. Sanderson E, Glymour MM, Holmes MV, Kang H, Morrison J, Munafò MR, Palmer T, Schooling CM, Wallace C, Zhao Q, Davey Smith G. Mendelian randomization. Nature Reviews Methods Primers. 2022 Feb 10;2(1):6. (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7614635/)
2. Hemani G, Bowden J, Davey Smith G. Evaluating the potential role of pleiotropy in Mendelian randomization studies. Human molecular genetics. 2018 Aug 1;27(R2):R195-208. (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6061876/)
3. Burgess S, Smith GD, Davies NM, Dudbridge F, Gill D, Glymour MM, Hartwig FP, Kutalik Z, Holmes MV, Minelli C, Morrison JV. Guidelines for performing Mendelian randomization investigations: update for summer 2023. Wellcome open research. 2019;4. (https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7384151/)
4. Hu X, Cai M, Xiao J, Wan X, Wang Z, Zhao H, Yang C. Benchmarking Mendelian Randomization methods for causal inference using genome-wide association study summary statistics. medRxiv. 2024:2024-01. (https://www.medrxiv.org/content/10.1101/2024.01.03.24300765v1)
5. Elsworth B, Lyon M, Alexander T, Liu Y, Matthews P, Hallett J, Bates P, Palmer T, Haberland V, Smith GD, Zheng J. The MRC IEU OpenGWAS data infrastructure. BioRxiv. 2020 Aug 10:2020-08. (https://gwas.mrcieu.ac.uk)
6. Hemani G, Zheng J, Elsworth B, Wade KH, Haberland V, Baird D, Laurin C, Burgess S, Bowden J, Langdon R, Tan VY. The MR-Base platform supports systematic causal inference across the human phenome. elife. 2018 May 30;7:e34408. (https://mrcieu.github.io/TwoSampleMR/authors.html)

