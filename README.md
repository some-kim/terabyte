# Terrabyte

Our project analyzes the relationship between mining activity and deforestation using global datasets from 1990 to 2020. Our goal was to investigate whether increased mining correlates with forest loss and uncover regional patterns that may inform environmental policy.



First data setts Mining Activity Data (miningvalueT.csv), Forest Cover Change Data (forestdata.csv)

# 1. Data Cleaning & Preprocessing
General Rules:
- Standardize column names for readability
- Convert date fields
- numeric formats
- Handle missing values via exclusion
- Merge datasets based on geographic and temporal keys (in this case country + year)


Data Loading & Cleaning:

- Data was imported from .csv and .xlsx files on forest coverage, mining value, and governance
- All placeholder values like "..." were replaced with NaN or dropped
- Narrowed time frame (1990–2015/2020)

Data Transformation:

- Data reshapd to long format using melt(), aligns years and countries across both mining and deforestation
- Columns  renamed and cleaned for consistency
- Countries with overlapping records in each dtaset was used

Merging Datasets:

Mined and forest datasets were outer-joined on country and year, forming table (merged_long_df) of mining vs deforestation data.




