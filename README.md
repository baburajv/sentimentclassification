# Sentiment Classifiction Project Overview
  In this project, a labelled test set is provided with text snippets labelled as either "Positive" or "Negative" sentiments. The model is trained based on this input data 
  to predict the sentiments of the text snippets in the test set.  The test set provided has numeric ids and text snippets, which is used for predicting the outcome. The output
  will be having id and the prediction whether the sentiment is "Positive" or "Negative.
  
## Participants
   Baburaj Velayudhan
   bvelayudhan@vmware.com
   CMBU
   
## Summary   
   The input text data is cleaned to remove any @mentions, URLs, hashtags, punctuations, html etc and a train and test split is created for validating the trained model.
   In an attempt to know the most common words used in Negative and Positive sentiments, a wordcloud representation is created and a plot is creatd with  most commonly 
   used words in Positive and Negative sentiments.  Top 10 words that are most frequently used in both are added to a custom stop word list
   
   MultinomialNB with CountVectorizer and TfidfVectorizer:
   
   As a first step, CountVectorizer is used with MulinomialNB classifier on unigrams. The model accuracy is computed for number of feature ranging from 1 to 10000 with
   stop words, without english stop words and without a combination of english and custom stop words. The results indicate that model has highest accuracy 
   with stop words and 4000 features. The same is done using bi-grams and tri-grams with feature count ranging from 1 to 100000. The results indicate that accuracy is high with    10001 features. A classification report for bigram and trigrams indicate almost same accuracy of 75% and f1- score of 70 for Negative and 71 for Positive cases.
   The process is repeated with TfidfVectorizer and MultinomialNB. However, the accuracy drops to 74% for unigram model and 71% for bi-grams and tri-grams
   
   LinearRegression with CountVectorizer and TfidfVectorizer:
   The same process is repeated with LinearRegression model and it shows that the tri-gram accuracy remains at 75%.
   
## Feature Selection
How did you select features for your analysis? Describe any feature transformations or feature engineering you performed prior to your analysis.

## Training methodology
Describe the training method(s) you used, including any ensemble approaches, if applicable.

## Notable aspects
Describe any tricks or interesting aspects of your solution that you think may have improved your model accuracy.

## References
   The data cleaning and model training approach is highly infiuenced by the Ricky Kim's article published in 
   https://towardsdatascience.com/another-twitter-sentiment-analysis-bb5b01ebad90
   
   I have adopted the techniques for data cleaning and model training as mentioned in the article.
   

### python and library versions
    Python:3.7.6
    sklearn:0.22.1
    numpy: 1.18.1
    seaborn:0.10.0
    Beautiful Soup: 4.8.2
    Matplotlib: 3.1.3
    pandas: 1.0.1
    wordcloud: 1.7.0
    NLTK: 3.4.5
