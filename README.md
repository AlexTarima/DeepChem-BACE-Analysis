# DeepChem-BACE-Analysis
Analysis of predictive methods to find active compounds on BACE-1 using a MoleculeNet dataset

Research Question: Which active-learning strategies are best at finding highly-active BACE-1 inhibitors using the fewest labeled molecules?

Dataset

Source: MoleculeNet BACE dataset, accessed through DeepChem
  1,513 molecules
  Molecular structures represented using SMILES
  Regression target: pIC50 (higher values indicate greater inhibitory potency)
  Molecular features: Extended-Connectivity Fingerprints (ECFP/Morgan)
  Dataset splitting: Scaffold-based training, validation, and test partitions
  Scaffold splitting is used to evaluate generalization across different molecular structural families, rather than relying on a random split that may place closely related compounds in both training and evaluation sets.
    Scaffold splitting results in an uneven train-validate-test split, and I may test other partition strategies. However, scaffold is recommended by DeepChem

Methodology

1. Data Preparation and Exploratory Analysis
  Inspected molecular structures and pIC50 labels.
  Validated SMILES representations using RDKit.
  Used canonical SMILES to investigate molecular duplicates.
  Examined the pIC50 distributions across dataset partitions.

2. Baseline Model: Random Forest Regression
   200 decision trees, random seed of 42
  MAE: 0.5286658106222579
  RMSE: 0.6661469511245
  R²: -0.7987722412794418
