# 🕵️‍♂️ Financial Fraud Detection with Imbalanced Data
This project implements **fraud detection models** on a synthetic financial transactions dataset. The main challenge addressed is the **imbalance in class distribution** (fraudulent vs legitimate transactions), which often leads to biased predictions.  
The goal is to:
- Preprocess and balance the dataset,
- Train multiple machine learning classifiers,
- Evaluate performance using robust metrics,
- Visualize results for interpretability.

---

## 🎯 Problem Statement
Financial fraud poses a serious threat to banks, businesses, and customers. Detecting fraudulent transactions is challenging because:
- Fraudulent cases are **rare** compared to legitimate ones,
- Models tend to get biased toward predicting only the majority class,
- Misclassifying fraud as legitimate can cause huge financial losses.
This project aims to build a reliable fraud detection pipeline that handles data imbalance and produces **high recall without sacrificing precision**.

---

## 📊 About the Dataset
- The dataset used: `synthetic_fraud_dataset.csv`  
- It contains **10,000+ synthetic transactions** with both fraudulent and legitimate labels.  
- Key features include:
  - `Transaction_Amount`, `Account_Balance`, `Transaction_Distance` (numeric transaction properties)  
  - `Device_Type`, `Location`, `Merchant_Category`, `Card_Type`, `Authentication_Method` (categorical transaction metadata) 
  - Target column: **`Fraud_Label`** (1 = Fraudulent, 0 = Legitimate)

---

## ⚙️ Methodology
1. **Exploratory Data Analysis (EDA)**  
   - Inspected dataset shape, column distributions, and missing values  
   - Checked fraud vs non-fraud class imbalance  

2. **Preprocessing**  
   - One-hot encoding for categorical columns  
   - Standardization of numeric features  
   - Final processed dataset built by concatenating scaled numeric + encoded categorical features  

3. **Data Splitting**  
   - Train-test split (70%-30%) with **stratification** to preserve class ratios  

4. **Models Trained**  
   - Logistic Regression  
   - Decision Tree Classifier  
   - Random Forest Classifier  
   - XGBoost Classifier  

5. **Evaluation Metrics**  
   - Confusion Matrix  
   - Accuracy, Precision, Recall, F1-score  
   - ROC Curve  

6. **Visualization**  
   - Correlation heatmap  
   - Confusion matrix heatmaps for misclassification analysis  
   - ROC curves for model comparison  

---

## 🧑‍💻 Results
- **Logistic Regression**: Served as a baseline, performed well in precision but weaker in recall.  
- **Decision Tree**: More flexible, but prone to overfitting.  
- **Random Forest**: Improved stability and recall compared to a single tree.  
- **XGBoost**: Delivered the best trade-off between precision and recall with the highest AUC.  

Overall, **ensemble methods (Random Forest & XGBoost)** handled imbalanced data more effectively.

---

## 📈 Visualizations
- **Accuracy & Loss Curves** during training  
- **Confusion Matrix Heatmap** showing classification performance  
- **ROC Curves with AUC Scores** for model comparison  

---

## ✅ Conclusion
This project successfully implemented a fraud detection pipeline with multiple ML models.  
Key takeaways:
- Class imbalance is a major challenge and must be handled via stratified splits & recall-focused evaluation.  
- Logistic Regression provides interpretability, but ensemble methods (Random Forest, XGBoost) deliver better performance.  
- ROC-AUC and confusion matrix visualizations are crucial to evaluate model effectiveness beyond accuracy.  
The framework can be extended with:
- SMOTE or other oversampling methods  
- Deep learning models (RNNs for sequential transactions)  
- Real-time fraud detection pipelines.
