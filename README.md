# Quora-Question-pair-similarity-Problem

## Problem Definition and Data Requirements :
- Problem Statement is to Predict pair of questions are duplicates or not, i.e. Identify which questions asked on Quora that have already been asked.
- Business objective is to predict as many tags as possible with high precision and recall and constraint is suggesting incorrect tags could impact customer experience on StackOverflow
- After doing EDA, Feature extraction & experimenting so many ML models we achieved minimum log_loss = 0.357, Initially for Random model log_loss was 0.887  
- Required Data available at : https://drive.google.com/drive/folders/19nKTSJ8JK1gbQDtbOk4beUgwHc1GNnkO?usp=sharing

## EDA :
- We are given a minimal number of data fields here, consisting of:
  - id:  Looks like a simple rowID
  - qid{1, 2}:  The unique ID of each question in the pair
  - question{1, 2}:  The actual textual contents of the questions.
  - is_duplicate:  The label that we are trying to predict - whether the two questions are duplicates of each other.
- Number of duplicate(smilar) and non-duplicate(non similar) questions :
![1](https://user-images.githubusercontent.com/54996809/154851082-48c5c6ff-093f-4640-bff2-53128bd526a7.png)

- Plot representing unique and repeated questions :
![2](https://user-images.githubusercontent.com/54996809/154851100-c61f269e-8928-4d3f-a1f7-3e689b50b606.png)

- Number of occurrences of each question :
![3](https://user-images.githubusercontent.com/54996809/154851192-f6a219df-3bdf-4da1-a55c-8df2551c474a.png)

- Feature: word_share :
![4](https://user-images.githubusercontent.com/54996809/154851364-6560cd80-8c3c-42e3-bd4d-1711aec6c47f.png)

- Feature: word_Common :
![5](https://user-images.githubusercontent.com/54996809/154851421-07c0acd9-de50-4677-9318-558d2f4cda96.png)

## Data Cleaning / Preprocessing :
- Removing html tags
- Removing Punctuations
- Performing stemming
- Removing Stopwords
- Expanding contractions etc.

## Analysis after Data Cleaning :
- Word Clouds generated from duplicate pair question's text :
![6](https://user-images.githubusercontent.com/54996809/154852177-272e4787-3077-4521-873a-ddf3e4900959.png)

- Word Clouds generated from non duplicate pair question's text :
![7](https://user-images.githubusercontent.com/54996809/154852203-2eb6ebea-c57b-494c-a579-2f29918cee19.png)

- Pair plot of features ['ctc_min', 'cwc_min', 'csc_min', 'token_sort_ratio'] :
![8](https://user-images.githubusercontent.com/54996809/154852228-71e87831-31a1-46c8-a786-fc41e2ad6c7f.png)

- Using TSNE for Dimentionality reduction for 15 Features(Generated after cleaning the data) :
![9](https://user-images.githubusercontent.com/54996809/154852292-1ca4ef92-5fd8-4881-9dcd-4d6bf3650315.png)

## Featurizing text data with tfidf weighted word-vectors :
After featurising we got,
- Number of features in nlp dataframe : 17
- Number of features in preprocessed dataframe : 12
- Number of features in question1 w2v  dataframe : 384
- Number of features in question2 w2v  dataframe : 384
- Number of features in final dataframe  : 794

## ML Modelling :
- Building a random model (Finding worst-case log-loss) :
![10](https://user-images.githubusercontent.com/54996809/154852846-ca98f2a5-9e5d-4319-a64f-78fde0118746.png)

- Logistic Regression with hyperparameter tuning :
![11](https://user-images.githubusercontent.com/54996809/154852857-d0d944ed-9de5-4303-8eee-a104b6244765.png)

- Linear SVM with hyperparameter tuning :
![12](https://user-images.githubusercontent.com/54996809/154852863-7638a2f2-5ca3-4f56-bd99-0ffff640cd4a.png)

- XGBoost :
![13](https://user-images.githubusercontent.com/54996809/154852873-b91572c1-9dc7-4cc0-9085-c139f84a8aee.png)









