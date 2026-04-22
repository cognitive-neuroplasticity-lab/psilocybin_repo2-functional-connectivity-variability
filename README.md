# Functional Connectivity Variability in the Psilocybin Dataset

A neuroimaging analysis project examining inter-individual variability in resting-state functional connectivity patterns within the OpenNeuro ds006072 psilocybin dataset.

This repository moves beyond dataset readiness into subject-level functional connectivity analysis using real imaging data, scalable workflows, and variability-focused interpretation.

---

## Project Aim

To test whether large-scale functional connectivity patterns differ meaningfully across individuals within the psilocybin precision functional mapping dataset, and to establish a scalable pipeline for future longitudinal and condition-based analyses.

---

## Dataset Used

* **Dataset:** Psilocybin Precision Functional Mapping
* **OpenNeuro ID:** ds006072
* **Population:** Healthy adults
* **Design:** Repeated-measures pharmacological neuroimaging study
* **Modalities Available:** Resting-state fMRI, Task fMRI, Structural MRI, Diffusion MRI

---

## Analytical Scope

This repository focuses on a proof-of-concept subset using:

* Three participants
* Resting-state fMRI
* One session / one run per participant
* Single-echo functional files
* Atlas-based connectivity estimation

---

## Why a Single-Echo Pipeline Was Used

Initial plans considered broader multi-echo ingestion across subjects and conditions. Inspection of raw file sizes showed that full multi-echo downloads were impractical within a cloud notebook environment.

A pragmatic pivot was therefore made to a single-echo pipeline that preserved the core scientific question: inter-individual variability in connectivity structure.

Future repositories may implement richer multi-echo or multi-session extensions.

---

## Methods

The repository used a lightweight and scalable workflow:

1. Select functional files from OpenNeuro S3 storage
2. Download files sequentially
3. Extract ROI time series using the Schaefer atlas
4. Compute subject-level correlation matrices
5. Standardise matrices for cross-subject comparison
6. Quantify and visualise variability across participants

---

## Main Findings

* Functional connectivity matrices were successfully generated from real imaging data
* Mean connectivity differed across subjects
* Connectivity profile similarity was low, indicating heterogeneity
* Cross-subject comparisons were feasible after matrix harmonisation
* The dataset is suitable for larger-scale variability analyses

---

## Repository Workflow

### Notebook 1 - Data Access and Sample Selection

Established data access, inspected file structure, and documented the pivot to a feasible ingestion strategy.

### Notebook 2 - Connectivity Matrix Construction

Built subject-level functional connectivity matrices from resting-state data.

### Notebook 3 - Variability Analysis

Compared connectivity structure across participants and quantified heterogeneity.

### Notebook 4 - Visual Overview

Created non-redundant interpretation figures and scaling roadmap visuals.

### Notebook 5 - Summary and Next Steps

Consolidated findings, limitations, and future directions.

---

## Limitations

* Proof-of-concept sample size (three subjects)
* Single session/run per participant
* Single-echo rather than full multi-echo integration
* Atlas-level summary rather than edge-wise modelling

---

## Future Directions

* Expand to all available participants
* Include multiple sessions and time points
* Compare acute vs post-acute states
* Link connectivity patterns to behavioural outcomes
* Evaluate preprocessing robustness

---

## Tools Used

* Python
* Pandas
* NumPy
* Nilearn
* Matplotlib
* Seaborn
* Google Colab

---

## Maintained By

Aditya Sundaray
