## Classifying news articles into different genres using Topic Modelling

#### `gensim` `nltk` `lda` `mallet` `spacy` `pandas`  `numpy` `seaborn` `matplotlib`
 
Often various newspaper companies find it difficult to classify topics into their respective genres as it requires people to manually read the articles, thus making it time consusming. In this project, we aimed to solve this issue by using the technique of topic modelling.

We predominantly use the `Latent Dirichlet Allocation (LDA)` package provided by gensim as it treats documents as bag of words. It also assumes that all words in the document can be assigned a probability of belonging to a topic. Thus LDA helps determine the mixture of topics that a document contains.

Now let us discuss about how the data was collected. Through web scrapping the BBC official website, we created a dataset that contained news articles and their corresponding genre- sport, business, politics, tech and entertainment.

We then followed different pre-processing steps to clean the news data. These steps were-
* tokenising using `simple_preprocess` package
* removal of stopwords
* lemmatisation using `spacy`

We then created a dictionary to represent each word and their corresponding frequency of occuring in the articles. This was done using the `gensim corpora` library. This was used as input for the `ldamodel` function. 

The output was formulated as sum of probabilities as follows-
| Topic number |Formulation
|--|--|
| 0 |  '0.016*"say" + 0.016*"technology" + 0.015*"mobile" + 0.013*"phone" + 0.012*"user" + 0.011*"service" + 0.010*"firm" + 0.010*"computer" + 0.010*"music" + 0.009*"network"' |
|1|'0.040*"game" + 0.020*"player" + 0.018*"play" + 0.015*"year" + 0.011*"good" + 0.009*"first" + 0.009*"time" + 0.009*"take" + 0.009*"go" + 0.009*"win"'|
|2|'0.023*"say" + 0.021*"people" + 0.013*"make" + 0.010*"get" + 0.010*"work" + 0.010*"could" + 0.009*"go" + 0.008*"way" + 0.008*"would" + 0.007*"use"'|
|  3| '0.016*"system" + 0.011*"security" + 0.011*"test" + 0.010*"domain" + 0.010*"machine" + 0.009*"could" + 0.009*"site" + 0.008*"chip" + 0.008*"card" + 0.007*"computer"'|
|4| '0.045*"say" + 0.016*"would" + 0.010*"mail" + 0.009*"search" + 0.007*"could" + 0.006*"tell" + 0.006*"make" + 0.006*"campaign" + 0.006*"also" + 0.006*"government"|

From the above, we can find which words contribute the most to each topic. Example the top 10 words that contribute to the first topic are say, technology, mobile, etc. Upon careful observation we can find out what each topic refers to.
| Topic number |Genre
|--|--|
| 0 | tech |
|1|sports  |
|2|business|
|  3| entertainment |
|4| politics |
  
We calculate the metrics for determining the accuracy of the model through perplexity= -7.8 and coherence score= 0.39

To further improve the accuracy of the model we use the `LDAMallet` package.With this the coherence score is 0.501. A higher coherence score value indicates a more accurate model.

