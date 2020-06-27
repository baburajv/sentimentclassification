"""
# SENTIMENT CLASSIFICATION PROJECT OVERVIEW

    In this project, a labelled test set is provided with text snippets labelled as either "Positive" or "Negative". 
    The model is trained based on this input data to predict the sentiments of the text snippets in the test set. The 
    test set provided has numeric ids and text snippets, which is used for predicting the outcome. The output will 
    contain the id and predictions (positive or negative).

### Participants
    Baburaj Velayudhan
    bvelayudhan@vmware.com
    CMBU

### Summary   
    The input text data is cleaned to remove any @mentions, URLs, hashtags, punctuations, html etc and a train-test split 
    is created for validating the trained model. Using a wordcloud, the most common words in positive and negative 
    sentiments are identified. There are many common words in positive and negative sentiments.

    I have used MultinomialNB with CountVectorizer and TfidfVectorizer. To model accuracy is compared with a LogisticRegression
    model with CountVectorizer and TfidfVectorizer. Based on my trials, i have selected MultinomialNB trigram model for 
    final predictions.
   
### Feature Selection
    For feature selection, chi2 with SelectKBest with chi2 is used. The chi2 score is highest with 1707 features at 76.57% 
    accuracy for trigrams using Tfidf vectorizer.
   
### Training methodology
    MultinomialNB with CountVectorizer and TfidfVectorizer:
   
    As a first step, CountVectorizer is used with MulinomialNB classifier on unigrams, bigrams and trigrams. The model 
    accuracy is computed for feature count ranging from 1 to 10000 with and without Words. A trigram model showed high 
    accuracy with stop words. A classification report for bigram and trigrams indicate almost same accuracy of 75.53 % 
    and f1- score of 70 for Negative and 79 for Positive cases. The process is repeated with TfidfVectorizer and 
    MultinomialNB and observed that a trigram model wth tfidf had 76.58% accuracy with 1901 features
   
    LogisticRegression with CountVectorizer and TfidfVectorizer:
       The same process is repeated with LogisticRegression model and it shows that the bi-gram and tri-gram accuracy drops 
       from the previous trials.

    With the above, MultinomialNB was chosen with Tfidf maximum features of 1901 and a SelectKBest showed 76.57% accuracy 
    with 1707 features. The classification report showed 73% accuracy for negative and 79% accuracy for positive cases. 
    Hence this was chosen for predictions.

### Notable aspects
    Many terms were common in positive and negative sentiments. I believe, if such words were filtered out, the model accuracy
    would have improved a bit more.
    
### References
    The data cleaning and model training approach is highly infiuenced by the Ricky Kim's article published in 
    https://towardsdatascience.com/another-twitter-sentiment-analysis-bb5b01ebad90
   
### Assumptions
    (1) The input data file is located in the data subfolder and the filename is Export_loop-sentiment-pos-neg-train_05112020000000.csv
    (b) The test data file is located in the data subfolder and the file name is sentiment-eval.csv
    (c) The final predictions will be located in the data subfolder and the file name is preditions.csv
        
### python and library versions
        Python        : 3.7.6
        sklearn       : 0.22.1
        numpy         : 1.18.1
        seaborn       : 0.10.0
        Beautiful Soup: 4.8.2
        Matplotlib    : 3.1.3
        pandas        : 1.0.1
        wordcloud     : 1.7.0
        NLTK          : 3.4.5

"""
