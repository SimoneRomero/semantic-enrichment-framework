# Improving the Classification of Events in Tweets using Semantic Enrichment

Details of the proposed semantic enrichment framework for event classification in tweets are presented in the paper submitted to the 14th ESWC 2017. In this online appendix, we present important results that could not be inserted in the paper due to space limitations.


### Using the Semantic Enrichment Framework for event classification in tweets

The figure below presents the results of the experiments performed using the seven event target datasets, all types of features (i.e. TERMS, NER, and ALL), and the WP/PR/PR+CFS combinations (i.e. without pruning, using only the Semantic Feature Pruning algorithm, and the application of the Semantic Feature Pruning algorithm in combination with the CfsSubsetEval feature selection technique).

For the classification, we used the algorithms available in Weka (version 3.8.0): Naive Bayes (NB) and an implementation of SVM called Sequential Minimal Optimization (SMO), with PolyKernel, since it is quite popular on Natural Language Preocessing (NLP) applications. We compared the results using F-measure (F), Precision (P) and Recall (R) metrics. We also used the Weka's default parameters and 5-fold cross-validation.


![alt tag] (https://cloud.githubusercontent.com/assets/5015987/22629606/27508d88-ebd0-11e6-88b0-5fa3a237d779.PNG)


### Using word embeddings for event classification in tweets

We adopted as the baseline a word embeddings based approach, which considers the co-occurrence of the words from the vocabulary encoded as real-valued vectors in a dimensional space. The distance between these vectors can be used to represent the semantic similarity between the  words within a domain (e.g. 'flood', 'rain' and 'storm' would have close embeddings). We choose this approach since it captures the syntactic and semantic characteristics of a word, allowing their representation in different contexts. Further, word embeddings can be considered as a primitive form of contextual enrichment, which allows us to compare our semantic enrichment approach to another kind of contextual enrichment. 

For the experiments, we used a pre-built word embeddings model trained over 2 billions tweets, representing a 1.2 millions vocabulary, which was trained using GloVe. We employed a model built in a 50-dimension space. Regarding the word features, we applied the mean technique, in which we calculate the mean of all word vectors recognized for each term in a tweet. Thus each tweet has been encoded into a unique vector representation, containing a 50-dimensional array. For the classification, we employed the supervised algorithms NB and SVM in a 5-fold cross-validation configuration.

The figure bellow shows the results of the word embeddings approach for event classification.
![alt tag](https://cloud.githubusercontent.com/assets/5015987/22621991/66098ba6-eb17-11e6-9ac9-4bb6125df72d.PNG)

### Performance Comparison

We compared semantic enrichment according to our approach against the use of word embeddings as a means of incorporating contextual information to tweets. Word embeddings-based approaches have been widely used for text classification, since they capture syntactic and semantic characteristics of a word and from the knowledge provided by co-occurrence statistics [10, 11]. Our results show the advantages of using external and semantic enrichment for event classification in tweets, outperforming the baseline in 96.5% of the cases.

We validate our results for each metric through a statistical test, using two-tail paired _t-test_. For the comparison, we analyzed each dataset variation and classifier against the baseline built using word embeddings. We claim the improvement is _significant_ with significance level of _alpha_ = 0.05, and _very significant_ if  _alpha_ = 0.01. 

The figures bellow show the results for NB and SVM algorithm classifiers, respectively.

Our semantic enrichment framework statistically outperformed the baseline in 94% of the cases.
