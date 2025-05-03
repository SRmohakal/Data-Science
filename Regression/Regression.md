# **Regression** 📊

Regression is a **supervised learning technique** used in **predictive modeling** to estimate relationships between variables. It helps in predicting **continuous numerical values** based on input features.

For example:

* Predicting **house prices** based on area, number of rooms, location, etc.
* Estimating **sales revenue** based on advertising expenditure.
* Forecasting **temperature** based on historical data.

---

## **🔹 Types of Regression in Data Science**

### **1️⃣ Linear Regression**

✔ Finds a straight-line relationship between **independent (X)** and **dependent (Y)** variables.
✔ Equation:

$$
Y = mX + b
$$

✔ Example: Predicting house prices based on size.

🔹 **Python Example:**

```python
from sklearn.linear_model import LinearRegression
import numpy as np

# Sample dataset
X = np.array([[1], [2], [3], [4], [5]])  # Independent variable
y = np.array([3, 6, 9, 12, 15])  # Dependent variable

# Model training
model = LinearRegression()
model.fit(X, y)

# Predict for X = 6
prediction = model.predict([[6]])
print("Predicted Value:", prediction[0])
```

---

### **2️⃣ Multiple Linear Regression**

✔ Extension of **Linear Regression** for **multiple features**.
✔ Equation:

$$
Y = b_0 + b_1X_1 + b_2X_2 + ... + b_nX_n
$$

✔ Example: Predicting car prices using **age, mileage, brand, and horsepower**.

🔹 **Python Example:**

```python
from sklearn.linear_model import LinearRegression
import numpy as np

# Sample dataset (Two features: horsepower, mileage)
X = np.array([[100, 50000], [120, 40000], [150, 30000], [180, 20000], [200, 10000]])
y = np.array([5000, 7000, 10000, 15000, 20000])  # Car price

# Model training
model = LinearRegression()
model.fit(X, y)

# Predict for new car features
prediction = model.predict([[130, 35000]])
print("Predicted Price:", prediction[0])
```

---

### **3️⃣ Polynomial Regression**

✔ Handles **non-linear relationships** by adding **polynomial terms** (e.g., $X^2, X^3$).
✔ Example: Predicting sales growth based on **time** (curved trend).

🔹 **Python Example:**

```python
from sklearn.preprocessing import PolynomialFeatures
from sklearn.pipeline import make_pipeline

# Polynomial regression model
poly_model = make_pipeline(PolynomialFeatures(degree=2), LinearRegression())
poly_model.fit(X, y)

# Predict for new data
print("Predicted Price:", poly_model.predict([[130, 35000]])[0])
```

---

### **4️⃣ Logistic Regression (For Classification)**

✔ Despite the name, Logistic Regression is **used for classification** problems.
✔ Predicts the probability of an event (e.g., **Spam or Not Spam**).
✔ Uses the **sigmoid function**:

$$
P(Y=1) = \frac{1}{1 + e^{-z}}
$$

✔ Example: Predicting if a customer will **buy a product (1) or not (0)**.

🔹 **Python Example:**

```python
from sklearn.linear_model import LogisticRegression

# Sample dataset
X = np.array([[20], [30], [40], [50], [60]])  # Customer age
y = np.array([0, 0, 1, 1, 1])  # Buy (1) or Not (0)

# Model training
log_model = LogisticRegression()
log_model.fit(X, y)

# Predict if a 45-year-old will buy
print("Will they buy?", log_model.predict([[45]])[0])
```

---

### **5️⃣ Ridge and Lasso Regression**

✔ **Ridge Regression** → Adds **L2 regularization** (penalty on large coefficients).
✔ **Lasso Regression** → Adds **L1 regularization** (reduces feature importance).
✔ Helps prevent **overfitting** in complex models.

🔹 **Python Example (Ridge Regression):**

```python
from sklearn.linear_model import Ridge

ridge_model = Ridge(alpha=1.0)
ridge_model.fit(X, y)
```

---

## **🔹 Regression Model Evaluation Metrics** 📈

To measure performance, we use:

1️⃣ **Mean Absolute Error (MAE)** → Average absolute differences
2️⃣ **Mean Squared Error (MSE)** → Average squared differences
3️⃣ **Root Mean Squared Error (RMSE)** → Square root of MSE
4️⃣ **R² Score (Coefficient of Determination)** → Measures model fit (higher is better)

🔹 **Python Example:**

```python
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

y_pred = model.predict(X_test)

print("MAE:", mean_absolute_error(y_test, y_pred))
print("MSE:", mean_squared_error(y_test, y_pred))
print("R² Score:", r2_score(y_test, y_pred))
```

---

## **🔹 When to Use Regression?**

✔ Predicting **continuous numerical values**
✔ Understanding **relationships between variables**
✔ Identifying **trends in data**

---

## **🔹 Summary 🚀**

✅ **Linear Regression** → Simple relationships
✅ **Multiple Regression** → Multiple features
✅ **Polynomial Regression** → Non-linear patterns
✅ **Logistic Regression** → For classification
✅ **Ridge & Lasso Regression** → To prevent overfitting

---
