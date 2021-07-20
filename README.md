### This is a Kaggle competition for Coleridge Initiative 

This competition challenges data scientists to show how publicly funded data are used to serve science and society. Evidence through data is critical if government is to address the many threats facing society, including; pandemics, climate change, Alzheimer’s disease, child hunger, increasing food production, maintaining biodiversity, and addressing many other challenges. Yet much of the information about data necessary to inform evidence and science is locked inside publications.

Now is the time for data scientists to help restore trust in data and evidence. In the United States, federal agencies are now mandated to show how their data are being used. The new Foundations of Evidence-based Policymaking Act requires agencies to modernize their data management. New Presidential Executive Orders are pushing government agencies to make evidence-based decisions based on the best available data and science. And the government is working to respond in an open and transparent way.

This competition will build just such an open and transparent approach. The results will show how public data are being used in science and help the government make wiser, more transparent public investments. It will help move researchers and governments from using ad-hoc methods to automated ways of finding out what datasets are being used to solve problems, what measures are being generated, and which researchers are the experts. Previous competitions have shown that it is possible to develop algorithms to automate the search and discovery of references to data. Now, Coleridge Initiative want the Kaggle community to develop the best approaches to identify critical datasets used in scientific publications.

**Disclaimer: I did not find the solution for this competition. Please check out the Leaderboard for winning notebooks. In this Capstone project, my focus is text processing and labeling: how to look for scientific articles in a body of text, process the raw text and subsequently classify them with predefined labels.**

# Business Statement

             - 1. Can natural language processing find the hidden-in-plain-sight data citations?

             - 2. Can machine learning find the link between the words used in research articles and the data referenced in the article?

# Methodology

In this competition, **natural language processing (NLP)** is used to automate the discovery of how scientific data are referenced in publications. Utilizing the full text of scientific publications from numerous research areas gathered from CHORUS publisher members and other sources, data scientists will identify data sets that the publications' authors used in their work.

The objective of the competition is to identify the mention of datasets within scientific publications. The goal in this competition is not just to match known dataset strings but to generalize to datasets that have never been seen before using NLP and statistical techniques.

For this project, the focus is text processing and labeling: we want to look for scientific articles in a body of text and subsequently classify them with predefined labels. This is a big challenge since sequence prediction is considered as one of the hardest problems to solve in the data science industry.

We will discuss how to approach any NLP problem with techniques like n-gram, sequence vector, and spaCy NER. We will look at:

1. Obtain Data
2. Data Scrubbing & Exploration
3. Data Annotation: Getting Train Sentences & Labels
4. Data Preprocessing
5. Feature Extraction
6. Part 1: Building n-gram Models
7. Part 2: Building RNN Models: Bidirectional LSTM & GRU Model
8. Part 3: Building CNN Model: sep-CNN Model
9. Part 4: Building spaCy NER Model
10. Prediction on Test Set
11. Prepare Submission Data


# The Deliverables

There are 5 deliverables for this project:

1. A well documented Jupyter Notebook containing any code and comments explaining it.


## Kaggle Kernels:

  **EDA:**
  https://www.kaggle.com/baotramduong/show-us-the-data-eda


  **N-gram Models:**
  https://www.kaggle.com/baotramduong/coleridge-initiative-n-gram-models

  **GRU:**
  https://www.kaggle.com/baotramduong/coleridge-initiative-gru

  **Bidirectional LSTM:**
  https://www.kaggle.com/baotramduong/coleridge-initiative-bidirectional-lstm

  **sep-CNN:**
  https://www.kaggle.com/baotramduong/coleridge-initiative-sep-cnn

  **spaCy NER:**
  https://www.kaggle.com/baotramduong/coleridge-initiative-spacy-ner

  **Capstone:**
  https://www.kaggle.com/baotramduong/coleridge-initiative-ngram-lstm-gru-spacy
  
2. An organized README.md file that describes the contents of the repository.

3. A short PowerPoint presentation (delivered as a PDF export) giving a high-level overview of the methodology used and recommendations for non-technical stakeholders. 

4. A Blog Post which can be found at: 

## Blogs:
  
  **Capstone:**
  
  https://baotramduong.medium.com/discover-how-scientific-data-is-used-for-the-public-good-with-natural-language-processing-d9f8825e1dcf
  
  **N-gram Models:**
  
  https://baotramduong.medium.com/natural-language-processing-nlp-with-n-gram-models-coleridge-initiative-f18d5714b492
  
  **Deep Learning Models:**
  
  https://baotramduong.medium.com/natural-language-processing-nlp-with-deep-learning-models-rnn-cnn-coleridge-initiative-928f8d003b6d
  
  **spaCy NER:**
  
  https://baotramduong.medium.com/spacys-ner-model-to-identify-scientific-datasets-a336bec6190a

5. A Video Walkthrough of my non-technical presentation, can be found at:

# Data Source

             - https://www.kaggle.com/c/coleridgeinitiative-show-us-the-data/overview
             - train.csv- CSV file contains metadata of the publications
             - train-JSON file contains publications that are referenced in train.csv
             - test-CSV file contains publications for testing purpose
             - sample_submission.csv-CSV file conatins publications IDs column and prediction columns

# Notebook Table of Contents

## Part I: EDA

<img src = '../main/Data & Figures/cleaned_label_wordcloud.png'>

<img src = '../main/Data & Figures/cleaned_label.png'>

## Part II: Modeling

### Summary of Findings

|#  |Model                            |Accuracy|CV  |Precision|Recall|F1  |
|---|---------------------------------|--------|----|---------|------|----|
|0  |CLF RandomForestClassifier       |0.75    |0.78|0.44     |0.45  |0.44|
|1  |CLF Linear Support Vector Machine|0.62    |0.62|0.21     |0.09  |0.11|
|2  |CLF MultinomialNB                |0.64    |0.62|0.25     |0.10  |0.12|
|3  |DL GRU                           |0.83    |-   |0.29     |0.33  |0.3 |
|4  |DL Bidirectional LSTM            |0.83    |-   |0.28     |0.31  |0.28|
|5  |DL sep-CNN                       |0.48    |-   |0.0      |0.01  |0.01|
|6  |spaCy NER                        |0.81    |-   |-        |-     |-   |

##  Recommendations

1. With supervised learning algorithms, large annotated data for training is required which are expensive and often take a lot of time. Future efforts could be dedicated on providing more effective deep transfer learning models and exploring appropriate data augmentation techniques (He et al., 2020).
2. Most neural models for sequence labeling do not scale well because when the size of data grows, the parameters of models increase exponentially, leading to the high complexity of back propagation. There exists need for developing approaches to balance model complexity and scalability (He et al., 2020).
3. Increasing access to confidential data presumed significantly increasing privacy risks. However, the country’s laws and practices are not currently optimized to support the use of data for evidence building, nor in a manner that best protects privacy. We need to improve data security and privacy protections beyond what exists today (US CEP, 2017).

##  Future Works

* Spend more time on gathering, cleaning and visualizing data
* Correct highly imbalanced dataset
* More focus on tweaking the hyper-parameters
* Learn techniques from winning solutions:

**1st Place Winning Notebook (0.576):**

https://www.kaggle.com/dathudeptrai/biomed-roberta-scibert-base

https://www.kaggle.com/suicaokhoailang/submit-gpt-spacy?scriptVersionId=66488765

* Context Similarity via Deep Metric Learning
* A shared Bert model for extract Context Embedding and Sequence Tokens Embedding
* An ArcFace Loss for training Mask/NoMask Embedding
* A BCE loss for training NER model to detect dataset citation in the input string
* Text extraction model with CLM backbone and beamsearch GPT

**2nd Place Winning Notebook (0.575):**

https://www.kaggle.com/c/coleridgeinitiative-show-us-the-data/discussion/248296

* Search for named entities using the Schwartz-Hearst algorithm
* Filter candidates using a fine-tuned roberta-base binary classifier
* Threshold and propagate candidates

## Reference
Banerjee, I., Ling, Y., Chen, M. C., Hasan, S. A., Langlotz, C. P., Moradzadeh, N., Chapman, B., Amrhein, T., Mong, D., Rubin, D. L., Farri, O., & Lungren, M. P. (2019). Comparative effectiveness of convolutional neural network (CNN) and recurrent neural network (RNN) architectures for radiology text report classification. Artificial intelligence in medicine, 97, 79–88. https://doi.org/10.1016/j.artmed.2018.11.004

Britz, D. (2016, January 10). Understanding Convolutional Neural Networks for NLP. WildML. http://www.wildml.com/2015/11/understanding-convolutional-neural-networks-for-nlp/.

Chollet, F. (2017). Chapter 6. Deep learning for text and sequences. Deep Learning with Python. · Deep Learning with Python. https://livebook.manning.com/book/deep-learning-with-python/chapter-6/18.

Google. (n.d.). Step 4: Build, Train, and Evaluate Your Model. Google. https://developers.google.com/machine-learning/guides/text-classification/step-4.

He, Z., Wang, Z., Wei, W., Feng, S., Mao, X., Jiang, S. (2020). A Survey on Recent Advances in Sequence Labeling from Deep Learning Models. arXiv:2011.06727v1 [cs.CL]. Cornell University.

Meparlad. (2020, December 11). Text Classification in Natural Language Processing. Analytics Vidhya. https://www.analyticsvidhya.com/blog/2020/12/understanding-text-classification-in-nlp-with-movie-review-example-example/.

Natural Language Toolkit. Natural Language Toolkit — NLTK 3.6.2 documentation. (n.d.). https://www.nltk.org/.

Pennington, J. (n.d.). GloVe: Global Vectors for Word Representation. https://nlp.stanford.edu/projects/glove/.

Phi, M. (2020, June 28). Illustrated Guide to LSTM’s and GRU’s: A step by step explanation. Medium. https://towardsdatascience.com/illustrated-guide-to-lstms-and-gru-s-a-step-by-step-explanation-44e9eb85bf21.

spaCy 101: Everything you need to know · spaCy Usage Documentation. spaCy 101: Everything you need to know. (n.d.). https://spacy.io/usage/spacy-101.

United States Commission on Evidence-Based Policymaking. (2017). The Promise of Evidence-Based Policymaking: Report of the Commission on Evidence-Based Policymaking. 
