# Introduction to Natural Language Processing
by Bonzanini

https://github.com/bonzanini/nlp-tutorial

> Discount Code for ebooks:
> packtpub.com/all with **PYDL1860**

# What is NLP
A crossover between **computer science** and **natural language processing**.

Formal vs Natural

> Examples of formal languages SQL

    SELECT name, address
    FROM business
    WHERE business_type = 'blaa'


> Examples of natural languages

    Tom went to the pub at eight o'clock

A formal language can have **syntactic errors** 

# NLP Applications
- Text Classification
- Text Clustering
- Text Summarisation
- Machine Translation
- Semantic Search
- Sentiment Analysis
- Question Answering
- Information Extraction

# Practical hands on
Starting with a short discussion between python env VS docker

# Exercise I: recipes_exploratory_analysis
1) Load word corpus
2) Tokenize the corpus
3) Analyze the token frequencies
> Check python.collections

The most common tokens are **stop words** (the , . a and ...)

One can get language specific stop words lists and punctiution lists. Removing
those from the token list will result in bette results.

4) Filter stop words

What we get now are many tokens which are variations of the same word
(Butter, butter, The, the)

Word preprocessing operations:
- lowercase
- Stemming (removing suffixes of words to get the base)
- synnonym matching


> Note: Difference between **term frequencies (TF)** and **document frequencies (DF)**
- term-frequencies ... how often a word appears in the whole corpus
- document-frequencies ... applying set() on the word frequencies of each document, this is the number of times a word appears in *different* documents.

### n-grams
An n-gram is a sequence of n adjacent terms.
It can be used to find common phrases

It will show which tokens come in a sequence of maximum token distance n.

# Exercise II: PyConUK talk abstract
Analyse 101 of abstract documents in order to get an overview of general content.

1) Load the dataset into a corpus
2) Visualize word frequencies with the library 'WorldCloud'
3) Perform some file loading preprocessing specific to the input file format

**Term Frequency (TF)**

    TF(term , doc) = count(term in doc)
    or
    TF(term, doc) = count(term in doc) / length(doc)

**Inverse Document Frequency (IDF)**
What is the weight/importance of this single term in the corpus

    IDF(term) = log(N / DF(term))
    IDF(term) = log(1 + N / DF(term))

# Text Classification
Type of classification tasks
- Binary:
- Multi-class: multiple classes, mutually exclusive
- Multi-lable: multiple classes, with multiple labels per word

# Exercise III: Text classification Generic

## Multi-Class
1) Generate some training and test data set
2) Vectorize the data sets based on their TF and IDF
3) For each data set entry you then get a vector with a single number per word.
4) Apply a SVM to classify the data set as either sport or none sport texts.

## Multi-Label

> Note: some training sets should contain elements that have 0 labels assigned
1) Encode the labels with a MultiBinarizer (one hot encoding for each label)

## SVM Type
**One Vs Rest**: SVM is a binary classifier and OvR will generate one classifier per class. Comparing if a data set is part of the class, or NOT.

**One vs One**: Do something like pair wise comparisons. It gets better results than OvR but it has N**2 comparisons versus N.

# Text Classification Evaluation 
How to evaluate the performance of the NLP Classifier?

## Precision vs Recall
Precision ... How many of those labeled green are really green
Recall ... How many of the green elements have been labeled green

accuracy ... correctly assigned elements / all elements

# Exercise IV: Text Classification Evaluation
> Notes: Check sklearn.metrics for different scores. f1, precision, recall

The precision and recall score is calculated per class. There are
two methods do compare the overall classification.

- **Micro-Average**: (with unbalanced classes)

- **Macro-Average**: (for equal important classes)

el5 : track and visualize the classification process
> Note: F1 as an aggregation (comparing different classifiers)


# Exercise V: Classification Retuers 21578
Most commonly used NLP data set.
Original 21578 news documents, are labeled with 90 classes, and split in 9000 training and 3000 training data sets. (50% of them are filtered by preprocessing)

> Note: in order to evaluate the classification process
## How to tune/improve results
- Build quantified measures
- Look at the miss classified samples
- Try to understand poor performance cases