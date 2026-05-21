# Benchmarking scRNA-seq Downstream Analysis Under Variable Sparsity and Sequencing Depth

This repository contains the full methodology, simulation configurations, and evaluation workflows for the **CMML Mini-Project 3: Simulating single-cell RNA-seq data with scDesign3**. 

The project includes systematically simulated single-cell transcriptomic datasets with varying target cell proportions and sequencing dropouts using `scDesign3` (based on real PBMC 3K data) and subsequently benchmarked three mainstream downstream workflows: **Seurat (clustering)**, **SingleR (annotation)**, and **scran (marker detection)**.

---

##  Repository Structure

- `notebooks/`: Fully executed Jupyter Notebooks with cached outputs.
  - `01_Data_Simulation_and_Preprocessing.ipynb`: Establishes the copula probabilistic model via `scDesign3` and exports simulated Seurat Objects under different configurations.
  - `02_Downstream_Benchmarking.ipynb`: Evaluates and benchmarks `Seurat`, `SingleR`, and `scran` performance, outputting the metrics (DR, FPR, and Marker Recovery) and visual representations.
---

##  How to Review and Run

Both notebooks in `notebooks/` are uploaded with fully preserved, pre-rendered R outputs and ggplot figures. Clicking on the notebooks above will open them in GitHub’s interactive viewer.


## General Setup for Local Execution
If you wish to execute the notebooks locally, use an R-kernel-enabled Jupyter environment. Please install the required libraries:

```R
install.packages(c("Seurat", "tidyverse", "BiocManager"))
BiocManager::install(c("scDesign3", "SingleR", "scran", "SingleCellExperiment", "celldex"))
