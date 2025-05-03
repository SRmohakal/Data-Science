# **Cosine Similarity in Data Science** 🔍📊

## **What is Cosine Similarity?**

Cosine Similarity is a **measure of similarity** between two non-zero vectors. It is widely used in **text analysis, high-dimensional data, and recommendation systems**. Instead of measuring distance, it evaluates the **angle** between two vectors in a multi-dimensional space.

✅ **Key Idea**:

* If two vectors point in the **same direction**, they are highly similar (**cosine similarity ≈ 1**).
* If two vectors are **orthogonal** (perpendicular), they are completely different (**cosine similarity = 0**).
* If two vectors point in **opposite directions**, they are negatively related (**cosine similarity ≈ -1**).

📌 **Formula for Cosine Similarity**

$$
\cos(\theta) = \frac{A \cdot B}{||A|| \times ||B||}
$$

where:

* $A \cdot B$ is the **dot product** of vectors **A** and **B**
* $||A||$ and $||B||$ are the **magnitudes (norms)** of the vectors
* $\theta$ is the **angle** between the two vectors

---

## **1️⃣ Example Calculation**

### **Vectors**

🔹 $A = (3, 4, 5)$
🔹 $B = (1, 0, 2)$

📌 **Step 1: Compute the dot product**

$$
A \cdot B = (3 \times 1) + (4 \times 0) + (5 \times 2) = 3 + 0 + 10 = 13
$$

📌 **Step 2: Compute the magnitudes**

$$
||A|| = \sqrt{3^2 + 4^2 + 5^2} = \sqrt{9 + 16 + 25} = \sqrt{50} = 7.07
$$

$$
||B|| = \sqrt{1^2 + 0^2 + 2^2} = \sqrt{1 + 0 + 4} = \sqrt{5} = 2.24
$$

📌 **Step 3: Compute Cosine Similarity**

$$
\cos(\theta) = \frac{13}{7.07 \times 2.24} = \frac{13}{15.84} = 0.82
$$

✅ The **Cosine Similarity** between A and B is **0.82**, meaning they are **highly similar**.

---

## **2️⃣ Cosine Similarity in Python 🐍**

### **Using NumPy**

```python
import numpy as np

A = np.array([3, 4, 5])
B = np.array([1, 0, 2])

cosine_similarity = np.dot(A, B) / (np.linalg.norm(A) * np.linalg.norm(B))
print("Cosine Similarity:", cosine_similarity)
```

📌 **Output:**

```
Cosine Similarity: 0.82
```

### **Using Scikit-Learn**

```python
from sklearn.metrics.pairwise import cosine_similarity

A = np.array([[3, 4, 5]])
B = np.array([[1, 0, 2]])

similarity = cosine_similarity(A, B)
print("Cosine Similarity:", similarity[0][0])
```

📌 **Output:**

```
Cosine Similarity: 0.82
```

---

## **3️⃣ Applications of Cosine Similarity in Data Science 🚀**

📌 **1. Text Similarity & NLP** → Used in **document comparison, chatbots, and search engines**
📌 **2. Recommendation Systems** → Finds similar **users or items** based on their preferences
📌 **3. Image Recognition** → Measures similarity between image feature vectors
📌 **4. Clustering & Classification** → Used in **K-Means Clustering**, **KNN**, and **SVM**
📌 **5. Anomaly Detection** → Identifies **outliers** based on feature similarity

---

## **4️⃣ Cosine Similarity vs. Euclidean Distance**

| **Metric**             | **Measures**               | **Best For**                                    |
| ---------------------- | -------------------------- | ----------------------------------------------- |
| **Cosine Similarity**  | **Angle** between vectors  | **Text analysis, high-dimensional data**        |
| **Euclidean Distance** | **Straight-line distance** | **Continuous numeric data, physical distances** |

✅ **Use Cosine Similarity when magnitude doesn't matter (e.g., text, categorical data).**
✅ **Use Euclidean Distance when actual distance is important.**

---

## **5️⃣ Conclusion 🎯**

✅ **Cosine Similarity measures the angle between two vectors**
✅ **Used in text similarity, recommendation systems, and clustering**
✅ **Efficient for high-dimensional data (e.g., NLP, embeddings)**

Would you like a **real-world dataset example** or a **visualization**? 🚀
