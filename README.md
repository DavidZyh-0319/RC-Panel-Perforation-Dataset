Release: RCSTL Ballistic Perforation Dataset

📌 Overview

This release publishes the comprehensive benchmark dataset used in our proposed Residual-Correction-based Simulation-augmented Transfer Learning (RCSTL) framework.

The dataset is specifically compiled to investigate the nonlinear dynamics of ogive-nosed projectiles perforating reinforced concrete (RC) panels. It serves as a robust empirical and simulation-driven foundation for developing predictive machine learning models in impact dynamics and terminal ballistics.

📊 Dataset Composition

The published dataset consists of 448 valid ballistic perforation samples divided into two distinct domains for transfer learning purposes:

1. Experimental Dataset (Target Domain)

Total Samples: 220 physical ballistic test records.

Sources: Compiled from 18 high-quality published experimental studies worldwide.

Scope: Encompasses a highly heterogeneous parameter space, ranging from small fragments (0.035 kg) to heavy penetrators (500 kg), and covering low, medium, and high-velocity regimes (202–1147 m/s).

Note: Multi-layer target tests have been decomposed into independent single-panel perforation samples based on the rigid-projectile assumption.

2. Simulation Dataset (Source Domain)

Total Samples: 228 numerical simulation cases.

Sources: Derived from 2 published LS-DYNA simulation studies.

Purpose: Specifically designed to fill the distributional gaps in the experimental data, notably extending coverage for thick targets and large obliquity angles.

🛠️ Feature Structure

Both datasets share a standardized schema consisting of 12 input features and 2 target responses.

Input Features (Predictors):

Projectile Geometry: Mass $M$ (kg), Diameter $d$ (mm), Length $L$ (mm), Caliber-Radius-Head ($CRH$), Length-to-Diameter ratio ($L/d$).

Projectile Material: Density $\rho_p$ (kg/m³), Casing Ultimate Strength $\sigma_u$ (MPa).

Target Properties: Concrete Compressive Strength $f_c$ (MPa), Target Thickness $T$ (mm).

Encounter Conditions: Initial Impact Velocity $V$ (m/s), Obliquity Angle $\theta$ (°), Angle of Attack $\alpha$ (°).

Output Variables (Prediction Targets):

Residual Velocity $V_r$ (m/s)

Attitude Angle $\delta$ (°)

💡 Usage Notes & Recommendations

Data Imbalance: Users should be aware that the experimental dataset exhibits natural skewness (e.g., clustered in small-caliber, low-thickness ranges). We highly recommend utilizing the provided simulation data via Transfer Learning (like our RCSTL framework) or Domain Adaptation techniques to improve model generalization.

Missing Values: While projectile geometries are fully recorded, certain response variables and encounter conditions (e.g., angle of attack) exhibit missing rates (~30-37%) in the experimental subset. Imputation or robust handling algorithms are required during preprocessing.

Cross-Validation: For benchmarking against our baseline, we recommend a 5-fold cross-validation scheme where the test set is strictly sampled from the Experimental Dataset to ensure fidelity to physical events.

📎 Attached Files

TargetDomain.xlsx - The 220 physical perforation samples.

SourceDomain.xlsx - The 228 LS-DYNA simulation samples.

data_dictionary.md - Detailed descriptions of units, bounds, and references.

For more methodological details, please refer to Chapter 2 of our accompanying paper/documentation.
