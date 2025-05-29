✅ Key Findings and Modeling Report
📊 Data Quality Assessment
No null or empty rows detected.

All data types are correct and appropriate.

Serial Number column was dropped due to uniqueness per row—does not contribute to prediction.

No missing or duplicate values found in the dataset.

Outliers were found in LOR and CGPA, but they were considered healthy outliers (valid values within a plausible range), so no removal was done.

🔍 Correlation and Multicollinearity
High correlation of CGPA, GRE, and TOEFL scores with the target variable: Chance of Admission.

Multicollinearity detected using:

Correlation matrix

Variance Inflation Factor (VIF)

Some variables showed high multicollinearity, so steps were taken to address it:

Removed/combined some features based on correlation and VIF analysis.

Applied regularization via Linear Regression and Random Forest, which are more robust to multicollinearity.

Feature importance from Random Forest was used to retain top features.

📈 Modeling Approaches Used
Multiple Linear Regression

Decision Tree Regressor

Random Forest Regressor

🧪 Model Performance (Before Hyperparameter Tuning)
Model	R² Score
Decision Tree	0.6401
Decision Tree (Tuned)	0.6601
Random Forest	0.8066
Linear Regression	0.8212

Random Forest and Linear Regression performed best before tuning.

Decision Tree had the lowest R² score in its default form.

🛠 Model Optimization
Hyperparameter tuning was applied to Decision Tree and Random Forest models using GridSearchCV or RandomizedSearchCV (assumed based on context).

Post-tuning, Decision Tree performance improved slightly.

Further optimization likely needed for RF for better generalization.

⭐ Top 5 Important Features (from Random Forest)
CGPA

GRE Score

TOEFL Score

SOP

LOR

These features had the highest impact on the prediction of admission chances.

>> Multicollinearity
We used the correlation matrix to detect multicollinearity. Features with high pairwise correlations (e.g., GRE Score and TOEFL Score) were identified. To reduce multicollinearity, we dropped GRE Score. After retraining the linear regression model with the reduced feature set, the model maintained good performance with improved interpretability and stability.

>>Top features
We used the feature importance scores from the Random Forest model to select the top 5 most influential features. After filtering the dataset to include only these features, we retrained the Linear Regression, Decision Tree, and Random Forest models. As expected, the R² scores slightly decreased, but the performance remained acceptable. This suggests that the top features capture most of the variance and can be useful in building lightweight, interpretable models.


✅ Conclusion
Multicollinearity was detected and mitigated using correlation matrices and model-based feature selection.

Linear Regression and Random Forest showed strong performance.

Feature importance helped focus on impactful predictors.

Hyperparameter tuning showed moderate improvement in model accuracy.

Future steps may include scaling, cross-validation, or ensemble models for improved generalization.
