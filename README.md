# Bone Marrow Immune Landscape Profiling Using Single-Cell RNA Sequencing

## Project Overview
This project presents a complete single-cell RNA sequencing (scRNA-seq) workflow to characterize the **immune cell landscape of human bone marrow**.  
Using a combination of **Scanpy**, **CellTypist**, **decoupler’s ULM scoring**, and **marker gene–based annotation**, this pipeline performs preprocessing, clustering, cell-type identification, and functional profiling.

**Scientific Objective:**  
To identify and annotate immune cell populations in PBMC-like bone marrow samples using marker-based scoring, clustering, and functional profiling._

This analysis was performed inside a dedicated **Conda environment**, with all tools and the Jupyter Notebook installed directly inside that environment to ensure full reproducibility.



##  Tools & Technologies Used
| Category | Tools |

| Core scRNA-seq analysis | `scanpy`, `anndata` |
| Cell-type prediction | `CellTypist` |
| Regulatory & activity scoring | `decoupler` (ULM) |
| Graph/FA layout tools | `igraph`, `fa2-modified` |
| Visualization | `matplotlib`, `seaborn`, Scanpy plotting |
| Environment management | Conda |
| Notebook interface | Jupyter Notebook |

All tools were installed inside the Conda environment using:
```bash
pip install scanpy anndata decoupler celltypist igraph fa2-modified


##  **Conda Environment Setup**
Create and activate environment
conda create -n seq python=3.10
conda activate seq

Install all required tools
pip install scanpy anndata celltypist decoupler igraph fa2-modified

Launch the notebook
jupyter notebook

# **flowchart TD**
    A[Load Raw Matrix] --> B[Create AnnData Object]
    B --> C[QC Filtering<br>mito %, n_genes, n_counts]
    C --> D[Normalization & Log Transform]
    D --> E[Highly Variable Gene Selection]
    E --> F[Scaling & PCA]
    F --> G[Neighborhood Graph]
    G --> H[Clustering (Leiden)]
    H --> I[UMAP Embedding]
    I --> J[Cell Typing<br>- PanglaoDB markers<br>- CellTypist<br>- ULM scoring]
    J --> K[Differential Expression]
    K --> L[Functional Profiling<br>(Pathway Scores)]

