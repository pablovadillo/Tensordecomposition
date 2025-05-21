# Tensor Decomposition for Time-Resolved Immune Cell Sequencing in Cancer

This repository contains the full set of code, supplementary figures, and result files related to the master's thesis:

> **Tensor Decomposition for Time-Resolved Immune Cell Sequencing in Cancer**  
> *by Pablo Vadillo Berganza and Violant Moreno Creixell*  
> Master's Thesis in Mathematics – Chalmers University of Technology

The project applies tensor decomposition techniques—specifically CP, Tucker, and PARAFAC2—to time-resolved γδ T cell receptor sequencing data from sarcoma patients. The aim is to discover interpretable structure in the data and explore immunological dynamics through unsupervised methods.

Note: This code is written to work with the original data, which contains sensitive patient information and is not included here. For privacy reasons, this repository includes a modified version of the dataset. Users may need to adjust data paths, variable names, or preprocessing steps to match their own dataset structure.

---

## Repository Structure

The repository is organized as follows:

```
.
├── Clinical info_v2.2.xlsx           # Clinical metadata (e.g., treatment days, response)
├── Cluster_comparison.ipynb          # NMI-based cluster evaluation scripts
├── CP_decomposition.ipynb            # CP decomposition analysis
├── Dataset_exploration.ipynb         # Initial exploration of dataset and patient data
├── Data_visualization.ipynb          # Scripts for time-series and metric visualization
├── DIFFIT.xlsx                       # DIFIT results used for rank selection
├── Ground_truth_analysis.ipynb       # Matching clustering with known clinical labels
├── metrics_dict.pkl                  # Dictionary containing all calculated TCR metrics
├── nmi_comparison_all_tensors.csv    # Clustering comparison results
├── PARAFAC2.ipynb                    # PARAFAC2 decomposition code
├── rank_selection_results.pkl        # Precomputed rank selection outputs
├── README.md                         # Project description and documentation
├── Simulation.ipynb                  # Synthetic data generation 
├── TCR_metrics.ipynb                 # TCR diversity/clonality metric calculations
├── TCR_seq_new.xlsx                  # TCR sequencing count and frequency data (raw)
├── Tensor_construction.ipynb         # Tensor creation from raw counts
├── Tucker_clustering.ipynb           # Clustering on Tucker component space
├── Tucker_components.ipynb           # DIFIT, SVD and reconstruction error plots
├── Tucker_decomposition.ipynb        # Main Tucker decomposition pipeline
├── tucker_decompositions.pkl         # Decomposed tensor components for all datasets
│
├── real_data/                        # Real data tensors with centering preprocessing
│   ├── tensor_70.npy
│   ├── tensor_100.npy
│   ├── tensor_200.npy
│   ├── tensor_300.npy
│   └── parafac2_data.npy
│
├── simulated_data/                   # Simulated data tensors 
│   ├── tensor_1.npy
│   ├── tensor_2.npy
│   ├── tensor_3.npy
│   └── tensor_4.npy
│
└── Results/
    ├── Clust Comparison/             # NMI comparisons of clustering outputs
    ├── GT/                           # Ground truth clinical response figures
    ├── Data plots/                   # TCR sequences and metrics over time per patient
    ├── TCR metrics/
    │   ├── Change in metrics/        # Change in metrics before and after clinical outcomes
    │   ├── Clustering/               # Cluster comparisons in TCR metric space
    │   ├── Metric by cluster/        # Trajectories grouped by cluster
    │   └── Time evolution/           # Global metric progression over time
    ├── Tucker Clustering/
    │   ├── Real_data/
    │   ├── Sim_data/
    │   ├── All with labels/
    │   └── Pair-specific/
    ├── Tucker Components/            # Singular value spectra and reconstruction plots
    └── Tucker Decompositions/        # Core tensors and factor matrices per decomposition with different numbre of components
```

---

## Key Methods

- **Tensor Decomposition:** CP, Tucker, PARAFAC2
- **Clustering:** K-Medoids on factor matrices and immune metrics
- **Diversity Metrics:** Richness, Clonality, Shannon Entropy, Pielou Index, and more
- **Data Sources:** Time-resolved γδ TCR sequences from 13 sarcoma patients

---

## How to Explore the Results

Start in the `Results/` folder and browse by topic:

- **Tensor decompositions** → `Tucker Decompositions/` and `Tucker Components/`
- **Clustering results** → `Tucker Clustering/` or `TCR metrics/Clustering/`
- **Time-resolved immune metrics** → `TCR metrics/Time evolution/`
- **Raw patient TCR plots** → `Data plots/`
- **Ground truth comparisons (simulated data)** → `GT/`
- **Cluster comparison summaries** → `Clust Comparison/`

These figures complement the main thesis and are referenced throughout the appendix. For exact figure references, see the thesis document, specifically Appendix A.

---

## Citation

If you use this work, please cite:

```bibtex
@mastersthesis{vadillomoreno2025tensor,
  author = {Vadillo, Pablo and Moreno, Violant},
  title = {Tensor Decomposition for Time-Resolved Immune Cell Sequencing in Cancer},
  school = {Chalmers University of Technology},
  year = {2025}
}
```

