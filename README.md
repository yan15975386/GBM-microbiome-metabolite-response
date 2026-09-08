# GBM microbiome-linked metabolite response programs

Reproducibility resources supporting the manuscript:

**Cross-modal analysis of microbiome-linked metabolite response programs in glioblastoma ecosystems**

## Overview

This repository contains the analysis code, fixed program/signature definitions, source-audit files,
software-session information, and machine-readable derived results used to connect microbiome-associated
gut taxa and curated metabolite-linked host responses with bulk, single-cell, and spatial transcriptomic
states in human glioblastoma.

The analytical chain is:

1. Prior MR-associated gut taxa
2. gutMGene taxonomy-aware microbe–metabolite–host integration
3. gutMDisorder human disease-context integration
4. TCGA-GBM and GSE16011 bulk transcriptomic validation
5. GSE182109 patient-level single-cell pseudobulk localisation and robustness analyses
6. GSE235672 spatial transcriptomic localisation and neighbourhood analyses
7. Expression-matched random-program and within-slide spatial-permutation specificity analyses

## Repository structure

```text
GBM-microbiome-metabolite-response/
├── README.md
├── LICENSE
├── LICENSE_CODE.md
├── LICENSE_DATA.md
├── CITATION.cff
├── .gitignore
├── MANIFEST.sha256
├── scripts/
│   ├── step3_bulk/
│   ├── step4_singlecell/
│   ├── step4B_robustness/
│   ├── step5_spatial/
│   └── step6_specificity/
├── derived_tables/
│   ├── step1_gutMGene/
│   ├── step2_gutMDisorder/
│   ├── step3_bulk/
│   ├── step4_singlecell/
│   ├── step4B_robustness/
│   ├── step5_spatial/
│   └── step6_specificity/
├── program_definitions/
├── source_audit/
├── session_info/
└── supplementary/
```

## Raw data are not redistributed

This repository intentionally does **not** redistribute the original TCGA, GEO, gutMGene, or
gutMDisorder source datasets.

The primary public transcriptomic datasets used in the study are:

- TCGA-GBM
- GSE16011
- GSE182109
- GSE235672

The upstream curated microbiome resources are gutMGene v2.0 and gutMDisorder v3.0.

Users should obtain the original source data from the corresponding public repositories and databases,
subject to their respective terms and access policies.

## Fixed program definitions

The host-response programs and GBM context signatures were fixed before downstream cross-modal testing.
Convenient copies are provided under `program_definitions/`, while the executed step-specific packages
retain their original configuration/resource files under `scripts/`.

## Reproducibility notes

The archived scripts are preserved as executed for auditability. Several step-specific configuration files
contain the original Linux server paths used by the authors. To reproduce the workflow on another system,
edit the relevant `00_config.R` or `01_config.R` paths before running the corresponding `09_run_all.R`.

The single-cell stages were run in R 4.4.1 on Linux. Available `sessionInfo()` outputs are collected in
`session_info/`.

## Interpretation boundary

The metabolite-linked program scores represent **transcriptional resemblance to curated host responses**.
They must not be interpreted as direct measurements of intratumoural metabolite concentrations,
gut microbial abundance, or direct microbial causation in glioblastoma.

## Licensing

- Analysis code: MIT License (`LICENSE_CODE.md`)
- Derived tables and repository documentation: CC BY 4.0 (`LICENSE_DATA.md`)

See `LICENSE` for the repository-level licensing summary.

## Citation

Please cite the associated manuscript when published. Citation metadata for the repository are provided in
`CITATION.cff`.

## Contact

Corresponding author: Chun Luo  
Department of Neurosurgery, Tongji Hospital Affiliated to Tongji University, School of Medicine,
Tongji University, Shanghai, China  
Email: boyluochun@126.com
