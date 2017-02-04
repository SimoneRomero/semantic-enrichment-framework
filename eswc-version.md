# Improving the Classification of Events in Tweets using Semantic Enrichment

### Results of the experiments, using the Semantic Enrichment Framework

#####TO-DO

### Using word embeddings for event classification in tweets

We adopted as the baseline a word embeddings based approach, which considers the co-occurrence of the words from the vocabulary encoded as real-valued vectors in a dimensional space. The distance between these vectors can be used to represent the semantic similarity between the  words within a domain (e.g. 'flood', 'rain' and 'storm' would have close embeddings). We choose this approach since it captures the syntactic and semantic characteristics of a word, allowing their representation in different contexts. Further, word embeddings can be considered as a primitive form of contextual enrichment, which allows us to compare our semantic enrichment approach to another kind of contextual enrichment. 

For the experiments, we used a pre-built word embeddings model trained over 2 billions tweets, representing a 1.2 millions vocabulary, which was trained using GloVe. We employed a model built in a 50-dimension space. Regarding the word features, we applied the mean technique, in which we calculate the mean of all word vectors recognized for each term in a tweet. Thus each tweet has been encoded into a unique vector representation, containing a 50-dimensional array. For the classification, we employed the supervised algorithms NB and SVM in a 5-fold cross-validation configuration.

The figure bellow shows the results of the word embeddings approach for event classification.
![alt tag](https://cloud.githubusercontent.com/assets/5015987/22621991/66098ba6-eb17-11e6-9ac9-4bb6125df72d.PNG)

##### Performance Comparison

We validate our results for each metric through a statistical test, using two-tail paired _t-test_. For the comparison, we analyzed each dataset variation and classifier against the baseline built using word embeddings. We claim the improvement is _significant_ with significance level of _alpha_ = 0.05, and _very significant_ if  _alpha_ = 0.01. 

The figures bellow show the results for NB and SVM algorithm classifiers, respectively.
![alt tag](https://cloud.githubusercontent.com/assets/5015987/22621966/ffc27bd2-eb16-11e6-8656-a25ba8c5719e.PNG)
![alt tag](https://cloud.githubusercontent.com/assets/5015987/22621967/ffed7ff8-eb16-11e6-8639-f6e3eddcb37e.PNG)

Discussion about the results are detailed in the paper.


