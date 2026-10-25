# Unlocking Bacterial Resistance: A Comprehensive Bioinformatic and Data-Driven Investigation

This repository contains a comprehensive bioinformatics and data-driven machine learning pipeline designed to analyze antimicrobial resistance (AMR) patterns, process Minimum Inhibitory Concentration (MIC) data, and uncover hidden population structures in bacterial datasets (specifically focusing on *Neisseria gonorrhoeae* unitigs).

---

## Project Overview
Antimicrobial resistance (AMR) is a critical global health challenge. This project implements an end-to-end computational pipeline using Python to:
1. Fetch and process large-scale genomic and phenotypic datasets automatically via `kagglehub`.
2. Perform rigorous data cleaning, missing value imputation, and outlier management (IQR Capping).
3. Apply statistical transformations ($\log_2$ transformation of MIC values) and feature scaling.
4. Utilize unsupervised machine learning algorithms, including **Principal Component Analysis (PCA)** for dimensionality reduction and **K-Means Clustering** for grouping resistance profiles.
5. Generate high-resolution statistical visualizations, correlation heatmaps, and geographical resistance distributions.

---

## Tech Stack & Libraries
The pipeline is built using Python and relies on the following standard data science and bioinformatics libraries:
* **Data Manipulation & Numerical Analysis:** `pandas`, `numpy`, `scipy`
* **Machine Learning & Preprocessing:** `scikit-learn` (`StandardScaler`, `PCA`, `KMeans`)
* **Data Visualization:** `matplotlib`, `seaborn`
* **Dataset Management:** `kagglehub`

---

## Pipeline Workflow
1. **Dataset Loading:** Automatically downloads the `nwheeler443/gono-unitigs` dataset from Kaggle.
2. **Exploratory Data Analysis (EDA):** Inspects dimensions, missing attributes, and clinical metadata (3,786 samples and 31 features).
3. **Data Preprocessing & Cleaning:** Handles missing numerical values via median imputation and stabilizes variance using $\log_2$ transformations and IQR capping.
4. **Dimensionality Reduction & Clustering:** 
   * Determines the optimal number of clusters ($K$) using the **Elbow Method**.
   * Applies **PCA** to project high-dimensional resistance markers into 2D space.
   * Executes **K-Means** clustering to categorize resistance phenotypes.
5. **Visualization:** Plots correlation heatmaps for cross-resistance patterns and continental resistance category distributions.

---

## How to Run the Notebook
1. Clone this repository or download the `.ipynb` file.
2. Open the notebook in **Google Colab** or your local Jupyter environment.
3. Ensure you have the required libraries installed:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn kagglehub
