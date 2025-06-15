# 🧠 Loan Approval Prediction with Machine Learning & Neural Networks

## 🔍 Problem Statement

This project explores the prediction of loan approvals using both classical Machine Learning algorithms and Neural Networks. The primary objective is to enhance prediction performance by applying optimization and regularization techniques. The task involves binary classification — determining whether a loan application should be **Approved** or **Rejected** based on features like income, employment, credit history, and more.

### 📊 Dataset Used

We use a custom loan approval dataset (`loan_data.csv`) that includes both categorical and numerical variables. After preprocessing, the feature set is one-hot encoded and scaled for training.

---

## 📌 Key Findings (Performance Summary)

| Model                | Optimizer | Regularization | Accuracy | F1 Score | Recall | Precision | Notes                      |
|---------------------|-----------|----------------|----------|----------|--------|-----------|----------------------------|
| Logistic Regression | -         | None           | 0.9610   | 0.9620   | 0.9700 | 0.9500    | Best traditional ML model |
| Neural Net 1        | Adam      | None           | 0.7792   | 0.8046   | 0.8974 | 0.7292    | No optimization baseline  |
| Neural Net 2        | Adam      | L1             | 0.5065   | 0.6724   | 1.0000 | 0.5065    | Overfitting observed      |
| Neural Net 3        | RMSprop   | L2             | 0.4935   | 0.0000   | 0.0000 | 0.0000    | Poor generalization       |
| Neural Net 4        | SGD       | L1             | 0.7273   | 0.8205   | 1.0000 | 0.6974    | Balanced NN performance   |

---

## ✅ Best Performing Combination

- **Traditional Algorithm**: Logistic Regression without any regularization or optimization outperformed all neural models in both accuracy and F1 score.
- **Neural Network**: The best-performing neural model was `model_4`, which used:
  - Optimizer: **SGD**
  - Regularization: **L1**
  - Architecture: **[64, 32, 16]**

---

## 🔬 Discussion: ML Algorithm vs. Neural Network

While Neural Networks offer flexibility and can model complex patterns, the classical Logistic Regression model delivered the highest performance for this dataset. This suggests that the dataset's complexity and size were better suited for simpler models. Key takeaways:

- **Logistic Regression** was robust, generalizable, and efficient.
- **Neural Networks** showed potential with optimization, but some configurations (like L2 + RMSprop) led to underfitting or training instability.
- The application of **regularization (L1/L2)** and **early stopping** influenced performance, especially in preventing overfitting.

---

## 📁 Project Structure

