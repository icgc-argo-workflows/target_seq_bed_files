# MONSTAR-JP Target Region BED Files

This folder contains **approximate primary target region BED files** for the following Foundation Medicine panels:

- **F1CDx** (FoundationOne® CDx)
- **F1LCDx** (FoundationOne® Liquid CDx)

These BED files were generated **in-house** based on gene lists published by Foundation Medicine, Inc. (**FMI**). FMI does *not* officially release BED files for these panels.

---

## Folder Structure
```
MONSTAR-JP/
└── Target-Seq/
  ├── F1CDX/
  │ ├── primary_target_regions.bed
  ├── F1LCDX/
  │ ├── primary_target_regions.bed
  └── README.md ← this file
```
> **Note:** This folder does **not** include `capture_target_regions.bed` files.  
> Due to the lack of publicly available probe-level design coordinates from FMI, it is not possible to accurately reconstruct the true capture regions.  
> The `primary_target_regions.bed` files represent the best approximation of targeted genomic intervals based on publicly available gene lists and annotations.

---

## How These BED Files Were Created

1. **Source**: Gene lists were collected from FMI’s relevant publication
   - **F1CDx**: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0264138
   - **F1LCDx**: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0237802

2. **Reference Genome**
   - Gene coordinates were mapped using the chosen reference genome build: **GRCh38.p14**.

3. **Region Definition**
   - The following genomic elements were included based:
     - **Promoter regions**
     - **Non-coding RNAs (ncRNA)**
     - **Exons**
     - **Introns**
   - **No additional padding** was applied to the coordinates.
   - Only annotated intervals were used; probe coverage details are unavailable.

---

## Important Notes
- These BED files are **approximations** and are **not official FMI releases**.
- The actual panel design may differ, including additional regions not represented here.
- These files are intended for research and exploratory use only.

---

## Recommended Use Cases

- Estimating approximate on-/off-target sequencing coverage.
- Region-based variant filtering and quality metrics calculation in pipelines.

---

## Disclaimer

These files and accompanying documentation are provided **as-is**, without warranty of any kind. The authors assume no responsibility for any consequences arising from their use.

---



