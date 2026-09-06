# 🛒 E-Commerce Orders Dataset

## 📌 Overview
This repository contains a cleaned dataset of e-commerce transactions.  
It includes details such as:
- Order information (OrderID, Date, CustomerID)
- Product details (Product, Quantity, UnitPrice, TotalPrice)
- Customer details (ShippingAddress, PaymentMethod)
- Order tracking (OrderStatus, TrackingNumber)
- Marketing insights (CouponCode, ReferralSource)

The dataset is useful for **data analytics, machine learning, and business intelligence projects**.

---

## 📂 Files
- `Cleaned_Dataset.csv` → Cleaned version of the dataset
- `Dataset for Data Analytics.xlsx` → Original dataset in Excel format

---

## 📊 Columns Description
| Column Name      | Description |
|------------------|-------------|
| OrderID          | Unique order identifier |
| Date             | Order date |
| CustomerID       | Unique customer identifier |
| Product          | Product name |
| Quantity         | Number of items ordered |
| UnitPrice        | Price per unit |
| ShippingAddress  | Customer shipping address |
| PaymentMethod    | Mode of payment (Debit Card, Credit Card, etc.) |
| OrderStatus      | Current status (Shipped, Pending, etc.) |
| TrackingNumber   | Shipment tracking number |
| ItemsInCart      | Total items in cart |
| CouponCode       | Applied coupon code |
| ReferralSource   | Source of referral (Instagram, Facebook, etc.) |
| TotalPrice       | Final order amount |

---

## 🚀 Usage
You can use this dataset for:
- **Exploratory Data Analysis (EDA)**
- **Sales trend analysis**
- **Customer segmentation**
- **Coupon & referral effectiveness**
- **Machine Learning models** (prediction, classification)

---

## 🛠️ Example (Python Pandas)
```python
import pandas as pd

# Load dataset
df = pd.read_csv("Cleaned_Dataset.csv")

# Quick overview
print(df.head())

# Total revenue
print("Total Revenue:", df["TotalPrice"].sum())
