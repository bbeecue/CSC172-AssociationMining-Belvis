# Association Rule Mining on Music Listening Habits and Mental Health Indicators
**CSC173 Intelligent Systems Final Project**  
*Mindanao State University - Iligan Institute of Technology*  
**Student:** Febe Gwyn R. Belvis, 2022-0380 
**Semester:**  AY 2025-2026 Sem 1


[![Python](https://img.shields.io/badge/Python-3.13+-blue)](https://python.org)


## Abstract


## Table of Contents
- [Introduction](#introduction)
- [Related Work](#related-work)
- [Methodology](#methodology)
- [Experiments & Results](#experiments--results)
- [Discussion](#discussion)
- [Ethical Considerations](#ethical-considerations)
- [Conclusion](#conclusion)
- [Installation](#installation)
- [References](#references)

## Introduction
### Problem Statement
Music is deeply involved and engrained in our lives, especially in our emotional regulation, stress levels, and well-being. However, most studies rely on correlations or predictive modls with respect to music and mental well-being rather than examining co-occuring patterns of listening behaviors, musical preferences, and mental health indicators. Therefore, this project seeks to observe which combinations of music generes, habits, and emotional states commonly occur together and see if such paterns can reveal meaningful associations about how us, individuals, use music to reflect on our mental health.

### Objectives
- Transform the MxMH survey records into a transactional-style dataset which will be used for apriori rule mining.
- Identify frequent itemsets representing common combinations of music genres, havits, and mental health levels.
- Generate association rules and evaluate their strength using the following metrics: support, cinfidence, lift, conviction, and leverage.
- Visualize insights from the rules and interpret the associations.


## Related Work
- De Filippis, R., & Foysal, A. A. (2025). Associations between Music Listening Habits and Mental Health: A Cross-Sectional Analysis. OALib, 12(04), 1–29. https://doi.org/10.4236/oalib.1113196
- Dong, X., Kang, X., & Ding, X. (2022). Influence and analysis of music teaching environment monitoring on students’ mental health using data mining technology. Journal of Environmental and Public Health, 2022(1), 1120156. https://doi.org/10.1155/2022/1120156

(GAPS: Most accessible papers only explores either ARM on mental health or ARM on music and not on both)

## Methodology
### Dataset
- Source: Kaggle Music X Mental Health Survey
- Shape: 736 Rows - 33 Columns
- 

### Apriori Algorithm and Values

| Parameter | Value |
|-----------|-------|
| Batch Size | 16 |
| Learning Rate | 0.01 |
| Epochs | 100 |
| Optimizer | SGD |


### Implementation Code Snippet
`frequent_items = apriori(df_onehot, min_support=0.1, use_colnames=True, max_len=5)`

`rules = association_rules(frequent_items, metric="support", min_threshold=0.05)
support_rules = rules.sort_values('support', ascending=False)`

[display_cols].head(10)

## Experiments & Results
### Metrics
| Metric| Rule | Percentage |
|-------|---------|-----------|
| Support | 85% | 0.87 | 0.82 | 12 |
| Confidence (Fine-tuned)** | **92%** | **0.94** | **0.89** | **15** |
| Lift (Fine-tuned)** | **92%** | **0.94** | **0.89** | **15** |
| Leverage (Fine-tuned)** | **92%** | **0.94** | **0.89** | **15** |
| Conviction (Fine-tuned)** | **92%** | **0.94** | **0.89** | **15** |

![Scatter Plot](images/loss_accuracy.png)

### Demo
![Detection Demo](demo/detection.gif)
[Video: [CSC173_YourLastName_Final.mp4](demo/CSC173_YourLastName_Final.mp4)] [web:41]

## Discussion
- Strengths: Decently tells us about the correlation and co-occurence of some mental health variables (anxiety and depression) and the most common favorite music genre (rock)

- Limitations: Very high dimensionality of dataset after preprocessing and one-hot encoding.

- Insights: 
    - Pruned itemsets with support below 0.1 or 1%. 
    - Excluded low power columns/high cardinality features
    - Binned some numerical features to reduce categories

## Ethical Considerations
- Bias: Dataset skewed toward plastic/metal; rural waste underrepresented
- Privacy: No faces in training data
- Misuse: Potential for surveillance if repurposed [web:41]

## Conclusion
[Key achievements and 2-3 future directions, e.g., Deploy to Raspberry Pi for IoT.]

## Installation
1. Clone repo: `git clone https://github.com/bbeecue/CSC172-AssociationMining-Belvis`
2. Install deps: `pip install -r requirements.txt`
3. Run notebook (1) `exploration_preprocessing.ipynb` then (2) `apriori_implementation.ipynb`

**requirements.txt:**
pandas
numpy
matplotlib
mlxtend
scikit-learn
seaborn

## References
[1] Dong, X., Kang, X., & Ding, X. (2022). Influence and analysis of music teaching environment monitoring on students’ mental health using data mining technology. Journal of Environmental and Public Health, 2022(1), 1120156. https://doi.org/10.1155/2022/1120156

[2] https://statisticsbyjim.com/graphs/pareto-charts/

## GitHub Pages
View this project site: [https://jjmmontemayor.github.io/CSC173-DeepCV-Montemayor/](https://jjmmontemayor.github.io/CSC173-DeepCV-Montemayor/) [web:32]
