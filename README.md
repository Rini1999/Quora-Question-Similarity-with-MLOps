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

### Step 1 : Load the dataset
In the first step, we imported the required libraries and modules that are necessary for our project.
Next, we loaded the dataset that contains the relevant information for our tasks.

### Step 2 : Data Cleaning and Exploratory Data Analysis 

Handling missing values : There are totally 3 missing values in the dataset. We have  huge dataset, so we can afford to drop the missing rows.

Data Imbalance check : 63% rows belongs to class-0 which is non-duplicate, whereas 37% belongs to class-1 which is duplicate. Hence, there is no strict imbalance in the dataset.

Text Preprocessing : Lowering text, Removing punctuations, Spelling corrections, Contractions, Removing extra spaces. 

### Step 3 : Feature engineering and extraction

We extracted basic features, length based features, token based features and fuzzy features.
