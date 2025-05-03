# **Manhattan Distance (City Block Distance) in Data Science** 🏙️📏

## **What is Manhattan Distance?**

**Manhattan Distance** (also called **City Block Distance**, **Taxicab Distance**, or **L1 Norm**) is a measure of distance between two points **along axes at right angles** (like city streets). Unlike **Euclidean Distance**, which measures straight-line distance, **Manhattan Distance** follows a grid-like path (like a taxi driving through streets).

📌 **Formula (for two points in n-dimensional space):**

$$
d(A, B) = |x_2 - x_1| + |y_2 - y_1| + ... + |z_2 - z_1|
$$

where:

* $(x_1, y_1, z_1, ...)$ and $(x_2, y_2, z_2, ...)$ are two points in an **n-dimensional space**.
* It **sums the absolute differences** between corresponding elements of the two points.

---

## **1️⃣ Example Calculation**

### **2D Example**

🔹 **Point A** = (2, 3)
🔹 **Point B** = (6, 7)

$$
d(A, B) = |6 - 2| + |7 - 3|
$$

$$
= 4 + 4 = 8
$$

✅ The **Manhattan Distance** between A and B is **8**.

---

## **2️⃣ Manhattan Distance in Python 🐍**

```python
from scipy.spatial.distance import cityblock

A = (2, 3)
B = (6, 7)

distance = cityblock(A, B)
print("Manhattan Distance:", distance)
```

📌 **Output:**

```
Manhattan Distance: 8
```

---

## **3️⃣ Applications of Manhattan Distance in Data Science 🚀**

📌 **1. Machine Learning** → Used in **K-Nearest Neighbors (KNN)**, **K-Means Clustering**, and **Decision Trees**
📌 **2. Image Processing** → Measures **pixel intensity differences**
📌 **3. Recommender Systems** → Computes similarity between users/items
📌 **4. Path Planning (Robotics, Games)** → Used when movement is restricted to grid paths
📌 **5. Finance** → Measures distance in stock market features (e.g., price movements)

---

## **4️⃣ Manhattan Distance vs. Euclidean Distance**

| **Metric**             | **Formula**                 | **Best Used For**                            |   |                                                     |
| ---------------------- | --------------------------- | -------------------------------------------- | - | --------------------------------------------------- |
| **Manhattan Distance** | ( \sum                      | x\_i - y\_i                                  | ) | Grid-based movement (e.g., city streets, logistics) |
| **Euclidean Distance** | $\sqrt{\sum (x_i - y_i)^2}$ | True geometric distance in continuous spaces |   |                                                     |

✅ **Use Manhattan Distance when movement is restricted to a grid (like a taxi on city streets).**
✅ **Use Euclidean Distance when diagonal movement is allowed (like a drone flying in open space).**

---

## **5️⃣ Conclusion 🎯**

✅ **Measures grid-like distance between two points**
✅ **Used in machine learning, image processing, and recommender systems**
✅ **Best for city-based and grid-based applications**

Would you like a **visualization** or a **real-world dataset implementation**? 🚀
