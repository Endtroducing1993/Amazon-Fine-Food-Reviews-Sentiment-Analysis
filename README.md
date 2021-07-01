# Amazon Fine Food Reviews

Table of Contents:
Problem Statement
About Data
EDA and Data Cleaning
Data featurization
Performance Metric
Predictive Modelling
Results
*****************************************************************************
# 1. Problem Statement: Given a review of Amazon Fine Food product we have to determine whether the review is positive (Rating of 4 or 5) or negative (rating of 1 or 2).

**2. About Data:** 
The Amazon Fine Food Reviews dataset consists of reviews of fine foods from Amazon.

Number of reviews: 568,454
Number of users: 256,059
Number of products: 74,258
Timespan: Oct 1999 - Oct 2012
Number of Attributes/Columns in data: 10 
 
Attribute Information:
 
1. Id
2. ProductId - unique identifier for the product
3. UserId - unqiue identifier for the user
4. ProfileName
5. HelpfulnessNumerator - number of users who found the review helpful
6. HelpfulnessDenominator - number of users who indicated whether they    found the review helpful or not
7. Score - rating between 1 and 5
8. Time - timestamp for the review
9. Summary - brief summary of the review
10. Text - text of the review
 
 
#### Objective:
Given a review, determine whether the review is positive (Rating of 4 or 5) or negative (rating of 1 or 2).
 
 
Question:How to determine if a review is positive or negative?
Answer:We could use the Score/Rating. A rating of 4 or 5 could be considered a positive review. A review of 1 or 2 could be considered negative. A review of 3 is neutral and ignored. This is an approximate and proxy way of determining the polarity (positivity/negativity) of a review.
 

**3. EDA and Data Cleaning**
Due to very limited processing power we are using only 100,000 data points. We choose our data points such that there are no neutral(rating=3) points. Also after checking for duplicate values we figure out there are no missing values in our data.
 
After we check the distribution of classes we find that our data is Imbalanced with 85 percent positive and 15 percent negative reviews.
 

**4. Data Featurization:** We are using tf idf-word2vec to featurize our two features. Text and Summary.

Using tf-idf and word2vec: We are using tf idf to give more importance to the words that occur rarely but are very important in sentiment analysis and we are using word2vec to preserve the semantic meaning of words and placing similar words closer to each other.

**5. Performance Metric:** We are using ROC-AUC as our performance metric. Since our data is imbalanced AUC is the right metric to check the performance of the model.

**6. Predictive Modelling:** We are using Logistic Regression, Random Forest and LSTM for predictive Modelling. Below Table portrays the performance of our model.


**Model**

**Logistic Regression**
ROC-AUC Score- 0.904

**Random Forest**
ROC-AUC Score- 0.888

**LSTM**
ROC-AUC Score- 0.910


**7. Results:** From the above results we infer that Logistic Regression and LSTM performs equally well on the data.
