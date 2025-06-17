Sure! Here's a concise summary of the **Introduction** and **Problem Statement**:

---

### ✅ **Introduction**

AgriEmpower Rwanda aims to improve loan access for women-led agricultural cooperatives in rural Rwanda. These women are vital to the farming sector but are often excluded from formal credit due to lack of documentation and digital access. The project uses machine learning and alternative data—like crop yields and airtime usage—to assess loan eligibility via a web platform, enabling remote, fairer loan applications.

---

### ❗ **Problem Statement**

Rural women face systemic barriers to credit because traditional lending requires documents, collateral, and bank proximity. Existing ML credit tools are built for urban users with smartphones, excluding rural women. AgriEmpower offers a solution by using locally relevant data and an interpretable ML model to predict loan eligibility, promoting financial inclusion.


### 📊 Dataset Used

This project uses a publicly available loan approval dataset sourced from Kaggle, titled loan_data.csv. The dataset includes both categorical and numerical variables relevant to loan eligibility, such as income, employment status, credit history, and loan amount.

After preprocessing, the data is cleaned, one-hot encoded for categorical features, and scaled to optimize training performance for both traditional machine learning models and neural networks.

The link to the dataset: https://www.kaggle.com/datasets/abhishekmishra08/loan-approval-datasets?select=loan_data.csv
---

## 📌 Performance Summary




| Train Instance | Model               | Regularizer | Optimizer | Epochs | Early Stopping | Number of Layers | Dropout Rate | Accuracy | F1 Score | Recall | Precision | Notes                           |
| -------------- | ------------------- | ----------- | --------- | ------ | -------------- | ---------------- | ------------ | -------- | -------- | ------ | --------- | ------------------------------- |
| 1              | Logistic Regression | None        | -         | -      | -              | -                | -            | 0.9264   | 0.7782   | 0.7881 | 0.7686    | Baseline traditional model      |
| 2              | CNN                 | L1          | Adam      | 100    | patience=12    | 7                | 0.3          | 0.9864   | 0.9586   | 0.9627 | 0.9546    | Strong performance, L1 + Adam   |
| 3              | CNN                 | L2          | RMSprop   | 100    | patience=12    | 7                | 0.3          | 0.9889   | 0.9669   | 0.9915 | 0.9435    | Highest recall, L2 + RMSprop    |
| 4              | CNN                 | L1          | SGD       | 100    | patience=12    | 7                | 0.3          | 0.9300   | 0.7801   | 0.7576 | 0.8040    | Lower recall, good precision    |
| 5              | CNN                 | L2          | Adagrad   | 100    | patience=12    | 7                | 0.3          | 0.9864   | 0.9578   | 0.9424 | 0.9737    | High precision, stable F1 score |


---

✅ Best Performing Combination
Traditional Algorithm: Logistic Regression performed reasonably well with an accuracy of 0.9264, but it was outperformed by all neural network models.

Neural Network: The best-performing neural model was Model 3, which used:

Optimizer: RMSprop

Regularization: L2

Dropout Rate: 0.3

Architecture: [64, 32, 16] (7-layer network including dropout)

Performance:

Accuracy: 0.9889

F1 Score: 0.9669

Recall: 0.9915

Precision: 0.9435

This model provided the most balanced and accurate predictions, making it the most reliable option among all configurations tested.



---

🔬 Discussion: ML Algorithm vs. Neural Network
While classical models like Logistic Regression provided strong baseline performance, Neural Networks clearly outperformed traditional algorithms on this dataset. The best-performing model was a CNN with L2 regularization and RMSprop optimizer, achieving the highest accuracy, F1 score, and recall. This highlights the capacity of neural networks to capture complex, nonlinear patterns when properly regularized and optimized.

Key Takeaways:
Neural Networks, especially when combined with L2 regularization and RMSprop, offered superior performance, demonstrating their ability to generalize well even on structured tabular data.

Logistic Regression remained competitive and was a strong baseline, especially in contexts requiring interpretability and low computational cost.

The use of regularization (L1/L2), dropout, and early stopping played a critical role in enhancing model stability and preventing overfitting.

Model performance varied significantly across different optimizers and regularizers, underscoring the importance of hyperparameter tuning.

---

🎥 Demo Video
A walkthrough of the loan approval prediction system, including model training, evaluation is available in the video below:

Link to the demo video: 

