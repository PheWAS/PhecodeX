# PhecodeX

The PhecodeX repository contains data files relevant to the updated phecode nomenclature. A brief description of the particular files are listed below. These data components are designed to work with the original PheWAS R package and the relevant text for using these datafiles with this package are described in phecodeX_PheWAS_example_R_script.txt

# Data file components included in this package include: 

### phecodeX_PheWAS_example_R_script.txt ###
Example script for running the new PhecodeX data files with the original PheWAS R package.

### phecodeX_info.csv ###
This file includes information related to each phecode, including the phecode string, category, and columns indicating sex-specificity and ICD-10 only status. The columns are as follows:

        phecode             The phecode label (two letters, “_”, and numeric phecode)
        phecode_string      A descriptive label for phecode
        category_num        A numeric value corresponding to the phecode category
        category            A string indicating the phecode category
        sex                 A string with values “Both”,”Female” or “Male.” Sex-specific phecodes (e.g. Prostate cancer) are labeled by accordingly.
        icd10_only          A Boolean value: 1 if the phecode is defined only by ICD-10 codes; 0 if the phecode is defined by both ICD-9 and -10 codes
        leaf                A Boolean value: 1 if the phecode has no children; 0 if the phecode has one or more children
        phecode_num         The unique numeric component of the phecode label. Can be useful for sorting

### phecodeX_unfolled.csv ###
This file includes the ICD-9 and -10 codes that define each phecodes. All codes are “unrolled” meaning that phecode ID_002.1 implies ID_002. The columns are as follows:

        phecode               The phecode label
        ICD                   The ICD code included in the phecode grouping
        flag                  A numeric value 9 or 10 indicating the ICD code is ICD-9 or ICD-10

### phecodeX_ICD_map_flat.csv ###
A highly descriptive file that includes both phecode strings and ICD descriptions. This file is “flat” (i.e. not “unrolled”) such that child codes are not mapped to parents. This file is useful for examining which ICDs that inform a particular phecode. The columns are as follows:

        phecode               The phecode label
        phecode_string        A descriptive label for phecode
        category_num          A numeric value corresponding to the phecode category
        category              A string indicating the phecode category
        ICD                   The ICD-9 or ICD-10 code
        flag                  A numeric value 9 or 10 indicating the ICD code is ICD-9 or ICD-10
        ICD_string            The string description of the ICD code
        ICD_chapter           The chapter of the ICD code

### phecodeX_sex.csv ###
A descriptive file designed to indicate if a specific phecode is indicative of a sex specific code based on (>90% of codes use associated with EHR-reported female/male only). The columns are as follows:

        phecode               The phecode label
        male_only             A true/false indicator of whether the specific code is used more than 90% of the time with EHR-reported male sex
        female_only           A true/false indicator of whether the specific code is used more than 90% of the time with EHR-reported female sex
