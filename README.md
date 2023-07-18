# phecodeX

The phecodeX repository contains data files relevant to the updated phecode nomenclature. A brief description of the particular files are listed below. These data components are designed to work with the original PheWAS R package and the relevant text for using these datafiles with this package are described in phecodeX_PheWAS_example_R_script.txt

# Data file components included in this package include: 

### phecodeX_PheWAS_example_R_script.txt ###
Example script for running the new PhecodeX data files with the original PheWAS R package.

### phecodeX_R_labels.csv ###
This file includes information related to each phecode, including the phecode string, category, and columns indicating sex-specificity and ICD-10 only status. The columns are as follows:

        phenotype           The phecode label (two letters, “_”, and numeric phecode)
        description         A descriptive label for phecode
        icd10_only          A Boolean value: 1 if the phecode is defined only by ICD-10 codes; 0 if the phecode is defined by both ICD-9 and -10 codes
        groupnum            A numeric value corresponding to the phecode category
        group               A string indicating the phecode category
        color               A string value indicating the color to use in plots for each group

### phecodeX_R_map.csv ###
This file includes the ICD-9 and -10 codes that define each phecodes. This mapping is "flat" in that the phecodes are not "unrolled." The columns are as follows:

        code                  The code included in the phecode grouping (current supported code types are ICD-9-CM and ICD-10-CM)
        vocabulary_id         A string indicating the code type (ICD9CM or ICD10CM)
        phecode               The phecode label
        
### phecodeX_R_rollup_map.csv ###
This file defines the phecode structure. Phecodes with decimals are "rolled up" to parent codes, such that every individual with code BI_160.11 also has BI_160.1 and BI_160.

        code               Primary phecode label
        phecode_unrolled   A phecode that is implied by the primary phecode label

### phecodeX_R_sex.csv ###
A descriptive file designed to indicate if a specific phecode is indicative of a sex specific code based on (>90% of codes use associated with EHR-reported female/male only). The columns are as follows:

        phecode               The phecode label
        male_only             A true/false indicator of whether the specific code is used more than 90% of the time with EHR-reported male sex
        female_only           A true/false indicator of whether the specific code is used more than 90% of the time with EHR-reported female sex
