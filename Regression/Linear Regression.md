# **Linear Regression** 📊

Linear Regression is a **supervised learning algorithm** used to predict a **continuous numerical value** based on given independent variables. It assumes a **linear relationship** between the dependent and independent variables.

💡 **Example:**

* Predicting **house prices** based on **area, number of rooms, and location**.
* Estimating **salary** based on **experience and education**.
* Forecasting **sales** based on **advertising spend**.

---

## **🔹 Mathematical Representation**

The equation of **Simple Linear Regression** (one independent variable):

$$
Y = mX + b
$$

Where:

* **Y** = Dependent Variable (Target)
* **X** = Independent Variable (Feature)
* **m** = Slope (How Y changes with X)
* **b** = Intercept (Value of Y when X = 0)

For **Multiple Linear Regression** (multiple independent variables):

$$
Y = b_0 + b_1X_1 + b_2X_2 + ... + b_nX_n
$$

Where **X1, X2, ..., Xn** are different features affecting Y.

---

## **🔹 Python Example: Simple Linear Regression**

Let's predict **house prices** based on the **size of the house**.

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression

# Sample dataset (House size in sq.ft vs. Price in $1000s)
X = np.array([[1000], [1500], [2000], [2500], [3000]])  # Independent Variable
y = np.array([150, 200, 250, 300, 350])  # Dependent Variable

# Train a Linear Regression Model
model = LinearRegression()
model.fit(X, y)

# Make predictions
predicted_price = model.predict([[1800]])
print("Predicted Price for 1800 sq.ft house:", predicted_price[0])

# Plot the regression line
plt.scatter(X, y, color="blue", label="Actual Prices")
plt.plot(X, model.predict(X), color="red", label="Regression Line")
plt.xlabel("House Size (sq.ft)")
plt.ylabel("Price ($1000s)")
plt.legend()
plt.show()
```

---

## **🔹 Multiple Linear Regression Example**

Predicting **car price** based on **horsepower and mileage**.

```python
from sklearn.linear_model import LinearRegression

# Sample dataset (Two features: horsepower, mileage)
X = np.array([[100, 50000], [120, 40000], [150, 30000], [180, 20000], [200, 10000]])
y = np.array([5000, 7000, 10000, 15000, 20000])  # Car price

# Train a Multiple Linear Regression Model
model = LinearRegression()
model.fit(X, y)

# Predict for a car with 130 HP and 35000 mileage
predicted_price = model.predict([[130, 35000]])
print("Predicted Car Price:", predicted_price[0])
```

---

## **🔹 Performance Evaluation Metrics**

To measure how well the model performs, we use the following:

1️⃣ **Mean Absolute Error (MAE)**

* Measures average absolute differences between predicted and actual values.
* Formula:

  $$
  MAE = \frac{1}{n} \sum |y_i - \hat{y_i}|
  $$

2️⃣ **Mean Squared Error (MSE)**

* Squares the errors before averaging.
* Formula:

  $$
  MSE = \frac{1}{n} \sum (y_i - \hat{y_i})^2
  $$

3️⃣ **Root Mean Squared Error (RMSE)**

* Square root of MSE, gives more penalty to larger errors.
* Formula:

  $$
  RMSE = \sqrt{MSE}
  $$

4️⃣ **R² Score (Coefficient of Determination)**

* Measures how well the independent variables explain the variance in the dependent variable.
* **Range:** 0 to 1 (Higher is better).

🔹 **Python Code for Model Evaluation**

```python
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

y_pred = model.predict(X)

print("MAE:", mean_absolute_error(y, y_pred))
print("MSE:", mean_squared_error(y, y_pred))
print("RMSE:", np.sqrt(mean_squared_error(y, y_pred)))
print("R² Score:", r2_score(y, y_pred))
```

---

## **🔹 Assumptions of Linear Regression**

1️⃣ **Linearity** → Relationship between independent and dependent variables should be linear.
2️⃣ **Independence** → Observations should be independent of each other.
3️⃣ **Homoscedasticity** → Variance of errors should be constant.
4️⃣ **Normality** → Errors should be normally distributed.
5️⃣ **No Multicollinearity** → Independent variables should not be highly correlated.

---

## **🔹 When to Use Linear Regression?**

✅ When predicting **continuous values** (e.g., price, temperature, sales).
✅ When the relationship between variables is approximately **linear**.
✅ When the dataset is **not too complex** or **small in size**.

---

## **🔹 Summary 🚀**

✔ **Linear Regression** is used to **predict continuous values**.
✔ It establishes a **linear relationship** between dependent & independent variables.
✔ **Simple Linear Regression** uses one feature, while **Multiple Linear Regression** uses multiple features.
✔ It is evaluated using **MAE, MSE, RMSE, and R² Score**.
✔ Assumes **linearity, independence, and no multicollinearity**.

---
