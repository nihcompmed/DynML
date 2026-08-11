# DynML: Dynamical System Machine Learning

## Overview

This repository contains the implementation of **DynML (Dynamical System Machine Learning)**, a multiplexed dynamical reservoir computing framework for nonlinear and biological time-series prediction.

DynML uses heterogeneous continuous-time chaotic systems, primarily Lorenz reservoirs, as fixed nonlinear dynamical feature maps. Input states are projected into the initial conditions of the reservoir ensemble, the reservoir evolves through its intrinsic dynamics, and a linear readout maps the final reservoir state to the target output.

The framework is evaluated on synthetic chaotic benchmarks and biological gene-expression datasets. In addition, the repository includes empirical finite-time Bowen–Dinaburg separated-orbit entropy analyses used to characterize reservoir dynamical richness under fixed-size controls.

This repository accompanies the manuscript:

**Empirical Separated-Orbit Entropy Correlates with the Predictive Power of Multiplexed Dynamical Reservoir Computing**

---

# Repository Organization

## Repository Structure
- `Chaotic timeseries/` – Benchmark systems (Lorenz, Rössler, double pendulum)
- `Drosophila/` – Spatiotemporal gene-expression prediction during Drosophila embryogenesis
- `Liver regeneration/` – Gene-expression dynamics during human liver regeneration
- `MNIST/` – Static high-dimensional classification using chaotic reservoirs

## Chaotic Time-Series Benchmarks

Folder:

- `Chaotic timeseries/`

This folder contains notebooks for the Rössler and double-pendulum benchmark systems, matched baseline and reservoir-ablation analyses, empirical separated-orbit entropy validation, and fixed-\(N\) reservoir-regime comparisons.

### Main-text Figures

| Notebook | Description | Output Figure |
| --- | --- | --- |
| `Fig_2(upper_pannel)_Lorenz_maps_rossler.ipynb` | DynML direct-transition prediction for the Rössler benchmark | Figure 2, upper panel |
| `Fig_2(lower_panel)_Lorenz_maps_double_pendulum.ipynb` | DynML direct-transition prediction for the double-pendulum benchmark | Figure 2, lower panel |
| `Fig_3_Rossler_reservoir_ablation.ipynb` | Matched baseline and reservoir-ablation comparison for the Rössler direct-transition benchmark | Figure 3 |
| `Fig_4_Lorenz_maps_double_pendulum-time.ipynb` | Reservoir-size scaling and computation-time analysis on the double-pendulum benchmark | Figure 4 |
| `Fig_5_benchmark_emperical_DB.ipynb` | Validation of the empirical Bowen–Dinaburg separated-orbit entropy estimate on maps with known entropy | Figure 5 |
| `Fig_6_SuppFig_S4_different_parameter_set_topological_entropy.ipynb` | Fixed-\(N\) reservoir-regime analysis and empirical separated-orbit entropy across Lorenz parameter regimes | Figure 6; Supplementary Figure S4 |

### Supplementary Figures

| Notebook | Description | Output Figure |
| --- | --- | --- |
| `SuppFig_S1_supplementary_figure_rossler_data.ipynb` | Representative post-transient Rössler trajectory and sampled transition timepoints | Supplementary Figure S1 |
| `SuppFig_S2_supplementary_figure_double_pendulum_data.ipynb` | Representative post-transient double-pendulum trajectory and sampled transition timepoints | Supplementary Figure S2 |
| `SuppFig_S3_DP_reservoir_ablation_variable_wise.ipynb` | Variable-wise double-pendulum matched baseline and reservoir-ablation analysis | Supplementary Figure S3 |

### Data Generation

| Notebook | Description |
| --- | --- |
| `generate_rossler_data_input_output_separate_files.ipynb` | Generates Rössler input-output files for direct sampled transition prediction |

---

## Drosophila Gene-Expression Prediction

Folder:

- `Drosophila/`

This folder contains data-preparation and DynML prediction notebooks for spatiotemporal gene-expression prediction in the Drosophila blastoderm.

DynML is evaluated on direct developmental gene-expression transitions using gene-expression features, spatial-coordinate features, and combined gene-expression plus spatial-coordinate features. The analysis includes both random cell-level validation and spatially blocked validation.

### Main-text Figures

| Notebook | Description | Output Figure |
| --- | --- | --- |
| `Fig_7_drosophila_DynML_prediction-spatial.ipynb` | DynML prediction across Drosophila developmental transitions under the random cell-level split | Figure 7 |
| `Fig_8_drosophila_DynML_prediction-spatial.ipynb` | Input-ablation and spatially blocked validation for Drosophila gene-expression prediction | Figure 8 |

### Data Preparation and Data Files

| File | Description |
| --- | --- |
| `drosophila_data_preparation.ipynb` | Prepares Drosophila gene-expression and spatial-coordinate data |
| `valid_genes_filtered.csv` | Filtered gene list used for the prediction task |
| `dmel-data-20140930.txt` | Drosophila gene-expression data |
| `dmel-data-20140204.txt` | Drosophila gene-expression data |
| `dmel-neighbors-20140930.txt` | Spatial-neighbor information |

---

## Human Liver-Regeneration Prediction

Folder:

- `Liver regeneration/`

This folder contains notebooks and data files for DynML prediction of human liver-regeneration gene-expression transitions.

The analysis includes within-patient synthetic-panel prediction and leave-one-patient-out validation. The leave-one-patient-out analysis evaluates patient-level generalization by generating training panels only from training patients and test panels only from the held-out patient.

### Main-text Figures

| Notebook | Description | Output Figure |
| --- | --- | --- |
| `liver_DynML_prediction_single_S_patient_1.ipynb` | Within-patient liver-regeneration prediction for Patient 1 | Figure 9 |
| `liver_DynML_prediction_single_S_patient_2.ipynb` | Within-patient liver-regeneration prediction for Patient 2 | Figure 9 |
| `liver_DynML_prediction_single_S_patient_11.ipynb` | Within-patient liver-regeneration prediction for Patient 11 | Figure 9 |
| `liver_DynML_prediction_single_S_patient_12.ipynb` | Within-patient liver-regeneration prediction for Patient 12 | Figure 9 |
| `Fig_10_liver_data_all_patients_LOPO_analysis.ipynb` | Leave-one-patient-out validation for human liver-regeneration transition prediction | Figure 10 |

### Supplementary Figures

| Notebook | Description | Output Figure |
| --- | --- | --- |
| `liver_DynML_prediction_single_S_patient_3.ipynb` | Within-patient prediction for Patient 3 | Supplementary Figure S5 |
| `liver_DynML_prediction_single_S_patient_4.ipynb` | Within-patient prediction for Patient 4 | Supplementary Figure S5 |
| `liver_DynML_prediction_single_S_patient_5.ipynb` | Within-patient prediction for Patient 5 | Supplementary Figure S5 |
| `liver_DynML_prediction_single_S_patient_6.ipynb` | Within-patient prediction for Patient 6 | Supplementary Figure S5 |
| `liver_DynML_prediction_single_S_patient_7.ipynb` | Within-patient prediction for Patient 7 | Supplementary Figure S5 |
| `liver_DynML_prediction_single_S_patient_8.ipynb` | Within-patient prediction for Patient 8 | Supplementary Figure S5 |
| `liver_DynML_prediction_single_S_patient_9.ipynb` | Within-patient prediction for Patient 9 | Supplementary Figure S5 |
| `liver_DynML_prediction_single_S_patient_10.ipynb` | Within-patient prediction for Patient 10 | Supplementary Figure S5 |

### Data Preparation and Data Files

| File | Description |
| --- | --- |
| `Data_preparation.ipynb` | Prepares liver-regeneration gene-expression panels |
| `cluster_dataPatients*.mat` | Patient-specific gene-cluster data files |
| `liver_data_for_dsrn_patient*.csv` | Patient-specific liver-regeneration input data |

---

## MNIST Proof-of-Concept

Folder:

- `MNIST/`

This folder contains a supplementary, noncompetitive proof-of-concept showing that DynML can also be instantiated with a Rössler-based reservoir for static high-dimensional classification.

This experiment is not intended as a competitive image-classification benchmark. It is included only to demonstrate that fixed chaotic reservoirs can generate useful nonlinear embeddings for static inputs.

### Supplementary Figure

| Notebook | Description | Output Figure |
| --- | --- | --- |
| `SuppFig_S6_Rossler_predicts_MNIST-i-b.ipynb` | MNIST digit classification using a Rössler reservoir-based DynML model | Supplementary Figure S6 |

### Output Files

| File | Description |
| --- | --- |
| `train_predictions_MNIST_rossler_i_b.csv` | Training-set prediction results |
| `test_predictions_MNIST_rossler_i_b.csv` | Test-set prediction results |
| `mnist_test_predictions_rossler_i_b_10.png` | Representative MNIST test predictions |
| `X_test_reservoir_rossler_10000i_b.npy` | Stored Rössler reservoir states for MNIST test data |

---

# Workflow

The typical workflow is:

1. Prepare the benchmark or biological dataset.
2. Construct direct temporal-transition input-output pairs.
3. Project input states into heterogeneous chaotic reservoirs.
4. Integrate the reservoir dynamics over a fixed time horizon.
5. Train a linear readout on reservoir states.
6. Evaluate direct-transition prediction on held-out data.
7. Compare DynML with persistence, direct ridge regression, random feature models, ESN baselines, and reservoir ablations where applicable.
8. Estimate empirical finite-time Bowen–Dinaburg separated-orbit entropy for reservoir-regime analysis.
9. Generate manuscript and supplementary figures using the corresponding notebooks.

---

# Features

- Multiplexed dynamical reservoir computing
- Heterogeneous Lorenz reservoir ensembles
- Direct temporal-transition prediction
- Empirical finite-time Bowen–Dinaburg separated-orbit entropy analysis
- Fixed-\(N\) reservoir-regime controls
- Matched baseline and reservoir-ablation comparisons
- Rössler and double-pendulum chaotic benchmark systems
- Drosophila developmental gene-expression prediction
- Spatially blocked validation and input-ablation controls
- Human liver-regeneration transition prediction
- Leave-one-patient-out biological validation
- Supplementary Rössler-reservoir MNIST proof-of-concept

---

# Datasets

Experiments were performed using:

- Synthetic Rössler trajectories
- Synthetic double-pendulum trajectories
- Drosophila blastoderm spatiotemporal gene-expression data
- Human liver-regeneration gene-expression data
- MNIST digit images for supplementary proof-of-concept analysis

Please obtain any external biological or image datasets from their original sources and organize them according to the paths used in the notebooks.

---

# Notes

- DynML is evaluated here in a direct-transition prediction setting, not as an autoregressive recursive rollout model.
- The empirical separated-orbit entropy analysis is a finite-time, finite-sample diagnostic and should not be interpreted as exact topological entropy.
- The MNIST experiment is included only as a supplementary proof-of-concept and is not intended as a competitive image-classification benchmark.
- `.DS_Store` files and `.ipynb_checkpoints/` folders are system-generated files and are not required for reproducing the analyses.