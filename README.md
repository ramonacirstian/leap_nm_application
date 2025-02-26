# LEAP3 Normative Modeling Application
## Overview
This repository contains the analysis pipeline for applying normative modeling (NM) to fractional anisotropy (FA) data in autism, integrating clinical symptoms and polygenic scores (PGS). The study utilizes multiset canonical correlation analysis (msCCA) to uncover shared variance across white matter structure, behavioral symptoms, and genetic risk factors.

## Methods Summary
1. Diffusion Processing & Feature Extraction
	○ DTI and TBSS preprocessing were performed on diffusion MRI data.
	○ FA values were extracted from skeletonized white matter tracts using the JHU atlas (48 tracts), ensuring tract-based FA representation.
	○ The final features represent the mean FA values for each tract.
2. Applying Normative Models to FA
	○ Pre-trained normative models were applied to FA values from LEAP3 participants to compute Z-scores, capturing deviations from expected distributions.
	○ The dataset was split into 40% adaptation, 60% test to account for site effects.
	○ FA Z-scores were extracted for 48 white matter tracts using the JHU atlas.
3. Clinical and Genetic Data
	○ Symptoms: Selected behavioral measures including ADI-R, ADOS-2, SRS-2, ADHD scales, sensory processing scores, and depression/anxiety assessments.
	○ PGS: Seven polygenic scores were selected, including those for ASD, ADHD, intelligence, neuroticism, and schizophrenia.
4. msCCA Analysis
        ○ Multiset Canonical Correlation Analysis (msCCA) was used to identify latent dimensions linking FA, symptoms, and PGS.
	○ Regularization parameters were tuned to increase feature stability, particularly for FA.
	○ Selection probability was assessed to determine robust white matter tracts and genetic features associated with autism traits.
5. Permutation Testing for Statistical Significance
	○ A permutation test (n=1000) was conducted to evaluate whether observed canonical correlations exceeded chance-level associations.
	○ The null distribution was created by randomly permuting symptom data while keeping FA and PGS intact.

