# Fake news analysis & classifier

## About

This is the mini project for NTU-SC1015 (Introduction to Data Science and Artificial Intelligence).

Due to the COVID-19 pandemic, the spread of fake news has been increasing. Therefore, our team decided to focus on analyzing fake news.

## Problem definition

- What are the textual differences between fake news and real news?
- Are we able to detect fake news through the title alone?
- Are we able to detect fake news through the result of various NLP modelling techniques? (Sentiment, emotions, text length etc) If so, what are the telltale indicators? 

## Dataset used
The dataset used for this project is retrieved from [here](https://www.kaggle.com/c/fake-news)

For the cleaned dataset, please download it from [here](https://drive.google.com/file/d/1asgxcQTREf-sDYe1p71gmoY7G2fqFQyJ/view?usp=sharing)

## Presentation
The presentation video can be found [here](https://www.youtube.com/watch?v=kcXan2_hB1g)

## Brief process walkthrough (In order)

1. [Data Preparation & Cleaning](<Data Preparation & Cleaning.ipynb>)
    - Data cleaning
      - Salvage empty rows
      - Removal of numbers & symbols (Excluding punctuation)
      - Removal of stopwords
      - Word stemming
      - Drop empty rows after all cleaning steps (Dirty data)
    - Data generation
      - Word count & char count
      - Stopwords count
      - Sentiment
      - Emotions
      - Parts-of-speech (POS)

2. [Exploratory Data Analysis](<Exploratory Data Analysis & Visualization.ipynb>)
   - Class analysis
   - Wordcount & charcount analysis
   - Author analysis
   - Corpus analysis
   - N-gram analysis
   - Sentiment & emotion analysis
   - Parts-of-speech (POS) analysis
   - Correlation analysis

3. [Model Training Attempt 1 & 2](<Model Training Attempt 1 & 2.ipynb>)
   - Attempt 1 (Decision Tree)
     - Train with top 5 predictors
     - Average accuracy: 0.73
     - Model evaluation
       - Plotting decision tree
       - Confusion matrix
   - Attempt 2 (Random Forest)
     - Train with top 5 predictors
     - Average accuracy: 0.75
     - Model evaluation
       - Confusion matrix
       - Grid search hyper-parameter tuning

5. [Model Training Attempt 3](<Model Training Attempt 3.ipynb>)
   - TF-IDF analysis 
   - Attempt 3 (Logistic Regression)
     - Train with only title
     - Average accuracy: 0.93
     - Model evaluation
       - Confusion Matrix
       - Recall, precision, F1 score
       - Receiver Operating Characteristic (ROC) Curve & Area Under Curve (AUC)
       - Model weights

## Conclusion
- Surprisingly, polarity & emotions does not have a strong relation to fake news, therefore, not a good indicator of fake news.
- Instead, indicators such as title wordcount, title adjective count, and text stopwords count are the best indicators to fake news. 
- Based on attempt 3, detection of fake news using title is sufficient. However, for the best results, author & title are required.
- Out of all the 3 models we implemented, decision tree performed the worst while logistic regression performed the best.
- Based on findings, we can suggest that from a reader's perspective in identifying fake news, author is a quick & credible identifier, and the title could further support a reader's attempt in identifying fake news.

## Key learning points
- NLP & Text processing techniques
  - Removal of stopwords
  - Removal of noisy data (Numbers & symbols)
  - Word stemming
  - Sentiment & emotion analysis
  - Parts-of-speech (POS)
  - N-gram analysis (Bi-grams)
- Logistic regression model training & evaluation
- Converting unstructured text into text vectors using TF-IDF scoring metric
- Using Python libraries with pre-trained models to predict and generate emotions & sentiment
- Plotting correlation matrix with categorical data


## Contributors

1. @ao9000 (Adrian Ong) - Data Preparation & Cleaning, Exploratory Data Analysis, Model Training Attempt 3
2. @jeremyxgch (Jeremy Goh) - Model Training Attempt 1 & 2, Presentation Slides, Presenter
3. @Hasterwfsc (Nigel Chok) - Model Training Attempt 1 & 2, Presentation Slides, Presenter

## References

- https://data-flair.training/blogs/advanced-python-project-detecting-fake-news/comment-page-2/
- https://towardsdatascience.com/logistic-regression-and-decision-boundary-eab6e00c1e8
- https://towardsdatascience.com/decision-trees-explained-3ec41632ceb6
- https://towardsdatascience.com/better-heatmaps-and-correlation-matrix-plots-in-python-41445d0f2bec
- https://towardsdatascience.com/evaluating-performance-of-models-8d5c3ca6f8cf
- https://medium.com/@knoldus/how-to-find-correlation-value-of-categorical-variables-23de7e7a9e26
- https://www.datacamp.com/community/tutorials/text-analytics-beginners-nltk
- https://www.nltk.org/howto.html
- https://towardsdatascience.com/tf-idf-for-document-ranking-from-scratch-in-python-on-real-world-dataset-796d339a4089
- https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html