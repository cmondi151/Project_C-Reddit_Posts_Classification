## Colin Mondi - Reddit Posts Classification

### Problem Statement

Subreddit feeds often include user posts that violate community norms, rules, and polices. Although there is a process in place to remove these types of posts, the turnaround time can be slower than expected giving more viewers time to read the content. To fix the issue Reddit is looking for a way to pre-determine which subreddits are most likely to contain these types of bad posts.

The first step in the process is to determine which subreddit an individual post originated from using post content alone, leading to new discoveries regarding patterns/trends in topic discussion boards. This capability not only identifies bad content but can predict beforehand where it is most likely to occur. Specific subreddits can be closely monitored therefore increasing turnaround time in post removal. But going back to the first step, is there a way to even link individual posts to subreddits based on some words written by bunch of lunatics?!?!

### Overview

For this project I chose two sub-reddits, both with topics on strategies involving fantasy sports. r/fantasyfootball includes content on fantasy football while r/dfsports includes content on daily fantasy challenges across all sports (not just football). I utilized the reddit Pushshift API to extract & reconcile post content from the two subreddit feeds. Using the merged data set, I tested two prediction models; Logistic Regression & Naive Bayes. I received the best results from Naive Bayes using a combination of the Multinomial Naive Bayes Classification Model & CountVectorizer Feature (via pipeline). The goal of this project is to predict which subreddit an individual post originated from only using post content alone.

### Modeling

I created two different types of "post-to-subreddit" prediction model; Logistic Regression and Naive Bayes. Here's what I found regarding the comparison of results between the two:

- Logistic Regression has slightly better R² (0.90 vs 0.89) and RMSE (0.31 vs 0.32) values
- Logistic Regression is overfit due to the higher train score (0.96) in comparison to both the test score (0.90) and k-Fold cross val score (0.86)
- Naive Bayes has almost identical scores for all three (0.89) indicating the model is fit fairly well
- Logistic Regression has a better accuracy rate for predicting r/dfsports posts (92% vs 91%)
- Naive Bayes has a better accuracy rate for predicting r/fantasyfootball posts (87% vs 84%)
- Naive Bayes has a more balanced test result regarding accuracy rate for predicting both subreddit posts; on the other hand, Logistic Regression performed much better for predicting r/dfsports posts in comparison to predicting r/fantasyfootball posts

### Conclusions and Recommendations

To summarize, both models successfully predicted the correct subreddit a post originated from for majority of cases. 

Although the Logistic Regression model has slightly better R-squared score and RMSE value, the difference in both metrics is too close to draw any conclusions. But the train, test, and k-Fold cross val scores for the Logistic Regression model indicate overfitting, while this is not the case for the Naive Bayes model. Given this, I believe the Naive Bayes model is the better option for the task at hand.
