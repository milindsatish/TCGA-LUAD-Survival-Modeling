# TCGA-LUAD-Survival-Modeling
Survival modeling pipeline for TCGA Lung Adenocarcinoma (LUAD) using RNA-seq and clinical data. Includes univariate and multivariable Cox models, LASSO Cox feature selection, train/test validation, multi-gene risk scoring, Kaplan–Meier curves, forest plots, heatmaps, and model evaluation in R.
Lung Adenocarcinoma Survival Modeling with TCGA-LUAD (RNA-seq + Clinical Data)

A complete reproducible survival-analysis pipeline in R

This project builds a full end-to-end survival modeling workflow using TCGA Lung Adenocarcinoma (LUAD) RNA-seq gene expression and clinical outcomes. It demonstrates modern statistical genomics methods commonly used in translational oncology and precision-medicine research.

The analysis includes:
	•	Processing TCGA RNA-seq expression and survival data
	•	Univariate and multivariable Cox proportional hazards models
	•	LASSO Cox (glmnet) feature selection across 20 LUAD driver genes
	•	Train/test validation pipeline with C-index and KM curves
	•	Multi-gene risk-score modeling
	•	Kaplan–Meier survival curves
	•	Forest plots for hazard ratios
	•	Gene-expression heatmap ordered by risk
	•	LASSO coefficient barplot
	•	Score distribution plot
	•	Model calibration plot

All code is fully reproducible in R and provided in the .Rmd file.

⸻

🔬 Project Goals
	•	Identify LUAD driver genes associated with survival
	•	Use penalized Cox regression to build a sparse prognostic model
	•	Construct and evaluate a multi-gene risk score
	•	Validate performance in a held-out test set
	•	Produce publication-quality visualizations suitable for a research portfolio

⸻

📁 Repository Structure
├── LUAD_survival_pipeline.Rmd   # full analysis + narrative
├── data/                        # expression, survival, clinical files (not included)
├── figures/                     # automatically generated plots
│   ├── forest_20_genes_pub.png
│   ├── lasso_coefficients_barplot.png
│   ├── KM_test_lasso.png
│   ├── KM_multi_gene_score_tertiles.png
│   ├── score_distribution.png
│   ├── heatmap_genes20.png
│   └── calibration_test_lasso.png
└── README.md

📊 Key Methods & Results

Univariate Cox Regression Across 20 LUAD Genes

Hazard ratios were estimated for major LUAD drivers, both smoking-associated and non-smoking oncogenic drivers.

Plot included: forest_20_genes_pub.png

⸻

LASSO Cox Feature Selection (glmnet)

LASSO identified a sparse predictive subset of genes.
Positive β → increased risk.
Negative β → protective.

Plot included: lasso_coefficients_barplot.png

⸻

Train/Test Validation Pipeline (70/30 stratified)

The model was trained only on the training set using λ_min and evaluated on the test set.

Outputs include:
	•	Test-set Kaplan–Meier survival curve → KM_test_lasso.png
	•	Test-set C-index
	•	3-year calibration plot → calibration_test_lasso.png

⸻

Multi-Gene Risk Score Modeling

Risk score = Σ (β_i × expression_i), standardized as z-score and grouped into tertiles.

Plots included:
	•	KM by risk tertiles: KM_multi_gene_score_tertiles.png
	•	Score distribution: score_distribution.png
	•	Heatmap ordered by risk: heatmap_genes20.png

⸻

📦 Dependencies
tidyverse
data.table
survival
survminer
glmnet
broom
pheatmap

▶️ How to Run the Analysis
	1.	Download TCGA-LUAD RNA-seq and clinical data
	2.	Place the files in the data/ directory
	3.	Open LUAD_survival_pipeline.Rmd in RStudio
	4.	Knit to HTML (recommended)

All figures will automatically be saved to /figures.

⸻

✨ Why This Project Is Valuable

This project demonstrates:
	•	Practical experience with survival analysis
	•	Working with large-scale genomics datasets
	•	Implementing penalized Cox models (LASSO)
	•	Reproducible workflows via R Markdown
	•	High-quality scientific visualization

Strong for:

✔ Bioinformatics / computational biology job applications
✔ Genomics / cancer research labs
✔ Graduate or fellowship applications
✔ Data science portfolios

⸻

📝 License

This project is released under the MIT License, a permissive open-source license that allows reuse with attribution.
