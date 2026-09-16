# MIMIC-IV Clinical Data Analysis Exercise
MIMIC IV demo data is a publicly available data set of deidentified health record for 100 patients. I analyzed this dataset to find the highest number of diagnoses in the sample, diagnoses with the highest mean admission times, and diagnoses with the highest median admission times. This exercise helped further build my knowledge and genuine familiarity with clinical data structure.

Admissions and diagnoses tables were joined on `hadm_id` and the ICD lookup table was joined on `icd_code` and `icd_version`. The version field had to be accounted for because ICD-9 and ICD-10 can share the same codes for different diagnoses. Length-of-stay was derived from `admittime` and `dischtime`, then grouped by diagnosis and filtered to diagnoses with ≥5 occurrences to avoid small-sample distortion. Mean and median lengths of stay were compared per diagnosis to check for right-skew from outlier stays.

See [results.md](results.md) for the diagnosis frequency and length of stay tables.

How to run this yourself?
1. Download the following CSVs from the `hosp` folder at the bottom of the page: MIMIC-IV Demo on PhysioNet (https://physionet.org/content/mimic-iv-demo/2.2/)
- `admissions.csv.gz`
- `diagnoses_icd.csv.gz`
- `d_icd_diagnoses.csv.gz`
2. Place them in the same folder as `clinical_analysis.ipynb`.
3. Run the notebook top to bottom in Jupyter.
