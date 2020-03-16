# PAS reference RData: Pre-build PAS reference for APAlyzer

## Overview
All the Pre-build PAS reference regions are stored at here, currently support mm9, mm10, hg19, and hg38

## File list
Sample file are only need when Reps='YES'. This file is a two-column table contain the information of the sample and group. For instance, in the above case, the sample file should looks like:

| File name | Genome | Note |
| --- | --- | --- |
| hg19_REF.RData | hg19 | Conserved 3'UTR PAS and highly used IPA from PolyA_DB3 |
| hg19_REF_ALL.RData | hg19 | All 3'UTR PAS and IPA from PolyA_DB3 |
| hg38_REF.RData | hg38 | Conserved 3'UTR PAS and highly used IPA from PolyA_DB3 |
| mm9_REF.RData | mm9 | Conserved 3'UTR PAS and highly used IPA from PolyA_DB3 |
| mm9_REF_ALL.RData | mm9 | All 3'UTR PAS and IPA from PolyA_DB3 |
| mm10_REF.RData | mm10 | Conserved 3'UTR PAS and highly used IPA from PolyA_DB3 |

## Use the file in R
```
URL="https://github.com/RJWANGbioinfo/PAS_reference_RData/blob/master/"
file="hg19_REF.RData"
library(repmis)
source_data(paste0(URL,file,"?raw=True"))
```