# MONSTAR-JP Target Region BED Files

This folder contains **approximate target region BED files** for the following Foundation Medicine panels:

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
  │ └── capture_target_regions.bed (same as primary)
  ├── F1LCDX/
  │ ├── primary_target_regions.bed
  │ └── capture_target_regions.bed (same as primary)
  └── README.md ← this file
```


| Term | What It Means Here |
|------|--------------------|
| **Primary Target Regions** | A bed file which holds the biologically relevant target regions (based on a genome, e.g. GRCh38) to capture by the assay. |
| **Capture Target Regions** | A bed file which holds the technically relevant probes regions to capture by the assay.  |


**Note:** For each panel, the `capture_target_regions.bed` is intended to represent probe-captured areas, but here **the same BED is reused** because detailed probe-level capture coordinates were not available from FMI.  

---

## How These BED Files Were Created

1. **Source**: Gene lists were collected from FMI’s relevant publication
   - **F1CDx**: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0264138
   - **F1LCDx**: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0237802

2. **Reference Genome**
   - Gene coordinates were mapped using the chosen reference genome build: **GRCh38.p14**.

3. **Region Definition**
   - The following genomic elements were included based on standard genome annotations (**to be specified**) :
     - **Promoter regions**
     - **Non-coding RNAs (ncRNA)**
     - **Exons**
     - **Introns**
   - **No additional padding** was applied to the coordinates.
   - Detailed probe design coordinates are not available; therefore, the same region file is used for both the primary and capture BED files.

---

## Important Notes

- These BED files are **not official** FMI releases.  
- The real assay may cover more or fewer bases than defined here.
- Users should **validate these files** before use in any production analysis.
- Please do **NOT** use these files for regulatory submissions, clinical decision-making, or patient reports without independent verification.

---

## Recommended Use Cases

- Estimating approximate on-/off-target sequencing coverage.
- Region-based variant filtering and quality metrics calculation in pipelines.
- Research and exploratory analyses.

---

## Disclaimer

These files and accompanying documentation are provided **as-is**, without warranty of any kind. The authors assume no responsibility for any consequences arising from their use.

---



