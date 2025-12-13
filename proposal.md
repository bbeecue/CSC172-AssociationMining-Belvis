
# CSC172 Association Rule Mining Project
**Student:** Febe Gwyn R. Belvis, 2022-0380  
**Date:** December 12, 2025

## 1. Project Title 
Association Rule Mining on Music Listening Habits and Mental Health Indicators

## 2. Problem Statement
Music is deeply involved and engrained in our lives, especially in our emotional regulation, stress levels, and well-being. However, most studies rely on correlations or predictive mdoels with respect to music and mental well-being rather than examining co-occuring patterns of listening behaviors, musical preferences, and mental health indicators. To address the aforementioned gap, this project seeks to observe which combinations of music generes, habits, and emotional states commonly occur together and see if such paterns can reveal meaningful associations about how us, individuals, use music to reflect on our mental health.

## 3. Objectives
- Transform the MxMH survey records into a transactional-style dataset which will be used for apriori rule mining.
- Identify frequent itemsets representing common combinations of music genres, havits, and mental health levels.
- Generate association rules and evaluate their strength using the following metrics: support, cinfidence, lift, conviction, and leverage.
- Visualize inisghts from the rules and interpret the associations.

## 4. Dataset Plan
- Source: Music & Mental Health Survey/MxMH (*from: https://www.kaggle.com/datasets/catherinerasgaitis/mxmh-survey-results/data*)
- Dataset Attributes:
<br> - Preferred genres
<br> - Hours of listening per day (Binned)
<br> - Mental Health Scores (Binned)
<br> - Demographics
<br> - Emotional Impacts
- Acquisition: Download

## 5. Technical Approach
**Algorithms**
- Apriori Algorithm  (to be tuned)

**Architectural Sketch**
1. Data Preprocessing
<br>-> Remove irrelevant attributes 
<br>->Handle missing values
<br>->Bin hours of listening per day and mental health scores
<br>->Convert all categorical features into one-hot encoded format and generate itemsets


2. Apriori Algorithm (to be adjusted and fine-tuned iteratively to balance the number and quality of generated itemsets)

****
- Framework: Python (`pandas`, `numpy`, `matplotlib/seaborn`, and `mlxtend`)
- Hardware: Google Colab


## 6. Expected Challenges & Mitigations
**Challenges:**
**High Data Distribution across differnet attributes (after one-hot encoding): This may generate very few "frequent" itemsets and/or large volume of rules with misleading correlations or low interpretability**

<br>*Solution: Combine or remove very low-frequency categories or apply length limits to the itemsets. I can also apply filters using lift, leverage, and conviction thresholds and post-process rules by selecting only high-value associations*