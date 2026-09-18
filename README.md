# Pan-Cancer Germline Variant Carrier Analysis — All of Us v8

This repository contains the analysis notebook used to identify and summarize carriers of qualifying germline variants across a predefined cancer predisposition gene panel using **All of Us Research Program Controlled Tier v8** short-read whole-genome sequencing data.

## Analysis overview

The notebook:

1. constructs the participant-level demographic cohort from the All of Us v8 CDR;
2. loads the v8 short-read WGS Variant Annotation Table (VAT);
3. restricts annotations to **97 prespecified MANE transcript identifiers**;
4. applies the ClinVar-classification and variant-consequence filters used in the published analysis;
5. intersects qualifying variants with the WGS genotype MatrixTable;
6. restricts the genomic analysis to a prespecified **85-gene cancer predisposition panel**;
7. identifies participants carrying non-reference qualifying variants;
8. applies the study-specific downstream exclusions;
9. calculates overall, variant-level, and gene-level carrier summaries;
10. compares carrier frequencies across demographic groups; and
11. generates the corresponding figures and reporting tables.

## Notebook

- `pan_cancer_v8_github_documented.ipynb` — documented GitHub-facing version of the analysis notebook.

### Code preservation

The GitHub-facing notebook was created specifically to improve readability without changing the published analysis.

**All 162 executable code cells were preserved exactly from the original notebook.** No executable code, code comments, variable names, filters, statistical tests, hard-coded values, file paths, or plotting commands were modified. Only Markdown documentation was added or rewritten.

This is important because the notebook represents the workflow that generated the published results.

## Data access

The analysis uses **All of Us Controlled Tier v8** data. Controlled participant-level data are not distributed with this repository.

Reproduction therefore requires appropriate All of Us Researcher Workbench access and the corresponding v8 clinical and genomic resources.

The original notebook references Researcher Workbench environment variables including:

- `WORKSPACE_BUCKET`
- `CDR_STORAGE_PATH`
- `WORKSPACE_CDR`
- `GOOGLE_PROJECT`
- `WGS_CLINVAR_SPLIT_HAIL_PATH`

Some cells also contain workspace-specific Google Cloud Storage paths. These paths are retained unchanged for provenance. Users rerunning the workflow in a different authorized workspace will need to adapt those paths in their own copy.

## Genomic resources

The workflow uses:

- GRCh38;
- All of Us v8 short-read WGS SNP/indel data;
- the All of Us v8 Variant Annotation Table;
- 97 prespecified MANE transcript identifiers; and
- a predefined 85-gene cancer predisposition panel.

## Software

The original notebook uses Python together with packages and services including:

- Hail
- pandas
- NumPy
- SciPy
- statsmodels
- matplotlib
- seaborn
- Google BigQuery / All of Us Researcher Workbench utilities

Because the notebook was preserved to match the published analysis, package-version pinning has not been retroactively added to the executable cells.

## Privacy and repository contents

Notebook outputs are cleared from the public-facing file, and participant-level datasets are not included. The repository is intended to document the analysis workflow rather than redistribute Controlled Tier data.

## Citation

Please cite the associated JAMA publication when using or referring to this analysis. Add the full publication citation and DOI here in the repository README.
