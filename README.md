# 🛒 JioMart Stock Price Prediction

This project aims to build a machine learning model that predicts the **discounted price** of products listed on [JioMart](https://www.jiomart.com/) using features such as original price, category, subcategory, and product title. The goal is to assist with dynamic pricing strategies and gain insights into how discounts are applied across product types.

---

## 📂 Dataset Overview

The dataset used is `ProductsDB - JioMart.csv`, containing 5,672 products with the following columns:

| Column           | Description                                               |
|------------------|-----------------------------------------------------------|
| `title`          | Product name (e.g., "Besan 1 kg")                         |
| `discountedPrice`| Final price after discount                                |
| `price`          | Original price before discount                            |
| `filename`       | Image URL of the product (not used in this model)         |
| `subType`        | Sub-category (e.g., "Atta, Flours and Sooji")             |
| `type`           | Main category (e.g., "Staples")                           |

---

## 🎯 Objective

The objective is to predict the **`discountedPrice`** of a product using:
- Original price (`price`)
- Product category (`type`)
- Sub-category (`subType`)
- Product title (`title`)

---

## 🧠 Approach

### 1. Preprocessing
- Categorical columns (`title`, `type`, `subType`) are encoded using `LabelEncoder`.
- The image URL column (`filename`) is dropped.

### 2. Feature & Target Selection
- **Features**: `title`, `price`, `subType`, `type`
- **Target**: `discountedPrice`

### 3. Model
- A `RandomForestRegressor` is used for training.
- The dataset is split into training (80%) and test (20%) sets.

### 4. Evaluation
- Model is evaluated using:
  - **Mean Absolute Error (MAE)**
  - **R² Score**
- Visualization of actual vs predicted values using a scatter plot.

---

## 📈 Results

The model shows a strong ability to estimate discounted prices, indicating:
- Price and category have a significant influence on discounting.
- The Random Forest algorithm performs well on tabular retail data.

---

## 📊 Visualization

A scatter plot compares actual vs predicted discounted prices to evaluate the model’s accuracy visually.

---

## 🛠️ Technologies Used

- **Python 3**
- **Pandas**
- **Scikit-learn**
- **Matplotlib**

---

## 🔮 Future Improvements

- Use **TF-IDF vectorization** or **word embeddings** for better feature extraction from product titles.
- Experiment with **advanced models** like XGBoost or LightGBM.
- Implement **hyperparameter tuning** for performance improvement.
- Extend model to include **image features** using CNNs (optional advanced step).

---

## 📁 Project Structure

```text
jio_mart_stock_price_prediction/
│
├── ProductsDB - JioMart.csv       # Dataset
├── JioMart_stock_price.ipynb      # Main notebook with modeling code
├── README.md                      # Project overview and documentation
