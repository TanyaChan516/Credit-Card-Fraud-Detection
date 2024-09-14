## Credit Card Fraud Detection
### Context
Credit card companies aim to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.

### Content
The dataset contains transactions made by credit cards in September 2013 by european cardholders.
Transactions occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, as the positive class (frauds) account for 0.172% of all transactions. <br>

It contains numerical input variables V1-V28 which are the result of a Principal Component Analysis (PCA) transformation, as original features are not provided due to confidentiality issues. Features that have not been transformed with PCA are 'Time' and 'Amount'. 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. 'Amount' denotes the transaction Amount. 'Class' is the response variable (labelled outcome) and it takes value 1 in case of fraud and 0 otherwise.  <br>

### Module 1: Data Exploration
Load `creditcard_train.csv` and explore the dataset. Meanwhile, handling outliers and missing data.

The dataset was explored solely, and by their class in terms of basic statistic, missing value, and outliers. Then 798 missing values and then total 71266 outliers are removed. The removal cause the a dispersed distribution in dataset fraud than in valid. 

### Module 2: Data Visualization
Explore and visualize the distributions of variables in the Fraud group and in the Normal group.
![image](https://github.com/user-attachments/assets/5cd89491-9276-4242-b52b-35f918f8fea7)

Correlation and connection between V1 to V28 with Class are studied with heatmap and subplots. V14 and V17 are found to be negatively related to Class while V2 and V11 are positively related. The distributions of V14 and V17 in Valid is very stable within -2.5 to 2.5 for V14 and V17 and within -3.0 to 3.0 for V2 and V11. While most data besides these range are considered to be Fraud.

### Module 3: Dimension Reduction
Apply unsupervised learning methods to achieve dimension reduction.

Demension of the transformed data has been reduced to 2D to find that it is difficult to separate fraud transactions from valid transactions.

### Module 4: Classification
Load `creditcard_test.csv` and use it as the test dataset to evaluate the classification models and compare their performance using 5-fold cross-validation.

### Summary
4 models are conducted to compute the overall accuracies, 
- LogisticRegression and LinearDiscriminantAnalysis return the highest accuracy > 90%
- QuadraticDiscriminantAnalysis > 80%
- KNeighborsClassifier > 60%

Note that we should always consider training most of the amount of our data into our model since every model is having different specific algorithm and calculations. However, due to the limitation of our data set, which is highly unbalanced, we have to undersample our data set into our calculation model, which might eventually be showing a great variety of results.

If it is possible to provide more data into the model and for testing, I believed the overall accuracy of the detection models will be > 80% or even higher.

