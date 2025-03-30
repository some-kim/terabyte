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

# 2. Visuals


- Time Series Plots for specific countries in this case  Brazil, showing trends in deforestation and mining
- Dual-Axis Plots to simultaneously track mining value and forest loss on different scales
- Graph Networks connecting countries to yearly environmental activity
- Cluster Analysis visualized using PCA-reduced scatterplots, with grouped countries

# 3. Results

 - positive correlation (≈ 0.50) between mining activity and deforestation, increased mining may lead to forest degradation
 - clstering identified regional patterns in deforestation trajectories grouping countries with similar results
 - time series trends have decreasing forest cover in countries like Brazil  with rising mining 

# 4. Technical

-  Data preprocessing included reshaping, merging, cleaning, and formatting inconsistencies
-  Clustering & PCA KMeans clustering followed by PCA for 2D visual
-  Graph Theory had a network of countries and activity over time to explore relationships via shortest paths and graph metrics
-  Used multiple libraries: pandas, numpy, matplotlib, seaborn, scikit-learn, networkx

# 5. Noteable results

PCA graph showed the results of a KMeans clustering analysis on deforestation data across different countries. Each point represents a country and the axes are the two "principal components" that capture the most variance in the data. Using KMeans clustering on deforestation trends from 1990 to 2015, we identified four distinct groups of countries based on the similarity of their forest loss patterns. Cluster 0 (green) contains the majority of countries such as Austria, and Belgium that experienced low or stable deforestation rates over time. These nations often have smaller forested areas, effective environmental regulations, or limited industrial-scale deforestation. Cluster 1 (orange) consists solely of the Russian Federation likely due to its large forested area and low deforestation levels spread across its region  making its pattern unlike the others. Similarly, Cluster 2 (blue) includes only Brazil  whose extreme deforestation levels  in the Amazon set it apart from all other countries. Cluster 3 (purple) groups Canada and China, which may share moderately high deforestation trends with consistent year-to-year fluctuations—potentially tied to industrial logging or land-use changes. These results highlight that while most countries follow similar environmental trends, a few outliers show unique or concerning deforestation behaviors that need deeper attention
