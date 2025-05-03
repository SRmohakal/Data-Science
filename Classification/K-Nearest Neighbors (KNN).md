# **K-Nearest Neighbors (KNN) in Data Science** 👨‍🔬📊

## **What is KNN?**

**K-Nearest Neighbors (KNN)** is a **supervised learning algorithm** used for **classification and regression**. It classifies a new data point based on the majority class of its **K nearest neighbors**.

📌 **Key Features of KNN:**
✅ **Simple & intuitive**
✅ **Non-parametric** (no assumptions about data distribution)
✅ **Works well with small datasets**
✅ **Used for both classification & regression**

---

## **1️⃣ How Does KNN Work?**

1️⃣ **Choose a value for K** (number of neighbors)
2️⃣ **Measure the distance** between the test point and all training points (Euclidean distance is common)
3️⃣ **Select the K closest points**
4️⃣ **For classification:** Assign the majority class among neighbors
5️⃣ **For regression:** Average the values of K neighbors

### **Example: KNN for Classification**

🔹 Suppose we have a dataset with two classes: **Red (🔴) & Blue (🔵)**

If **K = 3**, the algorithm looks at the **3 closest points** and assigns the majority class.

* **If 2🔴 & 1🔵 → Assign Red (🔴)**
* **If 2🔵 & 1🔴 → Assign Blue (🔵)**

---

## **2️⃣ Distance Metrics in KNN**

📌 **Common distance measures:**

* **Euclidean Distance** (default) → $d = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2}$
* **Manhattan Distance** → $d = |x_1 - x_2| + |y_1 - y_2|$
* **Minkowski Distance** → Generalized form of Euclidean & Manhattan

---

## **3️⃣ KNN in Python 🐍**

### **🔹 Example: KNN for Classification (Iris Dataset)**

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import accuracy_score

# Load dataset
iris = load_iris()
X_train, X_test, y_train, y_test = train_test_split(iris.data, iris.target, test_size=0.2, random_state=42)

# Normalize features (important for distance-based algorithms)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# Train KNN model with K=3
knn = KNeighborsClassifier(n_neighbors=3)
knn.fit(X_train, y_train)

# Predict and evaluate
y_pred = knn.predict(X_test)
print(f"Accuracy: {accuracy_score(y_test, y_pred):.2f}")
```

📌 **Output Example:**

```
Accuracy: 0.97
```

✅ **High accuracy with KNN on the Iris dataset!**

---

## **4️⃣ Choosing the Best Value of K**

* **Small K (e.g., 1-3)** → High variance (overfitting)
* **Large K (e.g., 10-20)** → High bias (underfitting)
* **Optimal K** is chosen using **cross-validation**

```python
from sklearn.model_selection import cross_val_score
import numpy as np

# Try different values of K
k_values = range(1, 21)
scores = [cross_val_score(KNeighborsClassifier(n_neighbors=k), X_train, y_train, cv=5).mean() for k in k_values]

# Find the best K
best_k = k_values[np.argmax(scores)]
print(f"Best K: {best_k}")
```

✅ **Finds the optimal K value using cross-validation!**

---

## **5️⃣ Advantages & Disadvantages of KNN**

| **Pros ✅**                              | **Cons ❌**                                       |
| --------------------------------------- | ------------------------------------------------ |
| **Easy to understand & implement**      | **Computationally expensive for large datasets** |
| **No training required (lazy learner)** | **Sensitive to irrelevant features & outliers**  |
| **Can handle multi-class problems**     | **Needs feature scaling for better performance** |
| **Works well with small datasets**      | **Not efficient for high-dimensional data**      |

---

## **6️⃣ Real-World Applications 🚀**

📌 **Medical Diagnosis** → Classifying diseases based on symptoms
📌 **Recommendation Systems** → Suggesting products based on user similarity
📌 **Image Recognition** → Identifying objects by comparing to known images
📌 **Anomaly Detection** → Detecting fraud in transactions

---

## **7️⃣ Conclusion 🎯**

✅ **KNN is a simple, powerful, and interpretable algorithm**
✅ **Used for both classification and regression**
✅ **Choosing the right value of K is crucial**
✅ **Works best with small, low-dimensional datasets**

Would you like a **KNN regression example** or a **visualization of KNN decision boundaries**? 🚀
