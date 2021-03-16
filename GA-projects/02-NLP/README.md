# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP 

# READ ME/ EXECUTIVE SUMMARY 

## Problem Statement:

Here at Reddit Marketing,

The Data Science team has been tasked with using NLP to train a classifier that can predict which subreddit a post came from.

The C-level executives would like to know what are the top words that have the most predictive value in our model so they can better advise their clients who work in the relationship/therapy space on how they can attract more clients who need their services. 


We will accomplish this task by using push shift API to web scrape, then train a classification model that will predict where our posts have come from.

For this project, we will focus on using two models; Logistic Regression and Naive Bayes.

Success will be evaluated based on the accuracy of either model in predicting accurately which subreddit a given post came from.

We will be presenting our findings to these executives  who may be interested in helping their clients to run some marketing campaigns to a targeted audience.

Let's dive in!

---

### Data Collection:

- In this step, I will collect data from reddit using pushshift API and requests library. 
- I have written a while loop function that allows me to pull data from August 1st - Wednesday August 26th 2020 until we have 8500 rows worth of data for each subreddit. 
- While this may seem like a short span, we've generated at least 17000 rows worth of data in total. 
- We will be cleaning in a few which will reduce this number, but I believe we have a good amount of data to work with here.
---

### Next Steps EDA:

- We're going to drop a few columns that won't add much value to our model. Mainly because most of these columns do not have enough useful data
- Then I'll use a .map function to change my subreddit columns to 0 for 'relationship_advice' and 1 for 'confession' 
- We'll then give some summary statistics about our data and then concat both data frames in to one.
- Then we will find some relationships in our data before we begin our next step; Preprocessing!

---

### Preprocessing:

- In this step we will be converting our text data into a matrix representation.
- We will be imploring our regex, tokenize, stemmatize and lemmatize functions and apply it to our data.
- Regex will allow us to find patterns in our data that we may possibly want to delete. We will then need to convert our data to a huge string in order to 
- This will help in converting our chosen column ('title').

---
### Modeling:

- Now we've done some preprocessing, let's go ahead and model our data! 
- We will be creating a Naives Bayes(Multinomial model) and a Logistic regression model and then compare our results.

### Results of Logistic Regression Model:

**New Results with Grid Search CV**

- By adding some more features, we were able to increase our Training and testing score to 95% and 85% respectively.
- Our accuracy score is 85.22%
- This means that our model can correctly predict which subreddit a given post is coming from about 85% of the time on unseen data  
- I did play around with a few features and got this to be the best result. 
- While it scored a bit higher on our training data, it did go a good job of scoring way above our base line so we will keep this score and evaluate our next model; Naive Bayes!
--
### Naive Bayes Model Results:
So what does this model tell us?

- On our traning and testing sets, the NB model scored 87% for training set and 84% for our testing set.
- This is a much closer bias-variance trade off than our logistic regression model.
- As far as accuracy goes, it correctly predicted which post a subreddit was coming about 84.94% of the time and misclassified a post about 15% of the time.

### Evaluation of Models

So which model performed better?

- This would depend on what we are looking to evaluate. 

- While we generally hold the notion that all models are wrong, some are actually quite useful. 

- We started with a baseline score of 52% relationship advice, to 47% confession and we were able to draw an accuracy score  between 84-85% on our models

- ***Since our main focus is on what classifer predicted more accurately, Logistic Regression has the slight edge over the Naives Bayes Model but not by much. Logistic regression came in at 85.2% accuracy and Naive Bayes was about 84.94%***


- I believe the methods used in both models (as outlined above) helped with increasing the score of our model. As mentioned, our model does suffer from a slight overfitting issue( especially within our Logistic Regression model) but with the help of grid search and adding specific parameters,we were able to cobmant this issue a bit more.

- We see the biggest difference in lowered bias-variance trade off in the NB model.

---

### Conclusions and Recommendations:

- Being that our level of success was based on accuracy we can say that our models were successful in predicting past the baseline models. 

- We applied several methods like count vectorizing, and grid searching to tune our parameters. 

- As far as the predictor words our clients would be interested in, we've listed the top 20 words that appeared within the titles. 

- Some of our top predictor words were "relationship", "feel", "friends", "boyfriend" "girlfirend", "years", and "help" so we can suggest to our clients that these are some of the words we can add to a targeted campaign to solicit new customers for them.

- As future steps are concerned, we can apply this modeling process to other types of subreddits that are within the interest of our clients in order to find more predictive words that can be used in a marketing context.

Thank you!


---







