# Predicting Student Performance from Gameplay Data

This project uses the Kaggle Predict Student Performance from Game Play dataset to predict whether a student answers correctly based on gameplay interaction data.

## Project Overview

The goal of this project is to build a machine learning model that predicts student performance from gameplay behavior. The dataset contains event-level gameplay data, which was cleaned and transformed into useful features for modeling.

## What This Project Includes



## Data Visualization

This project includes exploratory data visualizations to understand patterns in student performance before training the machine learning model.

### Correct and Incorrect Answer Distribution

This chart shows the overall distribution of correct and incorrect answers in the dataset.

![Correct and Incorrect Answer Distribution](figures/correct_incorrect_distribution.png)

### Correct and Incorrect Answers by Question

This visualization compares the number of correct and incorrect responses for each question.

![Correct and Incorrect by Question](figures/correct_incorrect_by_question.png)

### Average Correct Rate by Question

This chart shows the average correct rate for each question, helping identify which questions students answered correctly more often.

![Average Correct Rate by Question](figures/average_correct_rate_by_question.png)

### ROC Curve for Random Forest Model

The ROC curve shows how well the Random Forest model separates correct and incorrect answers. A higher AUC value means better model performance.

![ROC Curve for Random Forest Model](figures/roc_curve_random_forest.png)
A Random Forest classifier was used for this project.

## Files in This Repository

- `StudentPBG.ipynb`:containing the full project
- `README.md`: Project overview

## Future Work

In the future, I would love to improve this project by creating stronger features, such as question-specific behavior and spending more time over each questions .I would also love to try different models with other available datasets.
