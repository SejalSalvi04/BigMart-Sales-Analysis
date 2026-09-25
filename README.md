# 🛒 BigMart Sales Prediction

> A machine learning web application that predicts item-level sales for BigMart outlets based on product and store attributes — built using Python, Random Forest, and Flask.

---

## 📌 Project Overview

BigMart is a retail chain with multiple outlets across different cities. Each outlet sells a variety of products across categories. The goal of this project is to **predict the historical sales** of each product at a given outlet using key product and store features.

This project covers the full data science pipeline:
- Data cleaning & preprocessing
- Feature engineering
- Model training & evaluation
- Deployment as an interactive web application

---

## 📂 Dataset

- **Source :** [BigMart Sales Dataset — Kaggle](https://www.kaggle.com/datasets/brijbhushannanda1979/bigmart-sales-data)
- **Records :** 8,523 rows × 12 columns
- **Target Variable :** `Item_Outlet_Sales` (historical sales in ₹)

### Key Features Used

| Feature | Description |
|---|---|
| `Item_Weight` | Weight of the product (kg) |
| `Item_Visibility` | Display area ratio of the product in the store |
| `Item_MRP` | Maximum Retail Price of the product (₹) |
| `Item_Fat_Content` | Low Fat / Regular |
| `Item_Type` | Product category (e.g. Dairy, Snacks, Beverages) |
| `Outlet_Size` | Size of the store (Small / Medium / High) |
| `Outlet_Location_Type` | City tier (Tier 1 / 2 / 3) |
| `Outlet_Type` | Type of outlet (Grocery Store / Supermarket) |
| `Outlet_Age` | Age of the outlet (derived from establishment year) |

---

## 🧠 Model Summary

| Metric | Value |
|---|---|
| Algorithm | Random Forest Regressor |
| MAE | 762.37 |
| RMSE | 1093.17 |
| R² Score | 0.56 |
| Mean Sales | ₹ 2181.29 |
| Forecast Error | 35.0% |

> **Note:** The model predicts **past/historical sales** based on outlet data collected up to 2013. It is not a future sales forecasting model.

---

## 🛠️ Technologies Used

| Category | Tools |
|---|---|
| Language | Python 3.8+ |
| Data Handling | Pandas, NumPy |
| Machine Learning | Scikit-learn (Random Forest Regressor) |
| Model Saving | Pickle |
| Web Framework | Flask |
| Frontend | HTML, CSS (custom dark UI) |
| Templating | Jinja2 |
| IDE / Notebook | Google Colab, VS Code |

---

## 📁 Project Structure

```
BigMart-Sales-Prediction/
│
├── app.py                  # Flask web application
├── model.pkl               # Trained Random Forest model
├── requirements.txt        # Python dependencies
│
├── templates/
│   └── index.html          # Frontend web interface
│
├── SejalSalvi_BigMartAnalysis.ipynb   # Full ML notebook
├── bigmart.csv             # Dataset (or link to Kaggle)
└── README.md               # Project documentation
```

---

## ⚙️ Setup & Run Instructions

### Step 1 — Clone the Repository
```bash
git clone https://github.com/SejalSalvi04/BigMart-Sales-Prediction.git
cd BigMart-Sales-Prediction
```

### Step 2 — Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 3 — Run the Flask App
```bash
python app.py
```

### Step 4 — Open in Browser
```
http://127.0.0.1:5000/
```

> Enter Item Weight, Item Visibility, and Item MRP → Select prediction period (Weekly / Monthly / Yearly) → Click **Predict Sales**

---

## 🌐 Web Application Features

- Clean, responsive dark-themed UI
- Input fields for key product features
- **Time period selector** — Weekly / Monthly / Yearly
- Displays predicted sales with context (based on historical data)
- Built with Flask + Jinja2 templating

---

## 📊 Key Insights from Analysis

- **Item MRP** is the strongest predictor of sales — higher-priced items tend to generate more revenue
- **Outlet Type** significantly impacts sales — Supermarket Type 1 outperforms all others
- **Tier 3 city outlets** surprisingly contributed higher sales despite lower item visibility
- Items with **low visibility** don't always mean low sales — outlet type matters more

