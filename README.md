# feedback-prize-2022

## Data Sources

https://www.kaggle.com/competitions/feedback-prize-effectiveness - competition page for the Feedback Prize 2022 focused on assessing the effectiveness of feedback in student writing.

https://www.kaggle.com/c/feedback-prize-2021 - competition page for the previous iteration of the Feedback Prize competition, providing additional data and insights.

## Research Scheme

This image provides a visual representation of the overall research approach and methodology used throughout the project, outlining the sequence of experiments and ensemble methods applied.

![alt text](https://github.com/horacemtb/feedback-prize-2022/blob/main/feedback-prize.png)

## Notebooks Descriptions

- EDA & feature engineering - Initial data exploration and feature engineering steps, focusing on generating text-based and statistical features from the dataset to improve model performance. Additionally, this notebook involves using various embeddings (e.g., FastText, TF-IDF, UMAP) and assessing their quality and suitability for the task.

- Train ROBERTA with PEFT - Training the RoBERTa model using Parameter-Efficient Fine-Tuning (PEFT) techniques to enhance its performance on the competition dataset.

- Train DeBERTA with PEFT - Fine-tuning the DeBERTa model using PEFT methods, targeting improved results by optimizing training for the specific requirements of the dataset.

- 1st level DeBERTA | predict for holdout & test - Utilizing the trained DeBERTa model to make predictions on the holdout and test datasets, forming the basis for the first-level predictions in the ensemble.

- 1st level LSTM | train | predict for holdout & test - Training a Long Short-Term Memory (LSTM) model and using it to generate predictions for both holdout and test datasets as another first-level model.

- 1st level XGBoost | prepare data - Preparing the data specifically for training the XGBoost model, focusing on feature transformations and scaling necessary for optimal model performance.

- 1st level XGBoost | train | predict for holdout & test - Training the XGBoost model and generating predictions for the holdout and test datasets, completing the ensemble of first-level models.

- 2nd level Logistic regression | train on holdout | predict for test - Training a second-level Logistic Regression model using the predictions from the first-level models, then applying it to the test set to evaluate final model performance.