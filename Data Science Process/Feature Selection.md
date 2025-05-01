### **Feature Selection** 🚀  

Feature Selection is the process of choosing the most important features (variables) from a dataset while removing irrelevant or redundant ones. This helps in:  
✅ Improving model performance  
✅ Reducing overfitting  
✅ Decreasing training time  
✅ Enhancing model interpretability  

---

## **Types of Feature Selection Methods**  

### **1. Filter Methods (Unsupervised)**
These methods evaluate features independently of the model by using statistical techniques.

#### **(a) Correlation-Based Selection**  
- Remove features that are highly correlated with each other.  
- Example: If "height in cm" and "height in inches" are both present, one should be removed.  

  ```python
  import pandas as pd
  import seaborn as sns
  import matplotlib.pyplot as plt

  df = pd.read_csv("data.csv")
  correlation_matrix = df.corr()
  sns.heatmap(correlation_matrix, annot=True, cmap="coolwarm")
  plt.show()
  ```

#### **(b) Chi-Square Test (For Categorical Data)**  
- Measures dependency between categorical variables.  
- Used in classification problems.  

  ```python
  from sklearn.feature_selection import chi2, SelectKBest
  X_new = SelectKBest(score_func=chi2, k=5).fit_transform(X, y)
  ```

#### **(c) Mutual Information (Feature Importance Measure)**  
- Determines how much information one variable provides about another.  

  ```python
  from sklearn.feature_selection import mutual_info_classif
  importance = mutual_info_classif(X, y)
  ```

---

### **2. Wrapper Methods (Model-Based)**
These methods select features based on model performance.

#### **(a) Recursive Feature Elimination (RFE)**
- Iteratively removes least important features.  

  ```python
  from sklearn.feature_selection import RFE
  from sklearn.ensemble import RandomForestClassifier

  model = RandomForestClassifier()
  selector = RFE(model, n_features_to_select=5)
  X_new = selector.fit_transform(X, y)
  ```

#### **(b) Forward/Backward Selection**
- **Forward Selection:** Starts with no features and adds the best ones.  
- **Backward Selection:** Starts with all features and removes the worst ones.

---

### **3. Embedded Methods (Feature Importance from Models)**
These methods select features while the model is training.

#### **(a) Lasso Regression (L1 Regularization)**
- Shrinks less important feature weights to **zero**, effectively removing them.  

  ```python
  from sklearn.linear_model import Lasso
  lasso = Lasso(alpha=0.01)
  lasso.fit(X, y)
  selected_features = X.columns[lasso.coef_ != 0]
  ```

#### **(b) Feature Importance from Random Forest**
- Feature importance scores from tree-based models.  

  ```python
  from sklearn.ensemble import RandomForestClassifier
  model = RandomForestClassifier()
  model.fit(X, y)
  print(model.feature_importances_)  # Higher values mean more important features
  ```

---

## **Feature Selection Best Practices**
✅ Remove duplicate or highly correlated features.  
✅ Use **domain knowledge** to eliminate irrelevant features.  
✅ Try different methods and compare results.  
✅ Keep it simple – more features don’t always mean better models!  

---
