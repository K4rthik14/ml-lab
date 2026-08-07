# Ridge and Lasso Regression on the Diabetes Dataset

This experiment demonstrates the implementation of **Linear Regression**, **Ridge Regression (L2 Regularization)**, and **Lasso Regression (L1 Regularization)** using the **Diabetes dataset** from Scikit-learn. The performance of these models is compared using **Mean Squared Error (MSE)** and **R² Score**, while the optimal regularization parameter is selected using **GridSearchCV**.

---

## Objectives

- Understand the concept of regularization.
- Implement Linear Regression, Ridge Regression, and Lasso Regression.
- Preprocess the dataset using feature scaling.
- Tune the regularization parameter using cross-validation.
- Compare model performance using evaluation metrics.

---

## Dataset

**Dataset:** Diabetes Dataset

- Source: `sklearn.datasets.load_diabetes()`
- Samples: 442
- Features: 10
- Target: Disease progression measure

---

## Theory

### Linear Regression

Linear Regression predicts a continuous target variable by fitting the best linear relationship between input features and the target.

Model:

\[
y = \beta_0 + \beta_1x_1 + \beta_2x_2 + ... + \beta_nx_n
\]

Objective:

Minimize the Mean Squared Error (MSE).

---

### Why Regularization?

Linear Regression may overfit when:

- Dataset contains noisy features.
- Features are highly correlated.
- Model coefficients become very large.

Regularization adds a penalty to the loss function to reduce overfitting and improve generalization.

---

## Ridge Regression (L2 Regularization)

Ridge Regression adds the squared magnitude of coefficients as a penalty.

Loss Function:

\[
Loss = MSE + \alpha \sum_{i=1}^{n}\beta_i^2
\]

### Characteristics

- Shrinks coefficients toward zero.
- Does **not** remove features.
- Reduces model variance.
- Effective for multicollinearity.

---

## Lasso Regression (L1 Regularization)

Lasso Regression adds the absolute value of coefficients as a penalty.

Loss Function:

\[
Loss = MSE + \alpha \sum_{i=1}^{n}|\beta_i|
\]

### Characteristics

- Shrinks coefficients.
- Can make coefficients exactly zero.
- Performs automatic feature selection.
- Produces a simpler model.

---

## Hyperparameter Tuning

The regularization strength is controlled using **alpha (α)**.

A larger alpha:

- Increases regularization.
- Produces smaller coefficients.
- May underfit if too large.

A smaller alpha:

- Produces behavior similar to Linear Regression.
- May overfit.

GridSearchCV with 5-fold cross-validation is used to determine the best alpha value.

---

## Performance Metrics

### Mean Squared Error (MSE)

Measures the average squared prediction error.

Lower MSE indicates better performance.

---

### R² Score

Measures how well the model explains the variance in the data.

Range:

- 1 → Perfect prediction
- 0 → Model predicts the mean
- Negative → Worse than predicting the mean

Higher R² is better.

---

## Libraries Used

- NumPy
- Pandas
- Scikit-learn

---

## Workflow

1. Import libraries.
2. Load Diabetes dataset.
3. Split dataset into training and testing sets.
4. Standardize features.
5. Train Linear Regression.
6. Train Ridge Regression.
7. Train Lasso Regression.
8. Tune alpha using GridSearchCV.
9. Evaluate using MSE and R².
10. Compare results.

---

# Viva Questions

### 1. What is Regularization?

Regularization is a technique that reduces overfitting by adding a penalty to the loss function.

---

### 2. Why is Regularization required?

It prevents the model from learning noise and improves generalization.

---

### 3. What is Ridge Regression?

Ridge Regression is Linear Regression with L2 regularization.

---

### 4. What is Lasso Regression?

Lasso Regression is Linear Regression with L1 regularization.

---

### 5. Difference between Ridge and Lasso?

| Ridge | Lasso |
|--------|--------|
| L2 penalty | L1 penalty |
| Keeps all features | Removes some features |
| Better with correlated features | Performs feature selection |

---

### 6. What is alpha?

Alpha controls the amount of regularization.

Large alpha → Strong regularization.

Small alpha → Weak regularization.

---

### 7. Why StandardScaler is used?

Regularization depends on feature magnitude.

Scaling ensures all features contribute equally.

---

### 8. Why use GridSearchCV?

To automatically find the best hyperparameter using cross-validation.

---

### 9. What is Cross Validation?

The dataset is divided into multiple folds.

The model trains on some folds and validates on the remaining fold.

This process repeats several times.

---

### 10. What is Overfitting?

A model performs well on training data but poorly on unseen data.

---

### 11. What is Underfitting?

A model is too simple and cannot learn the underlying relationship.

---

### 12. What is Multicollinearity?

When independent variables are highly correlated with each other.

Ridge Regression handles this effectively.

---

### 13. Can Lasso perform feature selection?

Yes.

Lasso makes some coefficients exactly zero.

---

### 14. Which regression is preferred when feature selection is required?

Lasso Regression.

---

### 15. Which regression is preferred for highly correlated features?

Ridge Regression.

---

### 16. What evaluation metrics are used?

- Mean Squared Error (MSE)
- R² Score

---

### 17. Why do we split the dataset?

To evaluate model performance on unseen data.

---

### 18. What happens if alpha is zero?

Ridge and Lasso become ordinary Linear Regression.

---

### 19. Which model generally has the lowest training error?

Linear Regression.

---

### 20. Which models usually generalize better?

Ridge Regression and Lasso Regression.

---

# Interview Questions

- Explain Regularization.
- Difference between L1 and L2 Regularization.
- Why is feature scaling important before Ridge or Lasso?
- When would you choose Ridge over Lasso?
- What is GridSearchCV?
- Explain Bias-Variance Tradeoff.
- What is Cross Validation?
- Why can Lasso remove features?

---

# Learning Outcomes

After completing this experiment, you will be able to:

- Understand overfitting and regularization.
- Implement Ridge and Lasso Regression.
- Tune hyperparameters using GridSearchCV.
- Evaluate regression models using MSE and R² Score.
- Compare regularized regression models with Linear Regression.

---

## References

- Scikit-learn Documentation
- Introduction to Machine Learning – Ethem Alpaydin
- Machine Learning using Python – U. Dinesh Kumar