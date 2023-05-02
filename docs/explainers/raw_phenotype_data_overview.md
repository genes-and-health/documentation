# Raw health data overview

**UNDER CONSTRUCTION**

## Summary

This page provides an overview of the raw health data available to Genes and Health TRE users. All files described below are located in `genesandhealth/library-red`, please see the [page describing TRE file structures](/docs/explainers/file_structure.md) for further information. File paths described below assume you are starting from `genesandhealth/library-red`

For complete descriptions of file contents, please see the [raw health data description](/docs/explainers/raw_phenotype_data_description.md)

All folders contain  detailed `README.txt` files, which describe the contents of each data file in more detail (number of rows, number of G&H volunteers present in the file etc). 

## Primary care data

Primary care datasets and linkage are provided by agreement with GP practices, made at the CCG level. As of 2023-04-14 all primary care data are for participants registered with practices in East London only. Data are refreshed periodically to add complete historical records for new participants, and to update existing participants' records with information from clinical contacts made since the previous refresh.

### London

All files are located in **/DSA_Discovery_7CCGs**. Subfolders are created for each data refresh. Folder names are the date of the refresh. For refreshes before 2023_01 data are further split by Clinical Commissioning Group (CCG). 

1. `GNH_thwfnech` are for volunteers registered at practices in Tower Hamlets, Waltham Forest, Newham, City & Hackney CCGs

2. `GNH_bhr` are for volunteers registered at practices in Barking, Havering, Redbridge and outer east London CCGs

**For refreshes after 2023-01 the data for these two regions are combined.**

As of 2023-01 Genes and Health does not have access to data for volunteers registered with practices in the North West London and South East London CCGS

#### Data files

Each folder contains the following files, all containing raw, individual level data, with one row per observation. 

-  `medications_ord` for normal repeat prescriptions

- `medications_stmt` for short term medications and treatments

- `observations` for diagnoses, blood test results, clinical measurements, other tests and referrals

- `procedure_req` for health and medication reviews, screening and vaccination records

All files contain:

- A pseudo nhs number for [linkage](/docs/explainers/how_is_data_linked.md) across all health data, and to the Genes and Health OrageneID number. 

- SNOMED concept ID for describing diagnoses, procedures, and prescriptions (useful for generating [binary traits](/docs/explainers/phenotype_curation.md))

- value results (for test results e.g. creatinine, height etc where applicable and useful for generating [quantitative traits](/docs/explainers/phenotype_curation.md))

- value units (where applicable) describing the unit of measurement (e.g. meters or cm for height)

- Clinical effective date (usually when the SNOMED code was entered into the patient record)

### Bradford
No raw primary care data as of 2023-04-14

### Manchester
No raw primary care data as of 2023-04-14

## Secondary care data

[Hospital Episode Statistics (HES)](https://digital.nhs.uk/data-and-information/data-tools-and-services/data-services/hospital-episode-statistics) data will be available on the TRE soon (pending NHS Digital approval at 2023-04-14), and for most purposes will supersede the regionally sourced secondary care data described below (HES will replicate the majority of data, and because it offers nationwide coverage, will include more G&H volunteers).

At present, secondary care data are split by location. As of 2023-04-14 secondary care data are available for volunteers in London and Bradford. 

### London

All files are located in `DSA_BartsHealth_NHS_Trust`. Subfolders are created for each data refresh. Folder names are the date of the refresh. Data are retrieved from the Barts Health Trust Data Warehouse and contain information on visits made by Genes and Health volunteers to hospitals in that Trust only. 

Barts Trust provide multiple datasets that are unique/ specific to that Trust, including pathology lab data (useful for generating [quantitative traits](/docs/explainers/phenotype_curation.md)), prescribing data, and radiology department reports. Some datasets are only available by special request (e.g. maternity bookings, chemotherapy prescribing). Please see the `README.txt` in the `DSA_BartsHealth_NHS_Trust` folder for further details.

Data in the `icd_10_combined_redacted.txt` and `opcs_combined_redacted.txt` files will have substantial overlap with HES (see note above on availability), and are useful for generating [binary traits](/docs/explainers/phenotype_curation.md)


### Bradford
Data provided by Bradford Teaching Hospitals NHS foundation trust

### Manchester
No raw primary care data as of 2023-04-14
