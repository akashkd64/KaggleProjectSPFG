# Predicting Student Performance from Gameplay Data

This project uses the Kaggle “Predict Student Performance from Game Play” dataset to build a machine learning model that predicts whether a student will answer a question correctly based on gameplay interaction data. The dataset contains student gameplay events, including clicks, elapsed time, level progress, and session information. Since the original dataset is event-level data, the information was cleaned and transformed into session-level features that could be used for machine learning.


## Project Overview

The objective of this project is to predict whether a student answers a question correctly based on their gameplay behavior. The dataset consists of event-level sets capturing user interactions such as clicks, elapsed time, and level progression.
Since the raw data is highly detailed and event-based, it is not directly suitable for machine learning models. Therefore, the data is aggregated by session_id to create meaningful session-level features such as average elapsed time, maximum level reached, and total number of interactions.

The problem is formulated as a binary classification task, where the goal is to predict whether a student’s answer is correct (1) or incorrect (0). I used the  Random Forest classifier to model the relationship between gameplay behavior and student performance. The Random Forest model achieved decent performance with about 62% validation accuracy and a ROC AUC score of about 0.64.

# Summary of the work done
## Data
Dataset From: https://www.kaggle.com/competitions/predict-student-performance-from-game-play/data

Train shape: (26296946, 20)

Labels shape: (424116, 2)

Test shape: (3728, 21)

Sample submission shape: (54, 3)

The dataset consists of tabular gameplay event data stored in CSV format, where each row represents a user interaction.
It contains gameplay event data and labels showing whether students answered questions correctly or incorrectly. The main gameplay file contains millions of rows, so the project focuses on cleaning, filtering, and transforming the data into a smaller and more useful format for modeling.

The target variable is the ⁠ correct ⁠ column from the labels dataset. This column tells whether the student answered a question correctly. The input features were created from gameplay behavior, including time based information, level progress, and interaction counts. After preprocessing, the dataset I prepared the dataset so that each row represented a student session and level group, making it easier to train and evaluate the machine learning model.

## Data Visualization

I used  it to understand the student performance patterns before training the machine learning model. The first visualization shows the overall distribution of correct and incorrect answers in the dataset. This helped identify whether the dataset was balanced or if one class appeared more often than the other.

![Correct and Incorrect Answer Distribution](figures/correct_incorrect_distribution.png)

I used it to compares correct and incorrect answers for each question. This graph is useful because it shows that some questions have higher correct rates than others. Questions with more correct answers may be easier for students, while questions with more incorrect answers may be more difficult.

![Correct and Incorrect Answers by Question](figures/correct_incorrect_by_question.png)
The graph shows that some questions have higher correct rates than others. This means that certain questions may be easier, while others may be more difficult for students. A higher average correct rate means students answered that question correctly more often, while a lower average correct rate suggests that the question was more challenging.

![Average Correct Rate by Question](figures/average_correct_rate_by_question.png)

These visualizations were important because they helped explain patterns in the target variable before modeling. They also showed that question difficulty and student gameplay behavior may both play a role in predicting whether a student answers correctly.

## Data Preprocessing and Feature Engineering

Before training the model, the raw gameplay data had to be prepared. Since the original dataset was based on individual gameplay events, it was not directly ready for machine learning. The data was grouped by ⁠ session_id ⁠ and ⁠ level_group ⁠ so that each row represented a meaningful gameplay segment for a student.

Several session-level features were created from the event data. These features included average elapsed time, maximum level reached, and total number of gameplay interactions. These engineered features helped summarize student behavior in a way that the machine learning model could understand.

After feature engineering, the target labels were connected to the prepared gameplay features. The final dataset was then split into training and validation sets. The training set was used to teach the model, while the validation set was used to evaluate how well the model performed on data it had not seen during training.

## Model Used

A Random Forest classifier was used for this project. This model was selected because it works well for classification problems and can handle many different types of features.

The Random Forest model was trained using the prepared session-level gameplay features. The model learned patterns between student gameplay behavior and whether the student answered correctly. After training, the model was tested using the validation dataset.

## Model Evaluation

The model was evaluated using accuracy, classification report, and ROC AUC score. Accuracy measures how often the model predicted the correct class. The classification report gives more detailed information about precision, recall, and F1-score. The ROC AUC score shows how well the model separates correct and incorrect answers across different probability thresholds.

The Random Forest model achieved about 62% validation accuracy and a ROC AUC score of about 0.64. . The result suggests that gameplay behavior contains useful information for predicting student performance, but stronger features and additional modeling strategies could improve the prediction quality.

## Conclusion
This project used gameplay data to predict whether students would answer correctly. The Random Forest model achieved decent performance with about 62% validation accuracy and a ROC AUC score of about 0.64. This shows that gameplay behavior can help predict student performance. With improvements model can work more accurately.


## Future Work

In the future, I would love to improve this project by creating stronger features, such as question-specific modeling  and spending more time over each questions .I would also love to try different models with other available datasets.
