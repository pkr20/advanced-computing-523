# Introduction

This dataset includes Age, Year of Diagnosis, Sex, Race, Ethnicity, Primary Cancer Site, Tumor Grade, Summary Stage, Marital Status, Appalachia. I performed a survival analysis based on the data based on two different sets - 1: Appalachia, 0: Non-Appalachia for populations that lived near the Appalachia to observe an effect on survival.

# Working with Data

I started by standardizing and scaling the data for each of the two sets. Then I divided the data 70 20 10 train test validation split. I started to build the model for data_A and data_NA. I started building three different logistic regression models with different solvers including newton-cg, liblinear, and lbfgs.

# Machine Learning Model and Hyper Parameterization

The goal was to build machine learning models using Logistic Regression and XGBoost (both default and optimized) to predict the Survival Recode for individuals. After building and evaluating the models, I analyzed which algorithm performed best based on validation metrics and confusion matrix. The XGBoost model had a greater number of true positives and true negatives and less false predictions than logistic regression models. Logistic regression handles linear relationships between the features. For this dataset, the XGBoost as tree based model does a better job of handling non-linear relationships between these features and survival analysis. Furthermore, I was able to tune the model with hyperparameter options. After comparing performance, I chose the XGBoost algorithm optimized as best suited with this data because there was an increase in the accuracy score by around 10% from logistic regression. After experimenting between values I chose a max_depth of 5 which limits the depth of the tree and controls overfitting of a model. The learning rate I kept to 0.1 for the



## Conclusion
The analysis revealed that the XGBoost algorithm, especially with hyperparameter tuning, was best suited for this dataset due to its ability to handle non-linear relationships and improve accuracy. The insights also highlighted the disparities between populations near Appalachia and those outside it, further emphasizing the importance of tailored interventions for improved survival outcomes.
