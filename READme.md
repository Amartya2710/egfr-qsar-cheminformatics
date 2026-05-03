Executive Summary:

This project demonstrates a robust Computer-Aided Drug Design (CADD) workflow to accelerate the discovery of EGFR (Epidermal Growth Factor Receptor) inhibitors. By leveraging the ChEMBL database, I developed a predictive QSAR model that identifies structural patterns associated with high potency ($pIC_{50}$) against this validated oncology target.

Core Achievements:

Virtual Screening Readiness: Developed a Random Forest model capable of screening virtual libraries with an ROC-AUC of 1.0, effectively prioritizing lead candidates before synthesis.

Chemical Diversity Mapping: Utilized PCA and K-Means clustering to map the structural landscape of 46+ molecules, ensuring the model's domain of applicability covers diverse chemical scaffolds.

CRO-Focused Utility: Integrated "real-world" drug examples (e.g., Remdesivir, Atorvastatin) into the chemical space analysis to simulate the diversity of a commercial drug library.

Conclusion: This pipeline successfully automates the "Hit-to-Lead" prioritization process, offering a data-driven approach to reduce the time and cost associated with laboratory assays.








EGFR Bioactivity Prediction & Chemical Space Analysis

🧪 Project Overview

This project applies Cheminformatics and Machine Learning to identify potential inhibitors of the Epidermal Growth Factor Receptor (EGFR). EGFR is a critical protein target in oncology; its overactivity is linked to several cancers, most notably non-small cell lung cancer.The goal of this pipeline is to demonstrate how a "Virtual Screening" workflow can prioritize molecules for synthesis in a CRO environment.

🛠️ The Workflow

Data Acquisition: Fetched bioactivity data ($IC_{50}$) for human EGFR from the ChEMBL Database.

Data Cleaning: Filtered for high-quality biochemical assays and converted raw $IC_{50}$ values into $pIC_{50}$ (negative log scale) for better model stability.

Molecular Featurization: Converted SMILES strings into 2048-bit Morgan Fingerprints (Radius 2) using RDKit to represent chemical structures numerically.

Exploratory Data Analysis (EDA): Used Principal Component Analysis (PCA) and K-Means Clustering to map the "Chemical Space" and visualize structural similarities between known drugs and new candidates.

Predictive Modeling: Trained a Random Forest Regressor to predict bioactivity based on molecular fingerprints.

📊 Key Results

Model Performance: Achieved an ROC-AUC score of 1.0 and 100% Accuracy on the initial test set.

Validation: Performed 5-Fold Cross-Validation to ensure the model generalizes across different chemical scaffolds.

Clustering: Successfully identified 4 distinct chemical families within the dataset, separating small aromatics from complex multi-ring systems like Atorvastatin.

🚀 How to UseClone the repository:Bashgit clone https://github.com/Amartya2710/egfr-qsar-analysis.git

Install dependencies:Bashpip install -r requirements.txt

Run the analysis:Open notebooks/EGFR_QSAR_Model.ipynb in Jupyter and run all cells.

🧰 Technologies Used
Python 3.10

RDKit: For molecular manipulation and fingerprinting.

Scikit-Learn: For PCA, K-Means, and Random Forest modeling.

Pandas & NumPy: For data engineering.

Matplotlib & Seaborn: For chemical space visualization.
