# RHAMM-HiFi-lung-metastasis
Long-read sequencing reveals reduced genomic heterogeneity in RHAMM-deficient breast cancer lung metastases.
## About This Repository

This repository contains the analysis scripts and supplementary materials
for my undergraduate Honours thesis in Biology at the University of
Western Ontario (2026).

**Author:** Audrey Goddard
**Supervisor:** Dr. Kathleen Hill
**Mentor:** Joseph Butler
**Institution:** Department of Biology, University of Western Ontario
**Degree:** BSc Honours Biology (Biology 4999E)
**Year:** 2026

---

## Project Summary

This study used PacBio HiFi long-read whole-genome sequencing to
characterize genome-wide genetic heterogeneity in lung metastases from
MMTV-PyMT breast cancer mice with and without RHAMM deficiency.

The central finding is that Rhamm-/- metastases harbour 15-fold more
cohort-shared exclusive variants than wild-type (4,078 vs. 269), with
high allele frequencies (mean VAF = 0.94) consistent with clonal
dominance, despite carrying a higher overall mutation burden.

---

## Repository Contents

| Folder | Contents |
|--------|----------|
| `scripts/R/` | R scripts for all figures and statistical tests |
| `scripts/filtering/` | Bash scripts for the variant filtering pipeline |
| `supplementary/` | MultiQC reports, NanoPlot HTML files, alignment stats |
| `data/gene_lists/` | Gene lists used for DAVID and ClusterProfiler analysis |
| `data/parsed/` | Parsed TSV files used as input for R figures |
| `figures/` | Final publication-quality PNG figures |

---

## How to Run the R Analysis

### Requirements
Install these R packages before running:
```r
install.packages(c("ggplot2", "patchwork", "dplyr",
                   "tidyr", "scales", "cowplot"))
BiocManager::install(c("clusterProfiler", "enrichplot",
                       "org.Mm.eg.db"))
```

### Steps
1. Download this repository (green "Code" button → Download ZIP)
2. Unzip it and open RStudio
3. Set working directory to the folder containing the data files:
   Session → Set Working Directory → Choose Directory
4. Open `scripts/R/00_run_all.R`
5. Click Source — this runs all scripts in order

Output figures are saved to `~/Desktop/FinalThesisFigures/`

---

## Input Data Files Required

Place these files in the same folder as the R scripts before running:

| File | Description | How to generate |
|------|-------------|-----------------|
| `ko_parsed.tsv` | Parsed KO exclusive VCF | See Appendix C of thesis |
| `wt_parsed.tsv` | Parsed WT exclusive VCF | See Appendix C of thesis |
| `ko_exclusive_genes_clean.txt` | KO gene list | Extracted from SnpEff VCF |
| `wt_exclusive_genes_clean.txt` | WT gene list | Extracted from SnpEff VCF |

Raw FASTQ and BAM files are not included due to size.
Contact audrey.goddard@uwo.ca for access.

---

## Software Versions

### Bioinformatics (server: kh-compute.uwo.ca)
- pbmm2: vX.X.X
- samtools: v1.33
- DeepVariant: vX.X.X
- HiPhase: vX.X.X
- bcftools: vX.X.X
- mosdepth: vX.X.X
- NanoPlot: vX.X.X
- Reference genome: GRCm39/mm39

### R
- R version 4.5.0
- ggplot2, patchwork, dplyr, scales (CRAN)
- clusterProfiler v4.18.4, org.Mm.eg.db (Bioconductor)

---

## Citation

Goddard, A.A. (2026). Long-read sequencing reveals reduced genomic
heterogeneity in RHAMM-deficient metastases. Honours Thesis,
Biology 4999E, University of Western Ontario.

---

## Acknowledgements

This work was supervised by Dr. Kathleen Hill and supported by NSERC,
the Canadian Cancer Society, the Cancer Research Society, the London
Health Sciences Centre Research Institute, and Western Science.

---

## Licence

Code is released under the MIT Licence.
Data available upon request.
