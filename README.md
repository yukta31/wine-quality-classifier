# Wine Quality Classifier

A Decision Tree classifier built **from scratch** (without sklearn's DecisionTreeClassifier) to classify wine types based on physicochemical properties. Implements Gini index splitting, information gain calculation, and recursive tree building manually in Python.

Built as part of CS580 (Introduction to Artificial Intelligence) at George Mason University.

---

## 📊 Results

| Class | Precision | Recall | F1 Score | Support |
|-------|-----------|--------|----------|---------|
| Type 1 | 1.00 | 1.00 | 1.00 | 2 |
| Type 2 | 0.75 | 0.75 | 0.75 | 4 |
| Type 3 | 0.75 | 0.75 | 0.75 | 4 |
| **Overall** | **0.80** | **0.80** | **0.80** | **10** |

> **Accuracy: 80%** — custom Decision Tree (min_samples_split=2, max_depth=3)

**Generated Decision Tree:**
```
X_6 (Flavanoids) <= 1.09 → Type 3
Otherwise:
  X_12 (Proline) <= 750.0 → Type 2
  Otherwise → Type 1
```

Flavanoids and Proline are the top two discriminating features for wine type classification.

---

## 🌳 What Makes This Different

Most ML projects use `sklearn.DecisionTreeClassifier`. This project implements the full decision tree **from scratch**, including:

- **Node class** — stores feature index, threshold, left/right children, info gain
- **Gini Index** — impurity measure for split evaluation
- **Information Gain** — selects the best feature/threshold at each node
- **Recursive tree building** — splits until min_samples or max_depth reached
- **Leaf value calculation** — majority class voting
- **Feature importance** — calculated from split frequency across the tree

---

## 🎯 Objective

Classify wine samples into 3 types based on 13 physicochemical features including alcohol content, flavanoids, proline, color intensity, and more.

---

## 📂 Dataset

- **Source:** UCI Machine Learning Repository — Wine Dataset
- **Samples:** 30 total · 10 test samples
- **Features:** 13 physicochemical properties
- **Target:** Wine Type (1, 2, 3)
- **Split:** 70/30 train/test with random_state=41

---

## 🔧 Tech Stack

- **Language:** Python 3
- **Libraries:** NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn (accuracy_score only)
- **Algorithm:** Custom Decision Tree (Gini index, recursive splitting)

---

## 🚀 How to Run

```bash
git clone https://github.com/yukta31/wine-quality-classifier.git
cd wine-quality-classifier
pip install numpy pandas matplotlib seaborn scikit-learn
python wine_classifier.py
```

---

## 📁 Files

| File | Description |
|------|-------------|
| `wine_classifier.py` | Full implementation — custom Decision Tree from scratch |
| `wines.csv` | Wine dataset with 13 physicochemical features |
| `Project_Report.pdf` | Full project report with methodology and analysis |

---

## 🧠 Key Findings

- **Flavanoids** (feature X_6) is the most discriminating feature — threshold ≤ 1.09 perfectly separates Type 3
- **Proline** (feature X_12) is the second most important — threshold ≤ 750 separates Type 2 from Type 1
- The shallow tree (depth=3) achieves 80% accuracy with just 2 decision nodes

---

## 👩‍💻 Author

**Yukta Batra** — MS Computer Science, George Mason University

[Portfolio](https://yukta-batra.vercel.app) · [LinkedIn](https://linkedin.com/in/yuktabatra31) · [GitHub](https://github.com/yukta31)
