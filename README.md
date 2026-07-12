# Gene-Expression-Patterns-of-AMR-Plasmid-Transfer-Under-Tetracycline-Pressure-

## Overview

This project investigates the effects of tetracycline exposure on gene expression 
and conjugative plasmid transfer dynamics in a co-culture of *Salmonella enterica* 
and *Escherichia coli* over a 240-minute treatment period. RNA-seq data were analysed 
using a time-course design across four time points (0, 30, 90, and 240 minutes) to 
identify differentially expressed genes and assess the repeatability of gene expression 
measurements across conditions and time points.

Tetracycline resistance genes *tet(A)* and *tet(B)* were upregulated in response to 
antibiotic exposure, while conjugative transfer genes (*TraL*, *TraV*, *TraE*, *TraA*) 
showed dynamic temporal regulation — suggesting that antibiotic pressure acts as both 
a suppressor and promoter of plasmid transfer in a time-dependent manner.


## Dataset

- **Source:** NCBI Gene Expression Omnibus (GEO)
- **Accession:** GSE261094
- **Organism:** *Salmonella enterica* 452 (donor) + *Escherichia coli* J53 (recipient)
- **Design:** Tetracycline treatment (8 µg/mL) vs Control (PBS)
- **Time points:** 0, 30, 90, 240 minutes post-exposure
- **Replicates:** 3 biological replicates per condition

## Key Findings

- **9 genes** were differentially expressed overall in treatment vs control,
  including tetracycline resistance efflux pump genes *tet(A)* and *tet(B)*
- **Early response (0 min):** upregulation of *tet(A)*, *tet(B)*, relaxase and
  integrase; downregulation of conjugative transfer gene *TraL*
- **30 min:** upregulation of antitoxin genes *phd* and *vapB* suggesting
  cellular shift toward stability over conjugation
- **90 min:** reactivation of *tet(A)*; downregulation of *TraV*, *TraE*, *TraA*
- **240 min:** recovery phase — *TraL* upregulated, resistance genes no longer
  differentially expressed
- **Repeatability** ranged from 0.794 to 0.935 across all conditions,
  demonstrating high experimental consistency
- **Linear mixed-effects modelling** revealed significant time × treatment
  interaction in gene expression dynamics


## Repository Structure

```
.
├── Data
│   ├── Combined_count.xlsx
│   ├── GSE261094_Sal452_RNA_Seq_N.xlsx
│   ├── GSE261094_Sal452_RNA_Seq_T.xlsx
│   ├── Treatment_group.xlsx
│   └── sample_info.xlsx
├── Gene-Expression-Patterns-of-AMR-Plasmid-Transfer-Under-Tetracycline-Pressure-.Rproj
├── README.md
├── Result
│   ├── DEGs of TvC Timepoint comparison .png
│   ├── DEGs_control_vs_baseline.png
│   ├── QQ_plots.png
│   ├── Significant Genes Timepoint 0.png
│   ├── Significant Genes Timepoint 240.png
│   ├── Significant Genes Timepoint 30.png
│   ├── Significant Genes Timepoint 90.png
│   ├── heatmap_all_DEGs.png
│   ├── histogram_gene_expression.png
│   ├── mixed_model_summary.html
│   ├── mixed_model_summary.png
│   ├── mixed_model_time0_summary.html
│   ├── mixed_model_time0_summary.txt
│   ├── mixed_model_time240_summary.html
│   ├── mixed_model_time240_summary.txt
│   ├── mixed_model_time30_summary.html
│   ├── mixed_model_time30_summary.txt
│   ├── mixed_model_time90_summary.html
│   ├── mixed_model_time90_summary.txt
│   ├── predicated_count_TvC.png
│   ├── repeatability_barplot_Timpoints.png
│   ├── repeatability_barplot_TvC.png
│   ├── repeatability_overall.png
│   ├── repeatibility_control.png
│   ├── repeatibility_treatment.png
│   ├── sig_genes_0.xlsx
│   ├── sig_genes_240.xlsx
│   ├── sig_genes_30.xlsx
│   ├── sig_genes_90.xlsx
│   ├── sig_genes_name_0.xlsx
│   ├── sig_genes_name_240.xlsx
│   ├── sig_genes_name_30.xlsx
│   ├── sig_genes_name_90.xlsx
│   ├── venn_DEGs_T240_vs_C240v0.png
│   ├── venn_DEGs_T30_vs_C30v0.png
│   ├── venn_DEGs_T90_vs_C90v0.png
│   ├── venn_timepoints_Control_DEGs.png
│   ├── venn_timepoints_TvC_DEGs.png
│   └── volcano_plot_DEGs.png
├── antimicrobial_dataset.R
├── antimicrobial_dataset.Rmd
├── antimicrobial_dataset.html

```

## Requirements

**R version:** 4.3.1 or higher

**Install required packages:**

```r
# CRAN packages
install.packages(c("ggplot2", "dplyr", "tidyr", "tidyverse",
                   "lme4", "lmerTest", "MuMIn", "sjPlot",
                   "reshape2", "readxl", "writexl", "tibble",
                   "pheatmap", "RColorBrewer", "ggrepel",
                   "VennDiagram", "ggpubr", "ggplotify",
                   "webshot2", "rptR"))
                   

# Bioconductor packages
if (!requireNamespace("BiocManager", quietly = TRUE))
  install.packages("BiocManager")
BiocManager::install(c("DESeq2", "edgeR", "limma", 
                       "GEOquery", "apeglm"))
       
```

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/yourusername/Gene-Expression-Patterns-of-AMR-Plasmid-Transfer-Under-Tetracycline-Pressure.git
```

**2. Open the RStudio Project**

Open `Gene-Expression-Patterns-of-AMR-Plasmid-Transfer-Under-Tetracycline-Pressure.Rproj`

**3. Install required packages**

Run the installation code above in your R console

**4. Knit the R Markdown report**

Open `antimicrobial_dataset.Rmd` and click **Knit** — or run the 
`antimicrobial_dataset.R` script directly

## Acknowledgements
Dataset sourced from NCBI GEO (accession: GSE261094).

