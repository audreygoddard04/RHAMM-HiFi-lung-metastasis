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

The central finding is that *Rhamm*⁻/⁻ metastases harbour 15-fold more
cohort-shared exclusive variants than wild-type (4,078 vs. 269), with
high allele frequencies (mean VAF = 0.939) consistent with clonal
dominance, despite carrying a higher overall mutation burden
(mean 23,159 vs. 14,349 variants per sample; p = 0.0008).

---

## Supplementary HTML Reports

Interactive HTML reports for all quality control and annotation analyses
are available in `supplementary/reports/`. Download any file and open it
in Chrome or Safari to view the full interactive report.

| Report | Tool | Description |
|--------|------|-------------|
| [HiFi Sequencing QC](supplementary/reports/hifi_multiqc_report.html) | MultiQC | Raw HiFi read quality across all 8 samples |
| [Coverage Report](supplementary/reports/mosdepth_multiqc_report.html) | MultiQC + mosdepth | Genome-wide coverage depth per sample |
| [Alignment Statistics](supplementary/reports/samtools_multiqc_report.html) | MultiQC + samtools | Alignment rates and read statistics |
| [NanoPlot QC](supplementary/reports/nanoplot_multiqc_report.html) | MultiQC + NanoPlot | Read length and quality distributions |
| [DeepVariant Report](supplementary/reports/deepvariant_complete_report.html) | DeepVariant | Variant calling summary across all samples |
| [KO SnpEff Summary](supplementary/reports/KO_snpEff_summary.html) | SnpEff | Functional annotation of KO-exclusive variants |
| [WT SnpEff Summary](supplementary/reports/WT_snpEff_summary.html) | SnpEff | Functional annotation of WT-exclusive variants |
| [KO VEP Summary](supplementary/reports/KO_vep_summary.html) | VEP | Variant effect prediction for KO-exclusive variants |
| [WT VEP Summary](supplementary/reports/WT_vep_summary.html) | VEP | Variant effect prediction for WT-exclusive variants |

> **Note:** GitHub does not render HTML files directly in the browser.
> Click the link, then click "Download raw file" to save it, and open
> it locally in Chrome or Safari.

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
Contact audreyannagoddard@gmail.com for access.

---

## Software Versions

### Bioinformatics (server: kh-compute.uwo.ca)
- pbmm2: v1.17
- samtools: v1.19.2
- DeepVariant: v1.6.0
- HiPhase: v1.6.0
- bcftools: v1.19
- mosdepth: v0.3.10
- NanoPlot: v1.46.2
- NanoComp: v1.25.6
- MultiQC: v1.33
- SnpEff: v5.4c
- VEP: v115.2
- Reference genome: GRCm39/mm39

### R
- R: v4.5.0
- ggplot2, patchwork, dplyr, tidyr, scales, cowplot (CRAN)
- clusterProfiler v4.18.4, enrichplot, org.Mm.eg.db (Bioconductor)

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
