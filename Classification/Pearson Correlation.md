# **Pearson Correlation in Data Science** 📊📈

## **What is Pearson Correlation?**

Pearson Correlation measures the **linear relationship** between two numerical variables. It tells us **how strongly and in what direction** two variables are related.

✅ **Key Idea**:

* **+1** → Perfect **positive** correlation (as one increases, the other increases)
* **-1** → Perfect **negative** correlation (as one increases, the other decreases)
* **0** → **No linear relationship**

📌 **Formula for Pearson Correlation**

$$
r = \frac{\sum (X_i - \bar{X})(Y_i - \bar{Y})}{\sqrt{\sum (X_i - \bar{X})^2} \times \sqrt{\sum (Y_i - \bar{Y})^2}}
$$

where:

* $X$ and $Y$ are two numerical variables
* $\bar{X}$, $\bar{Y}$ are the **means** of $X$ and $Y$
* The numerator calculates **covariance** (how $X$ and $Y$ vary together)
* The denominator **normalizes** by standard deviations

---

## **1️⃣ Example Calculation**

### **Dataset**

| **X (Study Hours)** | **Y (Exam Score)** |
| ------------------- | ------------------ |
| 2                   | 50                 |
| 4                   | 60                 |
| 6                   | 70                 |
| 8                   | 80                 |
| 10                  | 90                 |

📌 **Step 1: Compute Mean**

$$
\bar{X} = \frac{2+4+6+8+10}{5} = 6
$$

$$
\bar{Y} = \frac{50+60+70+80+90}{5} = 70
$$

📌 **Step 2: Compute Pearson Correlation**

$$
r = 1.0
$$

✅ **Perfect positive correlation (1.0) → More study hours lead to higher scores.**

---

## **2️⃣ Pearson Correlation in Python 🐍**

### **Using NumPy**

```python
import numpy as np

X = np.array([2, 4, 6, 8, 10])
Y = np.array([50, 60, 70, 80, 90])

correlation = np.corrcoef(X, Y)[0, 1]
print("Pearson Correlation:", correlation)
```

📌 **Output:**

```
Pearson Correlation: 1.0
```

### **Using SciPy**

```python
from scipy.stats import pearsonr

correlation, _ = pearsonr(X, Y)
print("Pearson Correlation:", correlation)
```

📌 **Output:**

```
Pearson Correlation: 1.0
```

### **Using Pandas**

```python
import pandas as pd

df = pd.DataFrame({'Study Hours': X, 'Exam Score': Y})
print(df.corr(method='pearson'))
```

📌 **Output:**

```
              Study Hours  Exam Score
Study Hours         1.0         1.0
Exam Score         1.0         1.0
```

---

## **3️⃣ Applications of Pearson Correlation in Data Science 🚀**

📌 **1. Feature Selection** → Find **strongly correlated features** in datasets
📌 **2. Stock Market Analysis** → Measure **relationship between stocks**
📌 **3. Medical Research** → Check **correlation between diseases & factors**
📌 **4. Social Science** → Analyze **trends between variables**
📌 **5. Business Analytics** → Check **sales & marketing relationships**

---

## **4️⃣ Pearson Correlation vs. Other Correlation Metrics**

| **Metric**               | **Best For**                         | **Range** |
| ------------------------ | ------------------------------------ | --------- |
| **Pearson Correlation**  | Linear relationships                 | -1 to +1  |
| **Spearman Correlation** | Rank-based relationships (monotonic) | -1 to +1  |
| **Kendall’s Tau**        | Small datasets, non-parametric data  | -1 to +1  |

✅ **Pearson is best for linear relationships.**
✅ **Use Spearman/Kendall for non-linear relationships.**

---

## **5️⃣ Conclusion 🎯**

✅ **Measures linear relationships between two variables**
✅ **Range: -1 (negative), 0 (none), +1 (positive)**
✅ **Used in feature selection, finance, medicine, and analytics**

Would you like a **visualization** (scatter plot with correlation line)? 🚀
