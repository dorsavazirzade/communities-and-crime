# Communities and Crime

In this task, you will work with the Communities and Crime Dataset from the UCI repository (link). The objective is to analyze and model the data through the following steps:

## Data Preparation:

* **Address missing values in the dataset by first filling them using the mean of each column and evaluate the suitability of this method.** <br>
 Mean imputation is a common method for handling missing values because it is simple and fast. However, it has limitations:<br>
**Pros:** It preserves the size of the dataset and can work well if the data are missing completely at random. <br>
**Cons:** It can distort the distribution of the data, particularly if the missing data is not random. It does not consider the relationships between variables, leading to potentially biased estimates.<br>
* **Propose and implement an alternative approach to handle missing data, explaining its advantages and analyzing its impact on performance.** <br>
KNN imputation is generally a better choice when compared to mean imputation, especially in cases where the missing data is not random. It uses the similarity between instances (neighbors) to fill in missing values, preserving the relationships between features. <br>
**Pros:** KNN considers the correlation between variables, often leading to more accurate imputation. <br>
**Cons:** It is computationally more expensive, particularly with large datasets, and can introduce bias if the number of neighbors is not well-tuned. <br>
**Performance Comparison:** The code performs regression analysis on datasets imputed with both methods. Typically, KNN imputation tends to perform better, as seen in the potentially lower MSE. 

* **Submit the dataset with all missing values imputed.** <br>
The completed datasets (imputed with mean and KNN) are saved as ‘CandC- 
imputed-mean.csv’ and ‘CandC-imputed-knn.csv’.

## Linear Regression:

* **Build a linear regression model on the prepared dataset.**
* **Perform 5-fold cross-validation with randomized 80-20 splits and report the average Mean Squared Error (MSE) across the test sets.**
* **Document the parameters obtained for each of the five models.** <br>
  **MSE Calculation:** The code evaluates the Linear Regression model using 5 different 80-20 splits, calculating the MSE for each split and averaging them. This provides a robust estimate of the model’s performance. <br>
**Parameters Learnt:** The parameters of the Linear Regression model are saved for each of the 5 models, providing insight into how the model adapts to different data splits. 

## Ridge Regression:

* **Apply Ridge regression using various values of the regularization parameter λ.** <br>
The code evaluates Ridge Regression for multiple values of λ and plots the MSE versus λ. The plot helps identify the λ value that minimizes the MSE. 
* **Report the average test MSE across the splits for each λ, identifying the value that achieves the best fit.**

* **Visualize the results with a graph showing λ values on the x-axis and average MSE on the y-axis.** <br>
The best λ is determined by finding the λ value that corresponds to the lowest MSE in the plot. 
* **Discuss how Ridge regression results could assist in feature selection.** <br>
Ridge Regression can shrink parameters towards zero, though it does not typically produce exact zero parameters like Lasso. However, it can still be informative for identifying less important features that could be dropped to simplify the model. 
## Feature Selection and Comparison:

* **Train a model using a reduced set of features and compare its performance to the model trained on all features. Discuss the differences in their results.** <br>
After performing Ridge regression, the features with small coefficients were removed to create a simpler model. The comparison between the full and reduced models showed that the reduced model had a slightly higher Mean Squared Error (MSE). However, the reduced model benefits from being simpler and easier to interpret, which can help prevent overfitting while maintaining a similar level of performance. 
## Exploration of Advanced Methods:

* **Suggest advanced models or methods that could improve the dataset's performance. If applicable, provide the results of these methods.** <br>
**Lasso:** Feature Selection: Lasso regression is particularly well-suited for feature selection. It applies an L1 penalty, which can shrink some coefficients to exactly zero, effectively selecting a subset of features. This is useful for simplifying the model, improving interpretability, and potentially reducing overfitting. <br>
**Performance:** By reducing the number of features, Lasso often enhances the  model’s generalization ability, leading to better performance on unseen data. <br>
**Comparison:** The implementation of Lasso in this assignment shows that it can reduce the number of features without significantly compromising the model’s predictive accuracy. <br>
**Results with Lasso Regression:** The Lasso model selected a subset of features, and a linear regression model was then fitted using these features. The performance was comparable to the full model, demonstrating that Lasso is an effective method for this dataset. Lasso regression is a strong candidate for feature selection and can lead to simpler, more interpretable models without a significant loss in performance.
