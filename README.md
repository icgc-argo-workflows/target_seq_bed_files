# target_seq_bed_files
Welcome to the ICGC-ARGO Targeted Sequencing BED Files repository. This repository hosts BED (Browser Extensible Data) files that define the genomic coordinates of specific target regions used in various targeted sequencing experiments from ICGC-ARGO projects.

These files are essential for researchers and bioinformaticians working on targeted sequencing data analysis, providing precise genomic intervals for:
- Read Mapping
- Coverage Analysis
- Variant Calling
- Quality Control

## Purpose of field and definitions

To support Whole Exome Sequencing (WXS) and Targeted Sequencing (Targeted-Seq) data submissions, the following metadata fields are required:

- target_capture_kit
- primary_target_regions
- capture_target_regions

### `target_capture_kit`: 
The experimental kit (commercial/lab owned) used to isolate specific regions of the genome. RNA bait sequences bind to relevant complementary DNA sequences. Used in combination with WGS, this allows for focused sequencing to improve depth/coverage at regions of interest.
### `primary_target_regions`:
A bed file of biologically relevant regions targeted by Target_capture_kit. These regions will typically extend capture_target_regions. Synonyms include : “empirical target”,”regions” and or “target intervals”
### `capture_target_regions`:
A bed file of regions captured by probes. “Covered regions” and “bait intervals”


## What are Targeted Sequencing BED Files?
Targeted Sequencing BED Files are plain text files that specify genomic regions of interest for targeted sequencing experiments. They are formatted according to the BED (Browser Extensible Data) file format, a simple and flexible standard widely used in genomics.

### BED File Format
A BED file lists genomic intervals using one line per region, with fields separated by tabs. The standard BED format includes three required fields:
- chrom: Chromosome name (e.g., chr1, chr2, ..., chrX, chrY, chrM)
- chromStart: Start position of the genomic interval (0-based, inclusive, GRCh38/hg38)
- chromEnd: End position of the genomic interval (0-based, exclusive, GRCh38/hg38)

*Note*: The chromStart position is zero-based and inclusive, while the chromEnd position is zero-based and exclusive. This means the first base of a chromosome is position 0, and the interval includes bases from chromStart up to but not including chromEnd.

### Example of a BED File Entry
```
chr7    55019017    55019067 
```

## Repository Contents
This repository is organized to provide easy access to BED files, documentation, and metadata related to various targeted sequencing panels. Below is an overview of the repository structure and the contents of each directory:
```
├── README.md
├── LICENSE
├── docs/
    ├── usage_instructions.md
    ├── BED_format_guidelines.md
    └── ...
├──{study_id}/
    ├── {experiment_type}/
      ├── {target_capture_kit}/
        ├── primary_target_regions.bed
        ├── capture_target_regions.bed
        ├── README.md
...
```
E.g. 
```
POG-CA > WXS > xGenTM_Exome_Hyb_Panel_v2 > primary_target_regions.bed 
```
This organization will capture the following possibilities:
- A study having multiple capture kits for WXS or Targeted-Seq.
- Two studies using the same “capture kit” with possibility of being different versions

## Proposed SOP
1. Prior to data submission, DCC will notify data submitter of BED file requirement
2. Data submitter will provide capture kit name
3. More information on capture kit can be obtained online if commercial, otherwise data submitter will have to provide
4. BED file will be converted to Hg38 coordinates and published on repo
5. Customized enum values which can be mapped to BED file name and URL will be used in payload
