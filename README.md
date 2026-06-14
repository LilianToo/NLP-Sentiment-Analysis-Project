<img width="1200" height="674" alt="image" src="https://github.com/user-attachments/assets/6f38db8a-1283-460e-b47e-e3486f05051c" />

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
This step involves handling missing values,cleaning the text through lowercasing, removing punctuation, and stopwords to reduce noise and standardize the text for better vectorization.
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

It is an ensemble of decision trees and good at handling complex, non-linear data provides feature importance and resistant to overfitting as well as noise.

# 3. Neural Networks

Flexible and powerful for modeling non-linear relationships.
Can combine multiple feature types(embeddings + TF-IDF)
This model learns word interactions automatically, often more accurately.

<img width="1489" height="490" alt="image" src="https://github.com/user-attachments/assets/542c8e7f-b949-4b6e-a7bb-750f262cf6c9" />


# 4. BERT

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

Model Selection:  BERT was our best-performing-model hence we chose it.


<img width="1489" height="590" alt="image" src="https://github.com/user-attachments/assets/0267f577-56ab-465e-9e60-5e114bbf4323" />






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


Clearly, the model can detect positivity better than negativity, but struggles with borderline cases.

The model shows bias toward neutrality.

Positive and negative emotions are often misclassified as "No Emotion".
Therefore, the conservative bias reduces false positives but limits sensitivity to emotional signals.

1. Negative Emotion

Total actual negatives: 114
Correctly identified: 65 (57%)
Misclassified as Neutral: 32 (28.1%)
Misclassified as Positive: 17 (14.9%)

Business meaning: The model catches about half of all negative comments; the rest are softened into neutral or positive sentiment.

2. Neutral (No Emotion Toward Brand/Product)

Total actual neutral tweets: 1,106
Correctly identified: 846 (76.5%)
Misclassified as Negative: 50 (4.5%)
Misclassified as Positive: 210 (19.0%)
Business meaning: Neutral detection is strong, forming a reliable backbone for general sentiment tracking.

3. Positive Emotion

Total actual positives: 594
Correctly identified: 398 (67.0%)
Misclassified as Neutral: 175 (29.5%)
Misclassified as Negative: 21 (3.5%)
Business meaning: Positive sentiment is captured reasonably well, but nearly one-third is diluted into neutral.

Business Impact
Positive Business Impact
High reliability for neutral sentiment (76.5% correct) gives an accurate view of brand mentions and general engagement. Two-thirds of positive sentiment detected correctly (67.0%) supports tracking customer delight and campaign uplift. 

The model provides a strong baseline for:

Brand health measurement
Customer satisfaction trends
ROI analysis for marketing activities
Benchmarking conversation volume

<img width="1181" height="790" alt="image" src="https://github.com/user-attachments/assets/78a115b4-e2dc-41c3-b23e-b1fcc76d60ae" />


<img width="989" height="590" alt="image" src="https://github.com/user-attachments/assets/1276fe04-5cfb-4576-bc7c-69828380f42c" />

STRATEGIC RECOMMENDATIONS

FOR MARKETING DIRECTORS:

 CONTINUE SUCCESSFUL STRATEGIES
   
   • Apple: Maintain pop-up store approach for major events
   
   • Google: Continue engaging party and event strategy
   

 ADDRESS PAIN POINTS
   
   • Monitor negative sentiment around specific product issues
   
   • Implement real-time social listening for rapid response

FOR BRAND STRATEGY CONSULTANTS:

1. QUANTITATIVE COMPETITIVE ANALYSIS

   • Use sentiment scores for objective brand positioning
   
   • Identify market gaps and opportunities

3. REAL-TIME CAMPAIGN OPTIMIZATION
   
   • Adjust strategies based on live sentiment data

BUSINESS VALUE SUMMARY

✓ Data-driven decision making replaces guesswork

✓ Real-time competitive intelligence

✓ Quantifiable ROI measurement for marketing spend

✓ Proactive brand reputation management

# RECOMMENDATION

1. Include emotional signals such as emoji analysis, polarity scoring.
   
2. Engage an ensemble to stabilize sentiment predictions. 

 
 
