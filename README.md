# Quora-Question-pair-similarity-Problem
## Problem Definition and Data Requirements :
- Problem Statement is to Predict pair of questions are duplicates or not, i.e. Identify which questions asked on Quora that have already been asked.
- Business objective is to predict as many tags as possible with high precision and recall and constraint is suggesting incorrect tags could impact customer experience on StackOverflow
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
- Basic Feature Extraction (before cleaning) :
  - freq_qid1 = Frequency of qid1's
  - freq_qid2 = Frequency of qid2's
  - q1len = Length of q1
  - q2len = Length of q2
  - q1_n_words = Number of words in Question 1
  - q2_n_words = Number of words in Question 2
  - word_Common = (Number of common unique words in Question 1 and Question 2)
  - word_Total =(Total num of words in Question 1 + Total num of words in Question 2)
  - word_share = (word_common)/(word_Total)
  - freq_q1+freq_q2 = sum total of frequency of qid1 and qid2
  - freq_q1-freq_q2 = absolute difference of frequency of qid1 and qid2
- Feature: word_share :
![4](https://user-images.githubusercontent.com/54996809/154851364-6560cd80-8c3c-42e3-bd4d-1711aec6c47f.png)
- Feature: word_Common :
![5](https://user-images.githubusercontent.com/54996809/154851421-07c0acd9-de50-4677-9318-558d2f4cda96.png)












