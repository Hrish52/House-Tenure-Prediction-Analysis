# House-Tenure-Prediction-Analysis

# Abstract
This project will analyze and predict whether a household is owned or rented by the people who live there by analyzing and predicting the household's financial status. The analysis is based on census data from Washington state, sourced from the IPUMS USA dataset. The factors such as age, income, education, residential costs, and utility costs, are some of the factors that are used to build predictive models based on Support Vector Machines (SVM) using a variety of kernels (linear, radial, and polynomial).

# Introduction
Homeownership is one of the most important components of social stability and economic stability. There are a number of factors that can be considered when making a decision related to homeownership or renting. Using census data containing demographic, income, and housing information, we apply machine learning models to predict whether a residence is owned or rented based on information in the census.
**Key factors**:
  * Age
  * Income
  * Education
  * Utility Costs (electricity, water, gas)

# Dataset
Throughout this analysis, the housing data for Washington state was obtained from the IPUMS USA service, which contains the necessary housing data for this analysis. The dataset contains 75,388 rows with 24 columns, containing information relating to property ownership, income, and various household utilities, which is broken down into two subsets only.

# Methodology
1. **Data Cleaning**: We filtered the dataset to focus on relevant factors, removed missing values, and encoded categorical variables.
2. **Feature Selection**: Key features such as age, income, education, and utility costs were selected for prediction.
3. **Modeling**: We used three SVM models (Linear, Polynomial, and RBF kernels) to predict ownership status. GridSearchCV was employed to optimize parameters like C (cost) and gamma.
4. **Evaluation**: Accuracy and confusion matrices were used to evaluate model performance. The RBF kernel provided the highest accuracy after cross-validation.

# Algorithms
* **Support Vector Machines (SVM)**:
    * **Linear Kernel**: Used for classification, where the decision boundary is linear. It worked with features like age and total household income.
    * **Polynomial Kernel**: A non-linear model that introduced more complexity by considering features such as age, household income, and marital status.
    * **Radial Basis Function (RBF) Kernel**: This kernel transformed the data into a higher-dimensional space using a Gaussian function. It provided the best results, with an accuracy of 80.59%.
* **GridSearchCV**:
  Employed for hyperparameter tuning in the SVM models to find the optimal values for C (cost) and gamma parameters.
* **K-Fold Cross Validation**:
  Used to validate model performance by splitting the data into multiple training and test sets, ensuring a robust accuracy estimation.

# Results
| Kernel | Accuracy (Before Cross-Validation) | Accuracy (After Cross-Validation) |
|:-------------|:--------------:|--------------:|
| Linear         | 77.27%         | 77.61%         |
| Polynomial         | 75.28%         | 77.1%         |
| Radial Basis Function (RBF) | 80.8%  | 80.59%  |
The RBF kernel outperformed the other kernels, making it the preferred model for predicting house tenure.

# Technologies
* **Programming Language**:
  Python
* **Python Libraries**:
  * pandas: For data manipulation and preprocessing.
  * numpy: For numerical computations.
  * matplotlib and seaborn: For data visualization and plotting decision boundaries and confusion matrices.
  * scikit-learn (sklearn): For implementing the machine learning algorithms (SVM, GridSearchCV, train-test split, etc.).
  * mlxtend: For plotting decision regions and visualizing model results.

IPUMS USA. dataset (n.d.). Retrieved from https://usa.ipums.org/usa/index.shtml
