# Project_3 : Web APIs & Classification

__________________________________________________________________________________________________________________

# Problem Statement

1. Finding the word that is the most likely to use in each subreddit (marvelstudios & DC_Cinematic).
2. Application to use for analysis text or message from chat or Email and classify them ?
3. Examine the performance of various techniques employed for classification.

__________________________________________________________________________________________________________________

# Steps of working

1. Scraping the data from Reddit in the subreddit of "marvelstudios" and "DC_Cinematic"
2. Cleaning the data by
    - Regular Expression
    - Remove Stop words
    - Lemmatizing
3. GridSearchCV : Find the best model compare with testing score then I use the best model to classify and predict the new text from input.
    - **Model 1** : CountVectorizer + MultinomialNB (Testing Score = 0.9337)
    - **Model 2** : CountVectorizer + Logistic Regression (Testing Score = 0.9401)
    - **Model 3** : TF-IDF Vectorizer + MultinomialNB (Testing Score = 0.9316)
    - **Model 4** : TF-IDF Vectorizer + Logistic Regression (Testing Score = 0.9465) >> **Best Testing Score**
4. Evaluate Model 4 (The best model) : It has the accuracy about 95%. Mainly, model predicts to 'DC_Cinematics' more accurate than 'marvelstudios' with 97% and 93% respectively because DC_Cinematic has the number of data more than marvelstudios.
5. Prediction the new text and classfication it.

__________________________________________________________________________________________________________________

# Data Dictionary

| Columns | Description |
|---|---|
|name |Name of 'after' |
|title |Title of each post in Reddit |
|selftext |Text or message of each post in Reddit |
|subreddit |Name of subreddit |
|title_regex |Title with Regular Expression |
|title_regex_split |Split title after Regular Expression |
|title_regex_rmstop |Remove stop words |
|title_regex_lem |Lemmatizing |
|title_regex_onestring |Combine words to one string |

_________________________________________________________________________________________________________________

# Conclusion

1. Top 5 popular words of “marvelstudios” are “mcu, wandavision, falcon, winter and soldier. Top 5 of “DC_Cinematic” are “discussion, snyder, zsji, humor and league.  
2. From EDA, I found the abnormal popular words of “DC_Cinematic”. So in the step of gathering the data, we need to check the form of source and try to understand it.
3. The model (TF-IDF) can predict with good accuracy to classify the subreddit. 
4. Can apply to use in real working to classify text from chat or Email.
