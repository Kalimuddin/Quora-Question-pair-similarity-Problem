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
kd 
