# communities-and-crime
Handling Missing Values:

The dataset contains missing values, which need to be addressed before proceeding. Initially, missing attributes are filled using the column-wise mean. This approach's effectiveness is evaluated, with a discussion on its advantages and limitations.
Subsequently, a potentially superior technique is proposed and implemented for imputing the missing data. The performance of the dataset after this imputation is assessed, and the reasons for its improved results, if any, are explained.
Linear Regression:

The cleaned dataset is used to fit a linear regression model. The evaluation involves 5-fold cross-validation with randomized 80-20 train-test splits. The model’s performance is measured in terms of the Mean Squared Error (MSE) on the test set.
The parameters learned for each of the five folds are documented, along with the averaged test errors.
Ridge Regression:

Ridge regression is applied to the dataset with varying values of the regularization parameter 
𝜆. The experiment includes:
Calculating and reporting the test MSE averaged over five 80-20 splits for each λ value.
Identifying the λ value that yields the best performance and illustrating this using a plot (x-axis: λ, y-axis: average test MSE).
The possibility of leveraging Ridge regression results for feature selection is explored, with a detailed explanation.
Feature Selection and Comparison:

A reduced feature set is derived, and the model's performance with this subset is compared to the model trained on the full dataset. The differences in performance metrics are analyzed and discussed.
Advanced Methods:

Suggestions for advanced models or methods that could potentially enhance performance are provided, along with their results if implemented.
