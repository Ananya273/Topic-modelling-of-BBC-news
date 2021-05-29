# BBC News Topic Modelling with Gensim MALLET LDA
This project aims to classify various BBC news articles into their respective genres. This is an application of Topic Modelling in NLP using the LDA package of Gensim. After determining the accuracy of the model using this technique, we have also used the Mallet library to furthur improve the metrics.

**Datasets**

* bbc_data.csv
  * news- news content 
  * type- genre of news
  
**Exploratory Data Analysis**
  * Calculate the number of articles in each genre of news articles and convert them to a list
   
**Data Preprocessing**

  * Used `re` python package and `simple_preprocess` package in `Gensim` for tokenising and creating n gram models
  
  * Used `Spacy` for lemmatisation  
  
  * Calculated `TF-IDF` of words using Gensim.
  
**Training the model using Gensim LDA**

  * Used `LDA Model` package to train data for topic modelling.
  
  * Calculated the perplexity and coherence score of the model
  
  * *Perplexity is -7.8 and coherence score 0.39*
 
 **Training the model using Gensim MALLET**
 
  * Used 'LDAMallet' package to train data.
  
  * *Coherence score is 0.501*

  
  
  
