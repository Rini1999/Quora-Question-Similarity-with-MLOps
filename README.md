# Quora-Question-Similarity-with-MLOps

Over 100 million people visit Quora every month, so it's no surprise that many people ask similarly worded questions. Multiple questions with the same intent can cause seekers to spend more time finding the best answer to their question, and make writers feel they need to answer multiple versions of the same question. Quora values canonical questions because they provide a better experience to active seekers and writers, and offer more value to both of these groups in the long term. The main aim of the project is to predict whether a pair of questions are similar or not. 

## Problem Statement:
Identify which questions asked on Quora are duplicates of questions that have already been asked.

## Domain: Social Network 

## Prerequisites: Python programing language, Machine Learning, NLP and MLOPs

## Real World/Business Objectives and Constraints:
- The cost of a mis-classification can be very high.
- You would want a probability of a pair of questions to be duplicates so that you can choose any threshold of choice.
- No strict latency concerns.
- Interpretability is partially important.

## Type of Machine Learning Problem
It is a binary classification problem, for a given pair of questions we need to predict if they are duplicate or not.

## Solution
This project aims to develop a model that can accurately classify whether a pair of questions on quora are duplicates or not. By doing so, we can enhance the user experience by reducing search time, minimising duplicate questions and providing more value to quora's user base.

### Dataset description

| Column | Description |
| :---: | :---: |
| id | Unique id for each row |
| qid1 | Question 1 id |
| qid2 | Question 2 id |
| question1 | Question 1 |
| question2 | Question 2 |
| is_duplicate | Question pair is duplicate or not |

### Step 1 : Load the dataset
In the first step, we imported the required libraries and modules that are necessary for our project.
Next, we loaded the dataset that contains the relevant information for our tasks.

### Step 2 : Data Cleaning

Handling missing values : There are totally 3 missing values in the dataset. We have  huge dataset, so we can afford to drop the missing rows.

Data Imbalance check : 63% rows belongs to class-0 which is non-duplicate, whereas 37% belongs to class-1 which is duplicate. Hence, there is no strict imbalance in the dataset.

### Step 3 : Basic Text Preprocessing : Lowering text, Removing punctuations, Spelling corrections, Contractions, Removing extra spaces. 

### Step 4 : Feature engineering

We extracted basic features, length based features, token based features and fuzzy features.

| Basic Features | Length Based Features | Token Based Features | Fuzzy Features |
| :---: | :---: | :---: | :---: |
| Each question length | Mean length of two questions | First word equal or not | Fuzzy ratio |
| No: of words in each question | Absolute length difference of two questions | Last word equal or not | Fuzzy partial ratio | 
| Total no: of words in each question pair | Longest substring ratio | Ratio of common token count to maximum token count among each question pair | Fuzzy token sort ratio |
| Common words in each question pair | | Ratio of common token count to minimum token count among each question pair | Fuzzy token set ratio |
| Word share | | Ratio of common stopword count to maximum stopword count among each question pair | |
| | | Ratio of common stopword count to minimum stopword count among each question pair | |
| | | Ratio of common words to length of the smaller question among each question pair | |

### Step 5 : Exploratory Data Analysis

- Similar and Non-Similar question count analysis
- Target class imbalance analysis
- Extracted features impact analysis

#### Key findings in EDA:

- 8% questions are similar, 92% are not similar.
- 63% rows belong to class-0 and 37% rows belong to class-1.
- Basic features have less impact on target class.
- Token based and length based features have significantly less impact on target class.
- Fuzzy features have significantly high impact on target class.

### Step 6 : Advanced text preprocessing

#### Approaches used : 

- Basic approach with no text preprocessing and using BOW.
- Basic approach with text preprocessing and using BOW, TFIDF.
- Advance approach with text preprocessing, feature extraction and using BOW, TFIDF.
- Advance approach using own-embedding.
- Advance approach using Pre-trained model, Word2Vec, GloVe and BERT.

### Step 7 : Model building and experiment tracking

- Here, we tracked every experiment while training the model to save time.

### Step 8 : Model evaluation

#### Metrics used : 

- Classification report, Confusion matrix

#### Results : 

Accuracy increased from less than 80% using basic approach to greater than 80% using advance approach using BERT. Using BERT as a text to numeric vector conversion technique and XGBoost as a machine learning classification model, obtained highest accuracy as 85.3%.

### Step 9 : Model deployment 

## Challenges faced

- Main challenge we faced is the type of data. Working with textual data is bit difficult.
- Class imbalance in the dataset.
- Selection of best vectorization technique.
- Handling vector in BOW and TFID since vectors created by these two vectorization techniques are dense with high dimensions.
