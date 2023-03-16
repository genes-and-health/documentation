This page goes through what data is available in the sandbox and how to access it. It is a work in progress and will be updated as more data becomes available.

## TRE folders and what is in them

/library-red/genesandhealth/ **2022\_05\_12\_pseudoNHS\_oragene\_withmissing\_DEIDENTIFIED.txt**

This file links Oragene ID (for genetics & questionnaire data) with PseudoNHS number (for NHS e-health record data). This file may get updated and re-dated.

**/library-red/genesandhealth/GSAv3EAMD/**

Illumina GSAv3EAMD genotyping chip and TOPMed-r2 imputation data.

**/library-red/genesandhealth/exome\_seq/**

Exome sequencing data. Currently @Feb 2022 n=5236 low/mid depth samples sequenced at Wellcome Sanger Institute and funded by Wellcome Sanger Institute are available. Both aligned cram files and callset vcfs are available. The file 5236\_cram\_IDlinkage.xlsx links Oragene IDs with multiple different ID types used by Wellcome Sanger Institute.

Industry Consortium funded exome sequencing data on the full 50,000+ Genes & Health volunteer cohort during 9 month post datafreeze priority periods will only be available in /consortiumpriorityperiod-library-red/ After the priority period data will go into /library-red/genesandhealth/exome\_seq/

**/library-red/genesandhealth/phenotypes\_curated/**

Phenotypes which have been manually or automated curated for consistency.

See also this document which has data descriptions, case counts, and phenotype codelists [https://docs.google.com/spreadsheets/d/1ipwdF2j\_owfr\_QbkDYk1rk0TW3KtdfQYVQn-Vf-o38s/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1ipwdF2j_owfr_QbkDYk1rk0TW3KtdfQYVQn-Vf-o38s/edit?usp=sharing)

**/library-red/genesandhealth/phenotypes\_rawdata/**

'Raw' phenotype and health record data (NHS numbers pseudonymised, and deidentified of names, postcodes, dates of birth etc).

Data is organised by provider and data sharing agreement. This is so we can easily change access should any of the terms of data sharing change.

Please see the README files in each folder for detail.

Please note as of Feb 2023, we do not yet have permission from NHS Digital to put their data in the TRE. An amendment is awaited.

**/library-green/genesandhealth/**

This contains downloadable data 'publically' available to users (read-only).

E.g. @Feb 2022 there is regenie GWAS data on ~180 phenotypes.
