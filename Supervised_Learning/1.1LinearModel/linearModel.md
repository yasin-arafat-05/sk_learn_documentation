
# 1.1.1 Ordinary Least Squares:

Let's break down the information provided under the topic **" 1.1.1. Ordinary Least Squares "** from the scikit-learn documentation:

1. **LinearRegression**: This is a class in scikit-learn used for fitting linear regression models. It fits a linear model with coefficients to minimize the residual sum of squares between the observed targets in the dataset and the targets predicted by the linear approximation.

**Keywords:** <br>
**Fitting a linear regression model** <br>

```text
Fitting a linear regression model essentially means finding the best-fitting line (or hyperplane in higher dimensions) that describes the relationship between the independent variables (features) and the dependent variable (target) in the given dataset. The process involves determining the coefficients (weights) for each independent variable in order to minimize the difference between the actual target values and the values predicted by the linear equation.
```
<br>

**Residual sum:**
In machine learning, the residual sum refers to the sum of the squared differences between the actual target values (or observations) in a dataset and the corresponding predicted values obtained from a model. These differences, often referred to as residuals, represent the errors made by the model in predicting the target values.

Mathematically, if we have a dataset with $\( n \)$ observations, denoted by $\( (x_i, y_i) \)$ where $\( x_i \)$ represents the features and $\( y_i \)$ represents the actual target values, and our model predicts corresponding values $\( \hat{y}_i \)$, then the residual for each observation is $\( y_i - \hat{y}_i \)$.

The residual sum of squares (RSS) is calculated as:

$\[ RSS = \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 \]$

<br> <br>

2. **Mathematical Problem**: The LinearRegression model solves a mathematical problem where it minimizes the sum of squared differences between the actual target values and the predicted values obtained from the linear model.

3. **Usage**: To residualuse LinearRegression, you create an instance of the LinearRegression class and then call its `fit()` method with arrays X and y, where X contains the features and y contains the target values. After fitting, you can access the coefficients of the linear model using the `coef_` attribute of the LinearRegression instance.

4. **Example**: Here's an example provided in the documentation:
   ```python
   from sklearn import linear_model
   reg = linear_model.LinearRegression()
   reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])
   print(reg.coef_)  # Output: array([0.5, 0.5])
   print("Intercept:", reg.intercept_)     # Output: 0.0
   ```
   This example demonstrates fitting a LinearRegression model with three data points `[[0, 0], [1, 1], [2, 2]]` and corresponding target values `[0, 1, 2]`. After fitting, it prints out the coefficients of the linear model, which are `[0.5, 0.5]`.
   I see the discrepancy. Let's correct it:

Given the equation \( y = 0.5x_1 + 0.5x_2 + c \), we don't explicitly see \( c \) in the output `[0.5, 0.5]`, but it's implicitly assumed to be zero, meaning the line passes through the origin.

So, the equation simplifies to \( y = 0.5x_1 + 0.5x_2 \).

Now let's verify the given data:

For the point (0, 0):
$\[ y = 0.5 \times 0 + 0.5 \times 0 = 0 \]$

For the point (1, 1):
$\[ y = 0.5 \times 1 + 0.5 \times 1 = 1 \]$

For the point (2, 2):
$\[ y = 0.5 \times 2 + 0.5 \times 2 = 2 \]$

It seems there was a mistake in the calculation for the point (1, 1). The correct calculation should yield $\( y = 1 \), not \( y = 0.5 \)$. 

So, when we apply the coefficients `[0.5, 0.5]` to the given data points, we indeed get the correct predictions:
- (0, 0) → Predicted $\( y = 0 \)$ (Correct)
- (1, 1) → Predicted $\( y = 1 \)$ (Correct)
- (2, 2) → Predicted $\( y = 2 \)$ (Correct)


5. **Explanation on Coefficient Estimates**: The paragraph discusses how the coefficient estimates obtained from Ordinary Least Squares (OLS) rely on the independence of features. When features are correlated and the design matrix becomes close to singular (i.e., when the columns of the design matrix have an approximately linear dependence), the least-squares estimate becomes highly sensitive to random errors in the observed target. This sensitivity leads to a large variance in the estimates. This situation is referred to as multicollinearity and can occur, for example, when data are collected without an experimental design.

In summary, this section provides an overview of using LinearRegression for fitting linear models, illustrates an example, and explains the implications of multicollinearity on coefficient estimates obtained through Ordinary Least Squares.
