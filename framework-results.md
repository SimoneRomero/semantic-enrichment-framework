
# Improving the Classification of Events in Tweets using Semantic Enrichment

In this online appendix, we present important results that could not be inserted in the paper due to space limitations.


### Using the Semantic Enrichment Framework for event classification in tweets

In this section, we present the results of the experiments performed using the seven event target datasets, all types of features (i.e. TERMS, NER, and ALL), and the WP/PR/PR+FS combinations (i.e. without pruning, using only the Semantic Feature Pruning algorithm, and the application of the Semantic Feature Pruning algorithm in combination with the CfsSubsetEval feature selection technique).

For the classification, we used the algorithms available in Weka (version 3.8.0): Naive Bayes (NB) and an implementation of SVM called Sequential Minimal Optimization (SMO), with PolyKernel, since it is quite popular on Natural Language Processing (NLP) applications. We compared the results using F-measure (F), Precision (P) and Recall (R) metrics. We also used the Weka's default parameters and 5-fold cross-validation.

As the baseline, we considered only textual features. The baseline is composed by all alphabetic uni-grams extracted from each tweet dataset, without normalized symbols (i.e. T\_USER, T\_EMOT, and T\_URL).  Using a straightforward technique as the baseline, we can focus on the analysis of the contribution of our semantic enrichment approach in the classification of event-related tweets.

Next, we present the results of the application of each combination for the seven event target datasets, compared to a textual features only baseline. In these tables, we present the results for the positive class of each metric. The results depicted with (\*) represent that the baseline is statistically superior, whereas the (v) symbol means that the combination analyzed is statically superior against the baseline. Otherwise, there is no statistic difference between the results. 

The figure below shows the results for NB and SMO algorithm classifiers, considering the WP combination, for the positive class.
![alt tag] (https://cloud.githubusercontent.com/assets/5015987/23714901/a315d0e4-0409-11e7-9284-597a3a733596.PNG)

The figure below shows the results for NB and SMO algorithm classifiers, considering the PR combination, for the positive class.
![alt tag] (https://cloud.githubusercontent.com/assets/5015987/23714898/a3128e98-0409-11e7-9ce6-2d60d3932957.PNG)

The figure below shows the results for NB and SMO algorithm classifiers, considering the PR+FS combination, for the positive class.
![alt tag] (https://cloud.githubusercontent.com/assets/5015987/23714899/a313f1c0-0409-11e7-9ce7-d45b3f5046ae.PNG)

The same results are also presented for the weighted metric.

The figure below shows the results for NB and SMO algorithm classifiers, considering the WP combination.
![alt tag] (https://cloud.githubusercontent.com/assets/5015987/23714902/a3167a62-0409-11e7-813c-3c7aa77942fd.PNG)

The figure below shows the results for NB and SMO algorithm classifiers, considering the PR combination.
![alt tag] (https://cloud.githubusercontent.com/assets/5015987/23714904/a3a63422-0409-11e7-9a68-58e07a20ddab.PNG)

The figure below shows the results for NB and SMO algorithm classifiers, considering the PR+FS combination.
![alt tag] (https://cloud.githubusercontent.com/assets/5015987/23714900/a314caf0-0409-11e7-9e28-7e4d6f594eab.PNG)



### Using word embeddings for event classification in tweets


We performed the event classification in tweets using a word embeddings based approach, which considers the co-occurrence of the words from the vocabulary encoded as real-valued vectors in a dimensional space. The distance between these vectors can be used to represent the semantic similarity between the words within a domain (e.g. 'flood', 'rain' and 'storm' would have close embeddings). We choose this approach since it captures the syntactic and semantic characteristics of a word, allowing their representation in different contexts. Further, word embeddings can be considered as a primitive form of contextual enrichment, which allows us to compare our semantic enrichment approach to another kind of contextual enrichment. 

For the experiments, we used a pre-built word embeddings model trained over 2 billion tweets, representing a 1.2 millions vocabulary, which was trained using GloVe. We employed a model built in a 50-dimension space. Regarding the word features, we applied the mean technique, in which we calculate the mean of all word vectors recognized for each term in a tweet. Thus each tweet has been encoded into a unique vector representation, containing a 50-dimensional array. For the classification, we employed the supervised algorithms NB and SVM in a 5-fold cross-validation configuration.

The figure below shows the results of the word embeddings approach for event classification.
![alt tag](https://cloud.githubusercontent.com/assets/5015987/22621991/66098ba6-eb17-11e6-9ac9-4bb6125df72d.PNG)

### Performance Comparison

We compared semantic enrichment according to our approach against the use of word embeddings as a means of incorporating contextual information to tweets. We calculated the difference between the correspondent combination of our approach (i.e. TERMS/NER/ALL, WP/PR/PR+FS, and NB/SVM) and the word embeddings results. The results show the advantages of using our external and semantic enrichment approach for event classification in tweets, outperforming the baseline in 96.5% of the cases.

Then, we validate our results for each metric through a statistical test, using two-tail paired _t-test_. For the comparison, we analyzed each dataset variation and classifier against the baseline built using word embeddings. We claim the improvement is _significant_ with a significance level of _alpha_ = 0.05, and _very significant_ if  _alpha_ = 0.01. 

The figure below shows the results for NB and SVM algorithm classifiers, considering the WP configuration.
![alt_tag](https://cloud.githubusercontent.com/assets/5015987/22630191/40930f58-ebdc-11e6-80a8-535cdebff48f.PNG)


The figure below shows the results for NB and SVM algorithm classifiers, considering the PR configuration.
![alt_tag](https://cloud.githubusercontent.com/assets/5015987/22630192/40934626-ebdc-11e6-92f2-39a8201073e3.PNG)

The figure below shows the results for NB and SVM algorithm classifiers, considering the PR+CFS configuration.
![alt_tag](https://cloud.githubusercontent.com/assets/5015987/22630190/408fe774-ebdc-11e6-818c-7e062a94f211.PNG)

Considering these results, our semantic enrichment framework statistically outperformed the baseline in 94% of the cases.
