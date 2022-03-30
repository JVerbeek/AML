# AML

This is the repository for Applied Machine Learning. Files are committed from Colab for now. 

## Assignment 1
### Problem description
We receive a large, messy data set from a company. The data set contains about 1500 rows and 2500 columns, making it a p > n problem.
The task is a classification task, as we have to categorize each of the observations in class 0, 1, or 2. 
Eventually, a leaderboard will open where we can submit our solutions and see how we measure up. 

### Current approach 
As of 30-03, the approach I am taking is to first drop any columns with more than 200 missing values.
Then, the missing values in the remaining values are imputed. The data set is divided into a (stratified) train (and dev) and test set in order to be able to estimate the performance of this pipeline.
A random forest is used for a model. Several other models were tried, such as a simple neural network and AdaBoost, but the random forests did outperform both of these methods when tested.
The model is put into a sklearn pipeline along with a standard scaler.
This pipeline is put into grid search to find the optimal number of estimators. 
Conveniently, if the grid search is fit on the training set, it more or less automatically splits the training data into an actual (again stratified) training set and a dev set for fine-tuning. 
Thus, the test set is fully unknown to the model at this point. 
The pipeline achieves a performance of about 80% on the local test set. 

### Next steps
- Estimating pipeline performance on the actual test set
-- If good, ask teachers for next steps
- Improving preprocessing
