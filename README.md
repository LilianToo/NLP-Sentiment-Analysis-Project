# SXSW SENTIMENT ANALYSIS

# Overview

In this project, we studied how people feel about different companies and products during SXSW by analyzing tweets from a dataset "judge-1377884607_tweet_product_company". Each tweet includes the company, product category and corresponding sentiment labels. This makes it useful for understanding customer perception and brand performance.

# Business understanding
Nowadays, customers express their satisfaction and dissatisfaction on social media especially on platforms like Twitter. The tweets reveal how people feel about brands, products and their customer experience.
Companies are increasingly relying on sentiment analysis to monitor public perception, identify dissatisfaction early, and guide marketing, product design, and support decision-making.

# Problem Statement

Product owners and companies invest heavily on marketing at major events like SXSW,but lack real-time, data-driven understanding of public opinion. They struggle to answer:
1. Is our campaign resonating positively?
2. How sentiments towards our brand compare to our competitors?
3. What specific product features or marketing stunts are people talking about(Positive/Negative/Neutral)?

# Stakeholders
The stakeholders in this project are:
1.Marketing Directors:- They decide whether campaigns are resonating.
2.Brand Consultants:- Advise clients on positioning and trends.
3.Company Managers:- Plan budgets and strategies for future events.

# Data Understanding
From the dataset "judge-1377884607_tweet_product_company", each row contains the tweet text,the company referenced, the product category, and whether the sentiment is Positive, Negative or Neutral.The dataset is passed throught the following steps:
# Steps 
We prepared the data by using the following:
1. Data cleaning
2. Text preprocessing
3. Exploratory Analysis
4. Feature Engineering
5. Balancing Data using SMOTE
6. Modeling
7. Evaluation
8. Visualization.

# Data Preparation
This step involves handling the missing values,cleaning the text through lowercasing, removing punctuation, and stopwords to reduce noise and standardize the text for better vectorization.
The cleaned text is then tokenized and lemmatized to reduce vocabulary size by converting words to their base forms.

The encoded target labels converted categorical emotion labels into numerical format for modeling.

Stratified train-test split is performed to preserve class balance in both training and testing sets.

Applied TF-IDF vectorization to transform text into meaningful numerical features for ML models.

SMOTE is applied to balance minority classes for improved model performance on underrepresented labels.

Features are scaled to improve convergence and stability for the neural network model.

This enabled us to identify key factors that influence public opinion on different companies and products.

Our analysis revealed key insights such as:
1. Positive sentiment dominates
2. Negative sentiments
3. Tweet length trends
4. Competitive positioning

We conclude with three actionable recommendations based on sentiment patterns that can help companies improve brand reputation and strengthen customer satisfaction.

# Strategic Offering
 The analysis provides us quantified brand sentiment and competitive intelligence that can help companies make evidence-based decisions in marketing, product design and customer experience.

# Data Modeling
We transformed text into features that machine learning models can understand, i.e TF-IDF vectors or embeddings and selecting models capable of learning patterns that indicates the emotion behind each tweet. Models used:

# 1.Logistic Regression (Baseline Model)
This is a simple and interpretable linear model that works well with text represented as TF-IDF or word counts.

# 2.Random Forest
It is an ensemble of decision trees and good at handling complex,non-linear data Provides feature importance and resistant to overfitting as well as noise.

# 3. Neural Networks
Flexible and powerful for modeling non-linear relationships.
Can combine multiple feature types(embeddings + TF-IDF)
This model learns word interactions automatically, often moreaccu rately.

# 4.BERT

This is a pre-trained deep learning model specialized in language understanding.
Particularly effective for short, informal text like tweets, improving emotion classification by leveraging semantic understanding beyond simple word counts.
Can be fine-tuned on your dataset for state-of-the-art performance in classification tasks

This enabled us to identify key factors that influence public opinion on different companies and products.

# Key insights
Our analysis revealed key insights such as:
1. Positive sentiment dominates
2. Negative sentiments
3. Tweet length trends
4. Competitive positioning

We conclude with three actionable recommendations based on sentiment patterns that can help companies improve brand reputation and strengthen customer satisfaction.

# Strategic Offering
 The analysis provides us quantified brand sentiment and competitive intelligence that can help companies make evidence-based decisions in marketing, product design and customer experience.
=== MODEL COMPARISON ===
                      Model  Macro F1-Score  Accuracy
0  Baseline (Most Frequent)          0.2542    0.6163
1       Logistic Regression          0.5959    0.6946
2             Random Forest          0.5444    0.6513
3            Neural Network          0.3174    0.5634
4                      BERT          0.6521    0.7271

# RESULTS
# 1. Logistic Regression

Macro F1 = 0.59
The model correctly predicts 69% of the test samples which is better than the baseline model.
Logistic Regression tuning helps, but the model still struggles with minority classes.


# 2. Random Forest Classifier

Macro F1 = 0.54 average performance across all classes.
Accuracy = 0.65 correct predictions for about two-thirds of test samples.
Shows Random Forest can leverage TF-IDF features to capture text patterns across classes.

# 3. Neural Network
Macro F1 =0.31
Accuracy = 0.67
Performs similarly to the Random Forest
Suffers from class imbalance

# 5. BERT

Accuracy = 0.72
Macro F1 = 0.62
The BERT model achieves an accuracy of 0.72 and a macro F1 score of 0.62, outperforming previous models on all sentiment classes. This indicates the model reliably predicts negative, positive, and neutral emotions toward the brand, showing strong generalization and balanced performance across classes.

Model Selection:  BERT was our best performing model hence we chose it.

<img width="1489" height="590" alt="image" src="https://github.com/user-attachments/assets/0267f577-56ab-465e-9e60-5e114bbf4323" />

<img width="1489" height="590" alt="image" src="https://github.com/user-attachments/assets/526091fa-b734-4631-8bf7-8bb1b50c2754" />





<img width="766" height="590" alt="image" src="https://github.com/user-attachments/assets/48a29e3d-5270-4d43-835d-c6dd8059ab26" />

# Model Performance Insights

**Overall Strength**

Accuracy is approximately 0.73 and Macro F1 = 0.65, This shows that the model is significantly strong,but performance is uneven across classes.

Weighted averages are higher at (0.73)because the majority "No emotion" class dominates.

Neutral class dominance.

The model performs best on "No emotion brand/product" (Neutral) where the precision/recall =0.79.

This indicates data imbalance; the model learns neutral patterns more easily and defaults to then when uncertain.

Weakness in negative emotion detected :- Lowest precision (0.49) and recall(0.54)

Many negative cases are misclassified as neutral, showing difficulty in capturing subtle negative sentiment cues.

Model performance on positive emotion.

Precision and recall are balanced (at 0.65), but misclassifications into neutral remain common. 


Clearly the model can detect positivity better than negativity, but struggles with borderline cases.

The model shows bias toward neutrality.

Positive and negative emotions are often misclassified as "No Emotion".
Therefore, the conservative bias reduces false positives but limits sensitivity to emotional signals.

 
