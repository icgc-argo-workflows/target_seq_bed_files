# target_seq_bed_files
A repository to capture genes targeted by WES and target-Seq from ICGC-ARGO projects

## Purpose of field and definitions

To support WXS and Targeted Sequencing the following fields are now required :

- "Target_capture_kit"
- "primary_target_regions"
- "capture_target_regions"

### Target_capture_kit: 
The experimental kit (commercial/lab owned) used to isolate specific regions of the genome. RNA bait sequences bind to relevant complementary DNA sequences. Used in combination with WGS, this allows for focused sequencing to improve depth/coverage at regions of interest.
###  Primary_target_regions:
A bed file of biologically relevant regions targeted by Target_capture_kit. These regions will typically extend capture_target_regions. Synonyms include : “empirical target”,”regions” and or “target intervals”
###  Capture_target_regions:
A bed file of regions captured by probes. “Covered regions” and “bait intervals”
## Specifications of Bed Files
Bed files are text based with three columns: chromosome, chromosome start and chromosome end
Coordinates are to be zero-based and based on Grch38/Hg38
Bed files will hosted on www.github.com/icgc-argo-workflows/target_seq_bed_files

## Organization of Repo
Files will be organized under 
```
“studyId” > “Experiment Type” > “Target Capture Kit”
```
E.g. 
```
POG-CA > WXS > xGenTM Exome Hyb Panel v2 > Primary_target_regions.bed 
```
This organization will capture the following possibilities:
- A study having multiple capture kits for WXS or Targeted-Seq.
- Two studies using the same “capture kit” with possibility of being different versions
## Anticipated workflow
1. Prior to data submission, bioinfo will notify data submitter of bed file requirement
2. Data submitter will provide capture kit name
3. More information on capture kit can be obtained online if commercial, otherwise data submitter will have to provide
4. Bed file will be converted to Hg38 coordinates and published on repo
5. Value will be used in payload
