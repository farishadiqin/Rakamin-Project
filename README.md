# Job Description Classification Model: Enhancing Recruitment Efficiency at Ford

## Background

### Problem Statement
Ford, a CRM-based technology company, is currently facing difficulties in recruiting employees because job descriptions are too long. This makes it difficult for prospective candidates to understand the requirements and hesitate to apply. To increase efficiency, Ford wants to have a system that can provide job recommendations according to candidates' skills and experience, so that they can more easily find suitable positions. In this way, the recruitment process will be more efficient and can attract more right candidates.

### Goal
Optimizing a machine learning model that can classify sentence categories into one of the classes given in the training dataset provided.

### Objectives

![image](https://github.com/user-attachments/assets/22ba0d68-f322-4292-b251-1c3cb5fdb7be)

### Business Metrics

![image](https://github.com/user-attachments/assets/82e55ce6-e643-4c74-abdd-a5c25baf70e5)

## EDA - Insight

### Dataset

![image](https://github.com/user-attachments/assets/95776dd3-0e14-4407-8690-55b2740ac189)
![image](https://github.com/user-attachments/assets/d567c7f2-33b9-4028-9f85-87c24b1da583)

### Data Cleansing

![image](https://github.com/user-attachments/assets/2334887b-9ba3-403c-bfdc-8f65635136f6)
![image](https://github.com/user-attachments/assets/f3466c91-efef-40d8-b057-7cc90a33faf0)
![image](https://github.com/user-attachments/assets/6529975f-ce43-4b3b-9c7f-6ac40e4d150e)
![image](https://github.com/user-attachments/assets/b3cfb803-1473-4359-8c14-6739854350d1)
![image](https://github.com/user-attachments/assets/1890e458-661d-4ae9-ad1f-fd0a71542c7e)
![image](https://github.com/user-attachments/assets/eba907ff-e659-4500-83b4-f47e6204fdb0)
![image](https://github.com/user-attachments/assets/c8b15772-08ab-4d92-80ba-d9a741fde9b1)

Convert sentences into sentiment scores (positive, negative, neutral) to determine the sentiment expressed within the sentence. Performing Sentiment Analysis on the **New_Sentence** column (which contains job-related descriptions) allows companies to:
1. Understand prospective employees' reactions to job descriptions.
2. Optimize job descriptions to be more engaging and inclusive.
3. Tailor the message to suit the target audience and improve the quality of hires.
4. Reduce bias and inappropriateness in job communications, and increase employee satisfaction and retention.

![image](https://github.com/user-attachments/assets/4f1cff43-1d3a-4e14-803f-5fc268e855c0)
![image](https://github.com/user-attachments/assets/cd78051a-199e-4232-9280-0da79c3ec963)
![image](https://github.com/user-attachments/assets/677479c7-e5d0-40f2-805c-442f16132821)

To perform sentiment classification using the **Sentiment** and **Sentiment_No_Stopwords** columns with the Naive Bayes algorithm, we need to prepare the data and perform feature extraction. We will create two separate Naive Bayes classification models: one using 'Sentiment' as the target variable and another using 'Sentiment_No_Stopwords'. For each model, we will perform text preprocessing, feature extraction, and model training.

![image](https://github.com/user-attachments/assets/125ac1d4-c41d-4de9-ad26-9605d448a2dc)

1. Model Performance: Both models, the one using real text (with stopwords) and the one using text without stopwords, show very similar performance. Both models achieve an accuracy of around 86% with minimal differences.
2. Weaknesses in the Positive Class (1): Despite the overall good accuracy, the model exhibits lower sensitivity to the positive class (positive sentiment), as evidenced by the lower recall for class 1. This means that, while the model can effectively identify many negative examples, it tends to miss some positive instances.
3. Impact of Stopwords: Removing stopwords (as in the Sentiment_No_Stopwords model) does not significantly impact overall model accuracy or performance. However, it can be beneficial in certain cases, particularly when the model is unduly influenced by frequent but semantically insignificant words.

![image](https://github.com/user-attachments/assets/df921ed6-062c-412e-a777-b0a3a09f38d3)
![image](https://github.com/user-attachments/assets/2aa5ac9d-f729-43bf-a465-ed9753344179)

SMOTE can improve class balance but may lead to performance degradation if not followed by appropriate model adjustments.
The model's performance improved for some classes, such as classes 3 and 1, but decreased for classes 2 and 4, particularly in terms of lower recall.
Overall, while accuracy decreased slightly (to 68.19%), SMOTE can be a valuable technique for addressing class imbalance. However, the model requires further evaluation and may necessitate refinement or adjustments, such as hyperparameter tuning or using a more complex model.

## Modelling

![image](https://github.com/user-attachments/assets/a859fb9d-b731-4932-a9c2-e8c28e6c491b)
![image](https://github.com/user-attachments/assets/99fee59a-25e7-4556-be1d-65a53b8ca0dd)
![image](https://github.com/user-attachments/assets/48329d0e-1f7e-4a7e-8249-07bd3b079787)

Reasons for choosing accuracy as a metric:
1. Accuracy provides an overview of the proportion of correct predictions among the total data points. This facilitates communication of model results to stakeholders.
2. As Ford's goal is to classify sentences into the correct categories to improve the candidate experience, accuracy emphasizes the model's ability to make correct predictions overall.

![image](https://github.com/user-attachments/assets/4fba2315-2e2c-4953-97df-2744d8a4c52b)
![image](https://github.com/user-attachments/assets/006f99d5-0d0b-4d7c-bca7-600b7947d47c)
![image](https://github.com/user-attachments/assets/fad52bee-5a39-4366-ba39-500bbb8b8dbd)

## Conclusion

By utilizing Feature Importance from the SVM model, we can gain invaluable insights into the recruitment process. This can provide business insights into the influence of qualifications, skills, response time, and demographics on applicant acceptance. By implementing this strategy, the recruitment process can become more efficient and yield better results according to desired metrics.
