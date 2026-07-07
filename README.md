# PCA Classification Analysis

## Overview
This project applies Principal Component Analysis (PCA) to motion capture data in order to identify low-dimensional structure in high-dimensional joint coordinate measurements. After dimensionality reduction, a nearest centroid classifier is used to distinguish different types of human motion.

## Objective
The main goal of this project is to:
- reduce the dimensionality of motion capture data while preserving the dominant variance structure,
- visualize motion patterns in low-dimensional PCA space,
- evaluate whether the reduced representation supports accurate classification.

## Dataset
The dataset consists of motion capture sequences for three types of movement:
- walking
- jumping
- running

Each time snapshot is represented as a 114-dimensional vector of joint coordinates. Training snapshots are stacked and used to fit the PCA model, and both training and testing data are then projected into reduced PCA space.

## Methods
This project uses the following methods:
- **Principal Component Analysis (PCA)** via Singular Value Decomposition (SVD)
- **Cumulative explained variance** analysis
- **2D and 3D PCA visualization**
- **Nearest centroid classification**
- **Training and test accuracy evaluation** across different reduced dimensions \(k\)

## Key Results
- The cumulative energy increases rapidly with the first few PCA modes.
- Approximately:
  - 2 modes capture about 70% of the variance,
  - 3 modes capture about 80%,
  - 5 modes capture about 90%,
  - 7 modes capture about 95%.
- Low-dimensional projections show clear geometric separation among walking, jumping, and running classes.
- Classification accuracy improves substantially after dimensionality reduction.
- Test accuracy stabilizes around **95%** for moderate values of \(k\), showing that a relatively small number of principal components is sufficient for strong performance.

## My Contribution
I implemented the PCA-based dimensionality reduction workflow, analyzed explained variance, visualized motion trajectories in reduced space, and evaluated nearest centroid classification performance for different PCA dimensions.

## Files
- `HW2_Helper.ipynb` — project notebook with implementation
- `AMATH_482_project_2.pdf` — final project report
- `output_task1.png` — cumulative explained variance plot
- `output_task2a.png` — 2D PCA projection
- `output_task2b.png` — 3D PCA projection
- `output_task4.png` — training accuracy vs. number of PCA modes

## Skills Demonstrated
- Python
- NumPy
- scikit-learn
- PCA
- SVD
- Classification
- Data Visualization
- Dimensionality Reduction

## Conclusion
This project shows that PCA can effectively compress high-dimensional motion capture data while preserving the main structure needed for classification. The results demonstrate that low-dimensional representations can still achieve strong predictive performance, making PCA a useful tool for both visualization and machine learning workflows.
