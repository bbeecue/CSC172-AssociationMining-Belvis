# CSC172 Association Rule Mining Project
**Student:** Febe Gwyn R. Belvis, 2022-0390
**Date:** December 13, 2025  
**Repository:** [https://github.com/bbeecue/CSC172-AssociationMining-Belvis](https://github.com/bbeecue/CSC172-AssociationMining-Belvis)  
**Commits Since Proposal:** 8 | **Last Commit:** December 14, 2025 (6:25 PM)

## 📊 Current Status
| Milestone | Status | Notes |
|-----------|--------|-------|
| Exploratory Data Analysis | ✅ Done | Finalized columns to include and binning strategy |
| Preprocessing| ✅ Done | Binned Hours and Mental Health Variables Value + ~~Transformed genre frequency to one-hot encoding~~|
|*Removed genre listening frequency due to extreme sparsity* + Fixed df to cv code for proper transactions format|
| Association Rule Mining Implementation | ✅ Done | Finalized metric values (justification for the values to be explained) |
| Rule Filtering & Evaluation | ✅ Done | Exported each metric-high rules to CSV files |
| Interpretation and Visualization | ✅ Done| Visualized Annotated Scatterplot (adjustments demonstrated during demo video) 

## 1. Dataset Progress (Done ✅)
Analysis & Preprocessing
- Shape (before): (736 rows, 33 columns) 
- Shape (after): (736 rows, 9 columns) 
- Filled missing values (8) in `Music effects` column with its mode
- Binned hours:
    - Low-Medium <= 4 hours
    - High Hours > 4 hours
- Reduced fave genres to onyl top 12. Excluded genres are merged to 'Others' 
- exported to transactions.csv

- Dropped columns (explanation also included in the notebook):

| Feature | Data Type / Issue | Justification for Dropping (Sparsity Avoidance) |
| :--- | :--- | :--- |
| **Timestamp** | High Cardinality | These are unqiue timestamps for when the individual took the survey. Not relevant and will just introduce sparsity |
| **Age** & **BPM** | Continuous / Numerical | Require careful binning. Poor binning choices (too many bins or uneven distributions) introduce sparse itemsets and will just widen the itemsets' dimensions, and this hinders drawing meaningful rules |
| **Primary streaming service** | High/Moderate Cardinality (Not relevant) | Spotify has an overwhelming mode. The column also lacks power or relevance to other columns, therefore will just add unnecessary sparsity to the itemsets |
| **Exploratory, Foreign languages, While working, Instrumentalist, Composer** | Binary / Low Frequency | These are expected to have **low support** (meaning it has 'No' values) + add unnecesssary sparsity to the itemsets |
| **Permissions** | Zero variance | By default, all individuals in the dataset would have to give permission to the survey in order for the dataset to be created.|

The `Frequency [genre]` columns were dropped as well due to very high dimensionality. This is just according to my judgement to satisfy the requirements of Apriori transactional encoding, cleaner itemsets, and mitigate the risk of multicollinearity.

**Sample data preview:**
![Dataset Sample 1](images/dataset_preview.png)
![Dataset Sample 2](images/dataset_preview2.png)



## 2. ARM Implementation Progress
Metrics (minimum thresholds):
- For pruning (support): 0.1
- 


## 3. Challenges Encountered & Solutions (TO BE EDITED)
| Issue | Status | Resolution |
|-------|--------|------------|
| High Sparsity (with frequency per genre) | ✅ Solved | Dropped columns that will only introduce high sparsity (with justification in dataset progress and notebook)|
| TransitionEncoder doesn't one-hot encode the transitions.csv properly | ✅ Solved | Used the manual python method for opening csv (huhumaoradiay) |
| Too many rules generated | ✅ Solved | Adjusted minimum thresholds for metrics (lowered)|


## 4. Next Steps [TO BE EDITED] (Before Final Submission) 
- [✅] Data Analysis + Preprocessing
- [✅] Transactional format (from exploration notebeook) convert to csv
- [✅] Fix TransitionEncoder problem notebook
- [✅] Apriori Implememntation
- [✅] Rule Filtering
- [✅] Evaluation and Analysis


