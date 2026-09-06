# Fraud Detection Model — Project 2

## 📌 Overview
This project focuses on detecting fraudulent e-commerce transactions using machine learning techniques.  
The dataset contains order details, product information, customer details, and order status.  
Fraudulent transactions are defined as orders with status **Cancelled** or **Returned**.

---

## 📂 Dataset
- **Cleaned_Dataset.csv** — Preprocessed dataset of e-commerce orders  
- **Features included:**
  - OrderID, Date, CustomerID
  - Product, Quantity, UnitPrice, TotalPrice
  - ShippingAddress, PaymentMethod
  - OrderStatus, TrackingNumber
  - CouponCode, ReferralSource
- **Target Variable:** `FraudFlag` (1 = Fraud, 0 = Legit)

---

## ⚙️ Preprocessing
- Converted `Date` into **Year, Month, Day** features
- Applied **One-Hot Encoding** for categorical variables
- Handled class imbalance using **SMOTE (Synthetic Minority Oversampling Technique)**

---

## 🧠 Models Used
1. **Logistic Regression** (with StandardScaler pipeline)  
2. **Random Forest Classifier** (100 estimators)

---

## 📊 Results
- Both models achieved **100% accuracy** on test data  
- **ROC-AUC Score:** 1.0 for both Logistic Regression and Random Forest  
- **Confusion Matrix:** Perfect classification (no false positives/negatives)

---

## 🔑 Key Features (Top 10 by Random Forest Importance)
- OrderStatus (Shipped, Returned, Pending, Delivered)  
- UnitPrice  
- TotalPrice  
- Month, Day  
- ItemsInCart  
- Quantity  

---

## 📦 Model Deployment
- Trained Random Forest pipeline saved as `fraud_detection_model.pkl` using **joblib**  
- Example prediction:
  ```python
  new_data = pd.DataFrame({
      "Quantity":[2],
      "UnitPrice":[500],
      "TotalPrice":[1000],
      "ItemsInCart":[1],
      "Month":[9],
      "Day":[6],
      "OrderStatus_Delivered":[1],
      "OrderStatus_Returned":[0],
      "OrderStatus_Pending":[0],
      "OrderStatus_Shipped":[0]
  })
  prediction = model.predict(new_data)
  print("Fraud Prediction:", prediction)
