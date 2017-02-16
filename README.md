# Finding Possible Donors for a Charity

This project is the final project for Udacity's Machine Learning Nanodegree course on supervised learning. Supervised learning is the process of finding a function to accurately represent labelled training data. Using anonymized data from the 1994 census, the purpose of this project is to predict a person's income above or below $50,000. If they earn more than $50,000, they will be ideal candidates to donate to our charity. 

## Analysis

The stages in the analysis proceed as follows:
- Data Exploration - basic statistics
- Preparing the Data - feature transformation
- Evaluating Model Performance - comparing performance of three algorithms to a naive predictor
- Feature Importance - identifying features with the most predictive power

## Technologies

This project was completed using Python 2.7. Libraries include:
- scikit-learn
- numpy
- pandas
- IPython

## Results

For this problem, we wish to maximize our donations. A false positive (type 1 error) would result in sending a letter to an individual whose income was predicted above $50,000, but is in fact lower. However, a false negative (type 2 error) refers to our model missing a possible donor, whose income is greater than $50,000. Therefore a false negative is an egregious error for our model to commit. Precision is the probability of our model's correctness when labelling positive, and recall is the probability of positive cases being correctly identified. Therefore a metric with high recall should result in a greater number of donations. A metric favouring recall over precision is the F-0.5 score.

I tested three supervised learning algorithms: k-Nearest Neighbours, Logistic Regression, and Decision Trees. The algorithm with the greatest F-0.5 score was Logistic Regression. Following an optimization with grid search, logistic regression scores 0.85 on accuracy and 0.7 on F-0.5 score. These results are significantly higher than the naive predictor, which assumed that everyone made less than $50,000. 

From the feature analysis, the most important features, in order, are capital loss, age, capital gain, working hours per week, and education level. Training a model with only these features results in an accuracy of 0.81 and an F-score of 0.6. For a small dataset like this one, such feature selection is not necessary, but considering the possible scenario in which we have terabytes of data with hundreds or thousands of features, the efficiency gained by feature selection could be worth a slight drop in accuracy or F-score.
