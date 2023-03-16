
1.
## Getting help




1.

1.
## Data into and out of the TRE ![](RackMultipart20230315-1-192w74_html_7f08186abd517f83.png)










1.
## Linux Terminal

## Starting the Terminal ![](RackMultipart20230315-1-192w74_html_24a30aa7a3292bb1.png) ![](RackMultipart20230315-1-192w74_html_444e220ec98148cb.png)

The Terminal Application can be started from the Applications menu. Or conveniently, by right clicking on a folder and selecting Open Terminal Here.

##


## Multithreaded high i/o applications

Highly multithreaded applications (e.g. plink, regenie) running on many cores may crash/be unstable due to slow input/output from the library-red google storage bucket e.g. the 0.5Tb GSA data pgen files. The solution is to copy the very large files to local fast storage e.g. to /home/ivm/Documents and then read the files from there. The WDL pipelines automatically localise all files as a first step.

## Running docker images in the TRE



1.
## WDL HPC Pipelines

The pipeline runs container images, and enables almost unlimited high performance compute (which is not free!). Only some sandboxes have WDL Pipeline access at present, in order to control potential costs.

Google Cloud Platform WDL scripts are in use for a lot of genetics, genomics especially at Finngen, Broad Institute and NHGRI (Terra/Anvil platform). Thus there are a lot of user guides and useful scripts out there already:

## Useful links to learn WDL and Cromwell:

https://software.broadinstitute.org/wdl/

https://software.broadinstitute.org/wdl/documentation

https://cromwell.readthedocs.io/en/develop/

[https://cromwell.readthedocs.io/en/develop/tutorials/PipelinesApi101/](https://cromwell.readthedocs.io/en/develop/tutorials/PipelinesApi101/)

## Genes & Health TRE managed pipelines, with documentation

https://github.com/wsi-hgi-tre/pipelines

The documentation for the WDL supported by the TRE can be found here:

https://github.com/openwdl/wdl/blob/main/versions/draft-2/SPEC.md

## WDL Pipelines from other projects

- Broad Institute/Terra via website and github
- Finngen github [https://github.com/FINNGEN/](https://github.com/FINNGEN/)
- NHGRI DockStore [https://anvilproject.org/learn/introduction/intro-to-dockstore](https://anvilproject.org/learn/introduction/intro-to-dockstore)
- Other Dockstore [https://dockstore.org/search?descriptorType=wdl&entryType=workflows&searchMode=files](https://dockstore.org/search?descriptorType=wdl&entryType=workflows&searchMode=files)
- BioWDL [https://github.com/biowdl](https://github.com/biowdl)

## Controlling Google Cloud Platform costs

Terra has a good guide about this [https://support.terra.bio/hc/en-us/sections/360006459511-Controlling-Cloud-costs](https://support.terra.bio/hc/en-us/sections/360006459511-Controlling-Cloud-costs)

WRITING IN PROGRESS

1.
## Billing

WRITING IN PROGRESS

1.
## Phenotypes

Genes & Health volunteers complete a stage 1 questionnaire at recruitment. This enables the NHS number to be found.

Various types of NHS data are available via data sharing agreements with NHS Trusts, NHS Digital, Primary care etc.

Genes & Health has curated multiple phenotypes, more details are available here:

[https://docs.google.com/spreadsheets/d/1ipwdF2j\_owfr\_QbkDYk1rk0TW3KtdfQYVQn-Vf-o38s/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1ipwdF2j_owfr_QbkDYk1rk0TW3KtdfQYVQn-Vf-o38s/edit?usp=sharing)

WRITING IN PROGRESS

1.
## Other sources of information

Old slides from Solita

[https://docs.google.com/presentation/d/1UlH3vfzMuq4tY5ulIDePUBNKuXAgthLlilWUMdnXKp4/edit?usp=sharing](https://docs.google.com/presentation/d/1UlH3vfzMuq4tY5ulIDePUBNKuXAgthLlilWUMdnXKp4/edit?usp=sharing)

Slightly old user induction slides from Chris Harrison (Sept 2021). Some of the file paths are not correct. Contains info on WDL/Pipelines

[https://docs.google.com/presentation/d/1BUGVFMzTPCgzGC9UaN\_ogNb3hnygqfk0oywjAq-8YmI/edit?usp=sharing](https://docs.google.com/presentation/d/1BUGVFMzTPCgzGC9UaN_ogNb3hnygqfk0oywjAq-8YmI/edit?usp=sharing)

Sanger Institute confluence with admin information.

[https://confluence.sanger.ac.uk/display/HGI/Solita+TRE](https://confluence.sanger.ac.uk/display/HGI/Solita+TRE)

1.
## Planned Enhancements to the TRE / wishlist

- Better billing controls, capping spend on WDL pipelines, for example
- Allow users to put their own data in. Some sort of 1-way rysnc to a google bucket? Will need to be sandbox specific
- Put raw health data in once ISO27001 compliance achieved
-

1.
## Appendix

## Example regenie script for binary trait GWAS

## David van Heel, updated July 2022

## please feel free to adapt and reuse this script

## linux shell script or command line copy/paste to run regenie on Genes & Health Google Cloud TRE

## please test your script runs first on the cheap 2 core machine

## regenie has really good multithreading and will be fastest on the 64 core huge machine, but this costs $$ so PLEASE MAKE SURE YOU ACTIVELY TURN IT OFF !

## It is fast enough on a big multicore machine that you can run it just from the command line using a single all-chromosome pgen input file, no need for HPC or splitting by chromosome. Regenie will use all threads available minus 1 by default, so the big 64 core machine will run 63 times faster for the compute steps than the 2 core machine.

## It is fast enough on a big multicore machine that you can run several phenotypes. Obviously if you want to run 1000 phenotypes you will need to use Google HPC / WDL.

## RUN THIS FROM THE FOLDER WITH THE COVAR/PHENO FILES AND WHERE YOU WANT THE OUTPUT

## this is for BINARY TRAITS

## remove the --bt and firth etc options for quant traits, see the online regenie manual [https://rgcgithub.github.io/regenie/options/](https://rgcgithub.github.io/regenie/options/)

## first copy big files to local storage ivm SSD for better i/o than with google storage buckets

## regenie will sometimes crash if reading direct from library-red due to slow i/o

## cp /genesandhealth/library-red/genesandhealth/GSAv3EAMD/Jul2021\_44k\_TOPMED-r2\_Imputation\_b38/topmed-r2\_merged\_version03/chrALLincX.dose.merged\_INFO0.3\_MAF0.00001\_F\_MISSING0.2.8bit.sorted.p\* /home/ivm/Documents/

## CHANGE THE DATE EACH RUN ##

daterun=2022\_07\_20

covarfile="/genesandhealth/library-red/genesandhealth/GSAv3EAMD/Jul2021\_44k\_TOPMED-r2\_Imputation\_b38/GNH.44190.noEthnicOutliers.covariates.20PCs.tab"

## updated to covarfile with correct FID IID structure 15 July 2022

phenofile="/genesandhealth/library-red/genesandhealth/phenotypes\_curated/version005\_2022\_06/1stoccurrence\_3digitICD10\_1SNOMEDto1ICD10/2022\_06\_version005\_3digitICD10\_1to1\_42029withbothICD10andGSAJul2021.txt"

## these are the custom phenotypes: "/genesandhealth/library-red//genesandhealth/phenotypes\_curated/version005\_2022\_06/custom/2022-06-15\_big\_regenie\_phenoFile.txt"

grmfile="/genesandhealth/library-red/genesandhealth/GSAv3EAMD/Jul2021\_44k\_TOPMED-r2\_Imputation\_b38/bfile\_forSAIGEgrm\_44396\_chipgenotypes\_indep-pairwise\_500\_50\_0.2\_LDpruned\_NotChrY"

## regenie will run all phenotypes in the phenoFIle if you dont specify --phenoCol or --phenoColList

## beware the .log file does not have phenotype name in its filename (because it is designed for running many phenotypes at once), can get overwritten if run multiple times using same $daterun

## if want to run male-only or female-only analysis, best to use --keep with a list of individuals in Step1 Step2 rather than --sex-specific. Because sex-specific uses the sex in the bed or pgen files not from the covariate file. And sex is NA in the pgen file we have made

regenie \

--step 1 \

--bed "$grmfile" \

--covarFile "$covarfile" \

--phenoFile "$phenofile" \

--phenoExcludeList PseudoNHS\_2022\_02\_08 \

--phenoCol ICD10\_\_E10,ICD10\_\_E11 \

--minCaseCount 100 \

--bsize 1000 \

--bt \

--lowmem \

--lowmem-prefix tmp\_rg \

--gz \

--verbose \

--out "$daterun"\_fit\_binary\_out

regenie \

--step 2 \

--pgen /home/ivm/Documents/chrALLincX.dose.merged\_INFO0.3\_MAF0.00001\_F\_MISSING0.2.8bit.sorted \

--covarFile "$covarfile" \

--phenoFile "$phenofile" \

--bsize 1000 \

--minMAC 20 \

--minINFO 0.6 \

--bt \

--firth --approx \

--pThresh 0.01 \

--pred "$daterun"\_fit\_binary\_out\_pred.list \

--gz \

--verbose \

--out "$daterun"\_GNH\_binary\_GWAS\_firth

## END ##

## **Version Control**

| **Version** | **Issue Date** | **Changes** | **Author** |
| --- | --- | --- | --- |
| 1 | 04.03.2022 | Initial draft | David van Heel |
| 2 | 04.02.2023 | Backup policy and Version control added | Vivek Iyer |
|
 |
 |
 |
 |
|
 |
 |
 |
 |

## **Approval**

| **Version** | **Review Date** | **Reviewed by** |
| --- | --- | --- |
| 1 | April 2022 | ISMS committee |
| 2 | Feb 2023 | ISMS committee |