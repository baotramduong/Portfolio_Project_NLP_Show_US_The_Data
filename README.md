### This is a Kaggle competition for Coleridge Initiative

This competition challenges data scientists to show how publicly funded data are used to serve science and society. Evidence through data is critical if government is to address the many threats facing society, including; pandemics, climate change, Alzheimer’s disease, child hunger, increasing food production, maintaining biodiversity, and addressing many other challenges. Yet much of the information about data necessary to inform evidence and science is locked inside publications.

Now is the time for data scientists to help restore trust in data and evidence. In the United States, federal agencies are now mandated to show how their data are being used. The new Foundations of Evidence-based Policymaking Act requires agencies to modernize their data management. New Presidential Executive Orders are pushing government agencies to make evidence-based decisions based on the best available data and science. And the government is working to respond in an open and transparent way.

This competition will build just such an open and transparent approach. The results will show how public data are being used in science and help the government make wiser, more transparent public investments. It will help move researchers and governments from using ad-hoc methods to automated ways of finding out what datasets are being used to solve problems, what measures are being generated, and which researchers are the experts. Previous competitions have shown that it is possible to develop algorithms to automate the search and discovery of references to data. Now, Coleridge Initiative want the Kaggle community to develop the best approaches to identify critical datasets used in scientific publications.

# Business Statement

             - 1. Can natural language processing find the hidden-in-plain-sight data citations?

             - 2. Can machine learning find the link between the words used in research articles and the data referenced in the article?

# Methodology

In this competition, **natural language processing (NLP)** is used to automate the discovery of how scientific data are referenced in publications. Utilizing the full text of scientific publications from numerous research areas gathered from CHORUS publisher members and other sources, data scientists will identify data sets that the publications' authors used in their work.

If successful, data scientists will help support evidence in government data. Automated NLP approaches will enable government agencies and researchers to quickly find the information they need. The approach will be used to develop data usage scorecards to better enable agencies to show how their data are used and bring down a critical barrier to the access and use of public data.

The Coleridge Initiative is a not-for-profit that has been established to use data for social good. One way in which the organization does this is by furthering science through publicly available research.

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
  
  **Capstone:**
  
  **N-gram Models:**
  
  **Deep Learning Models:**
  
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

## PART I: EDA

<img src = '../main/Data & Figures/cleaned_label_wordcloud.png'>

<img src = '../main/Data & Figures/cleaned_label.png'>

## PART II: Modeling

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

##  Summary of Actionable Insights


##  Future Works


## Reference

