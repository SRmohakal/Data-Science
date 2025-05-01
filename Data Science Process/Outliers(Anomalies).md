### **Outliers (Anomalies)**  

Outliers are data points that significantly differ from the rest of the dataset. They can be **errors, rare events, or meaningful anomalies** that need special attention.  

#### **Types of Outliers**  
1. **Global Outliers (Point Anomalies)**  
   - A single data point that is far from the rest.  
   - Example: A person's height recorded as **300 cm** instead of a normal range (150-200 cm).  

2. **Contextual Outliers**  
   - Anomalies based on context (time, season, etc.).  
   - Example: **High credit card spending** is normal on **Black Friday** but unusual on a regular day.  

3. **Collective Outliers**  
   - A group of related anomalies in the dataset.  
   - Example: A **series of failed login attempts** in a short period may indicate a **cyberattack**.  

---

### **Outliers Detection**  

#### **1. Visualization Methods**  
- **Box Plot**  
  - Values outside the "whiskers" are potential outliers.  
  - Example using Python:  
    ```python
    import seaborn as sns
    import matplotlib.pyplot as plt
    
    data = [10, 12, 13, 15, 18, 19, 35, 100]  # 100 is an outlier
    sns.boxplot(data)
    plt.show()
    ```
  
- **Scatter Plot**  
  - Helps in identifying outliers in 2D data.  

- **Histogram/Density Plot**  
  - Shows distribution and extreme values.  

---

#### **2. Statistical Methods**  
- **Z-Score (Standard Score Method)**  
  - Measures how many standard deviations a value is from the mean.  
  - Formula:
    ``` 
    Z = (X - μ) / σ
    ```
  - A common threshold is **|Z| > 3**.  

  ```python
  from scipy.stats import zscore
  import numpy as np
  
  data = np.array([10, 12, 13, 15, 18, 19, 35, 100])
  z_scores = zscore(data)
  outliers = data[abs(z_scores) > 3]
  print(outliers)  # Output: [100]
  ```

- **Interquartile Range (IQR) Method**  
  - Outliers lie outside **1.5 times** the IQR.  
  - Formula:
  ```
    \[
    IQR = Q3 - Q1
    \]
    \[
    \text{Lower Bound} = Q1 - 1.5 \times IQR
    \]
    \[
    \text{Upper Bound} = Q3 + 1.5 \times IQR
    \]
  ```
  ```python
  import numpy as np
  
  Q1, Q3 = np.percentile(data, [25, 75])
  IQR = Q3 - Q1
  lower_bound = Q1 - 1.5 * IQR
  upper_bound = Q3 + 1.5 * IQR
  outliers = data[(data < lower_bound) | (data > upper_bound)]
  print(outliers)  # Output: [100]
  ```

---

### **3. Machine Learning Methods**
- **Isolation Forest (Unsupervised Anomaly Detection)**
  ```python
  from sklearn.ensemble import IsolationForest
  data = np.array(data).reshape(-1, 1)
  model = IsolationForest(contamination=0.1)
  outliers = model.fit_predict(data)
  print(outliers)  # -1 indicates outliers
  ```

- **DBSCAN (Density-Based Clustering)**  
  - Detects anomalies based on density.  

- **Autoencoders (Deep Learning for Outliers)**  
  - Used for high-dimensional data like images.  

---

### **Outliers handling**
1. **Remove Outliers** (if they are errors).  
2. **Transform Data** (log transformation to reduce impact).  
3. **Use Robust Models** (Decision Trees, Random Forest).  
4. **Impute Outliers** (replace them with median values).  

---

### **Use Cases of Outlier Detection**
✅ **Fraud Detection** (Unusual credit card transactions).  
✅ **Cybersecurity** (Detecting hacking attempts).  
✅ **Healthcare** (Identifying abnormal patient vitals).  
✅ **Finance** (Stock market price anomalies).  

---
