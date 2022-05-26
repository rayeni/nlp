# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP

### Overview

This project is a demonstration of the different classifiers that were learned in week four and the webscraping APIs, and Natural Language Processing (NLP) that were learned in week five.


### Problem Statement

Use the Pushshift API to collect text data (posts) from two subreddits that focus on financial investing and trading.  After collecting the data, do the following:

> - Use NLP techniques to train various models to analyze a subset of the data.
> - Test how well the various models classify posts.  

The two classes correspond to the two subreddits from which the data was collected. 

>  Class 0: Subreddit r/pennystocks
>  Class 1: Subreddit r/CryptoCurrency

---

### Datasets

#### Data Used in Analysis

The PushShift API was used to download the data from Reddit.  To facilitate easy access to data for later use, they were saved in the following files:

* [`sr_posts_dirty.csv`](./data/sr_posts_dirty.csv): Raw data downloaded from Reddit.

* [`sr_posts_clean.csv`](./data/sr_posts_clean.csv): Clean data produced from raw data downloaded from Reddit.  

#### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**selftext**|*string*|sr_posts_clean.csv|post to be analyzed and classified| 
|**word_count**|*int*|sr_posts_clean.csv|Number of words in post|


---

### Analysis Summary

Four classification models (Naive Bayes, Random Forest, Simple Vector Classifier, and AdaBoost) were fitted to the data and evaluated.  Of the four models, I recommend Random Forest (RF), because it had the lowest variance (0.0066) between its training (0.8523) and test (0.8457) RMSE scores.

In addition to best classifying new data, RF also attained the highest sensitivity (a measure of the true positive rate) score of 0.9488.  In terms of specificity (a measure of the true negative rate), the model didn't do well (0.7433), in comparison to the other models (0.8035, 0.9085, and 0.9548).

---

### Conclusions/Recommendations 

- The all models could have performed better if more attention were given to eliminating stop-like words.

- An increase in the number of observations improved the scores of all models.  Initially, a sample size of 4000 observations were collected.  The scores improved after the sample size was increased to 15,000 observations.

- Finding the best hyperparameters is dependent on time and compute resources, and can lead to improved model performance.

---
