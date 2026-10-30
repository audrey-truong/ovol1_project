# Ovol1 Transcriptomic & Co-Expression Analysis

This repository contains computational pipelines for analyzing *Ovol1*-related transcriptomic data, featuring differential expression profiling, functional enrichment, and weighted gene co-expression network analysis (WGCNA).

---

## 🌿 Repository Structure & Branches

The project is structured across multiple branches to separate core analyses from external GEO dataset processing and integration.

### `main` Branch
Contains the core analytical pipelines for primary datasets:
* **`DE_analysis.Rmd`**: Differential expression analysis workflow using `DESeq2`, functional gene set enrichment using `clusterProfiler`, and associated visualization scripts (volcano plots, heatmaps, PCA).
* **`WGCNA.Rmd`**: Weighted Gene Co-expression Network Analysis pipeline, including module detection, trait association, and module-specific functional enrichment.

### `geo_data` Branch
Houses workflows for external validation using Gene Expression Omnibus (GEO) datasets:
* **`GSE[Accession_Number]`**: Individual scripts and notebooks for preprocessing and analyzing specific GEO series (e.g., `GSEXXXXX.Rmd`).
* **Data Integration & Combination Tests**: Workflows detailing how to merge multiple expression cohorts, manage batch effects, and conduct cross-dataset statistical combination tests.

---

## 🛠️ Methodologies & Core Tools

* **Differential Expression**: [`DESeq2`](https://bioconductor.org/packages/release/bioc/html/DESeq2.html)
* **Co-Expression Networks**: [`WGCNA`](https://cran.r-project.org/web/packages/WGCNA/index.html)
* **Functional Enrichment**: [`clusterProfiler`](https://bioconductor.org/packages/release/bioc/html/clusterProfiler.html)
* **Visualization & Graphics**: `ggplot2`, `pheatmap`, and `ComplexHeatmap`

---

## 📦 Prerequisites & Installation

To run the R Markdown notebooks locally, ensure you have R (>= 4.0) installed along with the required CRAN and Bioconductor packages:

```R
# Install BiocManager if not already present
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

# Install core Bioconductor packages
BiocManager::install(c("DESeq2", "clusterProfiler", "WGCNA", "org.Mm.eg.db", "org.Hs.eg.db"))

# Install CRAN dependencies
install.packages(c("tidyverse", "ggplot2", "pheatmap", "RColorBrewer"))
```

---

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/ovol1-project.git
   cd ovol1-project
   ```

2. **Access primary pipelines (`main` branch):**
   Open `DE_analysis.Rmd` or `WGCNA.Rmd` in RStudio and execute the chunk workflows.

3. **Explore GEO datasets (`geo_data` branch):**
   ```bash
   git checkout geo_data
   ```
