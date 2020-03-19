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
library(repmis)

URL="https://github.com/RJWANGbioinfo/PAS_reference_RData/blob/master/"
file="hg19_REF.RData"
source_data(paste0(URL,file,"?raw=True"))
```

# Test data: APA analysis in mouse testis versus heart
## About this dataset
To provide a complete tutorial of APA analysis using our package, we have now 
prepared a testing dataset through down sampling of mouse RNA-Seq data in heart 
(GSM900193) and testis (GSM900199):
| Sample ID | SRRID     | Sample Name | Down sampling reads|
|-----------|:---------:|------------:|----------:|
| GSM900199 | SRR453175 | Heart_Rep1  | 5 Million |
| GSM900199 | SRR453174 | Heart_Rep2  | 5 Million |
| GSM900199 | SRR453173 | Heart_Rep3  | 5 Million |
| GSM900199 | SRR453172 | Heart_Rep4  | 5 Million |
| GSM900193 | SRR453143 | Testis_rep1 | 5 Million |
| GSM900193 | SRR453142 | Testis_rep2 | 5 Million |
| GSM900193 | SRR453141 | Testis_rep3 | 5 Million |
| GSM900193 | SRR453140 | Testis_rep4 | 5 Million |

## Download the bam files
```{r eval=FALSE}
library(APAlyzer)
download_testbam()
flsall <- dir(getwd(),".bam")
flsall<-paste0(getwd(),'/',flsall)
names(flsall)<-gsub('.bam','',dir(getwd(),".bam"))
```