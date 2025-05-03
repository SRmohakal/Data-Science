# **Class Conditional Probability in Data Science** 📊

## **What is Class Conditional Probability?**

Class conditional probability is the probability of a feature **given a specific class** in classification tasks. It plays a crucial role in **Bayesian classification models**, especially **Naïve Bayes**.

📌 **Mathematically:**

$$
P(X | C) = \frac{P(C | X) P(X)}{P(C)}
$$

where:

* $P(X | C)$ → **Class conditional probability** (Probability of feature $X$ given class $C$)
* $P(C | X)$ → Posterior probability (Probability of class $C$ given feature $X$)
* $P(X)$ → Evidence (Probability of feature $X$)
* $P(C)$ → Prior probability (Probability of class $C$)

---

## **1️⃣ Importance of Class Conditional Probability**

✔ **Used in Bayesian models** like **Naïve Bayes**
✔ Helps in **calculating posterior probability** in classification
✔ Assists in **feature selection and importance estimation**

---

## **2️⃣ Example in Naïve Bayes Classification**

### **Email Spam Detection (Example)**

Let's assume we want to classify an email as **Spam** or **Not Spam** based on words in the email.

* **Feature (X):** Word "FREE" appears in an email
* **Class (C):** The email is Spam (S) or Not Spam (NS)

#### **Class Conditional Probability Calculation**

$$
P(\text{FREE} | \text{Spam}) = \frac{\text{Emails with "FREE" and Spam}}{\text{Total Spam Emails}}
$$

$$
P(\text{FREE} | \text{Not Spam}) = \frac{\text{Emails with "FREE" and Not Spam}}{\text{Total Not Spam Emails}}
$$

🔹 **If $P(\text{FREE} | \text{Spam}) > P(\text{FREE} | \text{Not Spam})$, the email is more likely Spam!**

---

## **3️⃣ Python Example**

### **Using Naïve Bayes for Spam Classification**

```python
from sklearn.naive_bayes import MultinomialNB
from sklearn.feature_extraction.text import CountVectorizer

# Sample data
emails = ["Win a FREE iPhone", "Exclusive Offer just for you", "Meeting at 10 AM"]
labels = [1, 1, 0]  # 1 = Spam, 0 = Not Spam

# Convert text to feature matrix
vectorizer = CountVectorizer()
X = vectorizer.fit_transform(emails)

# Train Naïve Bayes model
model = MultinomialNB()
model.fit(X, labels)

# Check class conditional probability (P(X|C))
print("Class Conditional Probabilities:\n", model.feature_log_prob_)
```

📌 The output shows **log probabilities** of words **given each class (spam or not spam).**

---

## **4️⃣ Applications in Data Science 🚀**

✅ **Spam Filtering** → Probability of words appearing in spam vs. non-spam
✅ **Medical Diagnosis** → Probability of symptoms given a disease
✅ **Sentiment Analysis** → Probability of words in positive vs. negative reviews
✅ **Fraud Detection** → Probability of transactions given fraudulent behavior

---

## **5️⃣ Summary 🎯**

✔ **Class conditional probability helps in probabilistic classification**
✔ **Used in Naïve Bayes and other Bayesian models**
✔ **Crucial for spam detection, fraud analysis, and medical predictions**

Would you like a **real-world dataset example**? 🚀
