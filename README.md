# TEXT CLASSIFICATION OF HEAVILY IMBALANCED DATA USING SIMILARITY BASED APPOACHES


The modern text classification approaches uses the combination of two documents to classify them for their relation(label). Even though they are performing well, this project attempts to find few alternative approaches which uses similarity of independent document and classify the labels. 

- Data is collected from "WSDM - Fake News Classification"(https://www.kaggle.com/c/fake-news-pair-classification-challenge)
- NLP library used 
  1. SpaCy(https://spacy.io/)
  2. Gensim(https://radimrehurek.com/gensim/)

- Vectorizers:
  1. Term Frequency - Inverse Document frequency(TF-IDF) Vectorizer 
  2. Count Vectorizer

- **Preprocessing of text**
  1. Tokenized
  2. Lemmatized
  3. Removed stop words
  4. Extracted only alphabets


### Approaches used

* Context based Similarity - Topic Modelling 
   1. K-means Clustering
   2. Gaussian Mixture Model
   3. Latent Dirichlet Allocation

* Semantic based similarity - Embeddings
  1. Word2Vec embedding - Similarity score approach
  2. Transformer 
  3. Doc2Vec embedding


### Context based Similarity:

Each article from 'title1_en' are clustered independently. Similarly, each article from 'title2_en' are clustered independently. If both articles from a single row belong to same cluster, then they are related. Else, they are unrelated. Here, articles are clustered based on distance between word in it's respective vectorized form, which is tells about  the similarity. If article from 'title2_en' also fall in same cluster, it means that the distance between two articles should less in the vector space and the two articles are 'related'. This idea is carried forward and clustering approaches like K-means, Gaussian Mixture Model and Latent Dirichlet Allocation are used to model the topic(Cluster) and later compared with each other.

### Semantic based Similarity:

Semantic based similarity is a distance or cosine based similarity index but here, each word of the document or each document is embedded and then vectorized. This approach focuses on representing data as a Continuous Bag of words where each document from article A and article B is transformed as a vector and check the Cosine Similarity between them.  Two documents are 'related' when cosine similarity is high. Else they are 'unrelated'. This idea is checked with Simple similarity calculation of Word2Vec, Transformer which sums up all the word vectors and Doc2Vec approaches.


### Results:

This experiment proves that context based similarity is not ideal for classification of text data. However, Semantic based similarity is working great. This can be improved by using LSTM or BERT to make more accurate predictions
