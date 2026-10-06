# -Restaurant-Food-Preparation-Predictor
Restaurant Food Preparation Predictor uses NLP, TF-IDF, and XGBoost to predict optimal food preparation quantities from dish descriptions, historical orders, and restaurant conditions, helping improve planning, inventory management, and reduce food waste
# 🍽️ Restaurant Food Preparation Predictor

### NLP + TF-IDF + XGBoost

A Machine Learning and Natural Language Processing project that predicts the optimal quantity of food to prepare in a restaurant using dish descriptions, historical orders, restaurant conditions, and other relevant features.

The system is designed to support better preparation planning and help reduce unnecessary food waste.

---

## 📌 Project Overview

Restaurants need to estimate how much food should be prepared for upcoming demand. Preparing too much can increase food waste, while preparing too little can lead to poor dish availability.

This project combines **NLP and Machine Learning** to predict the required preparation quantity based on restaurant and dish-related information.

The project uses **TF-IDF** to convert dish names and descriptions into numerical features and **XGBoost Regression** to predict the preparation quantity.

---

## 🎯 Objectives

* Predict the optimal quantity of food to prepare.
* Analyze dish names and descriptions using NLP.
* Use historical restaurant order information.
* Consider restaurant conditions such as weather, season, and events.
* Improve food preparation planning.
* Help reduce unnecessary food waste.

---

## 📊 Dataset

The project uses a dataset containing approximately **100,000 restaurant records**.

### Target Variable

`Quantity_Prepared`

### Features

#### 📝 NLP Features

* `Dish_Name`
* `Description`

#### 🏷️ Categorical Features

* `Category`
* `Day`
* `Season`
* `Weather`
* `Event`

#### 🔢 Numerical Features

* `Month`
* `Price`
* `Prep_Time`
* `Previous_Orders`
* `Stock`

Example records include dishes such as Chicken Biryani, Caesar Salad, and Chocolate Lava Cake.

---

## 🧠 NLP Pipeline

The text data from the dish name and description is processed using **TF-IDF (Term Frequency–Inverse Document Frequency)**.

### Processing Steps

```text
Raw Text
   ↓
Lowercase
   ↓
Remove Punctuation
   ↓
Remove Stop Words
   ↓
TF-IDF Vectorization
   ↓
Numerical Feature Matrix
```

The project uses:

* Unigrams
* Bigrams
* Maximum 1000 TF-IDF features
* English stop-word filtering

This converts dish-related text into numerical vectors that can be used by the Machine Learning model.

---

## ⚙️ Feature Engineering

Several preprocessing and feature-engineering techniques are applied:

### Log Transformation

Applied to:

* `Previous_Orders`
* `Ingredients_Stock`

### Weekend Indicator

`Day_of_Week` is converted into a binary weekend indicator.

### One-Hot Encoding

Applied to:

* Category
* Season
* Weather
* Event

### Standard Scaling

Applied to:

* Price
* Prep_Time
* Month

These features are combined with the NLP features before model training.

---

## 🤖 Machine Learning Model

### XGBoost Regression

The primary model used in this project is **XGBoost Regression**.

The final feature set combines:

```text
TF-IDF Text Features
        +
Categorical Features
        +
Numerical Features
        +
Engineered Features
        ↓
     XGBoost
        ↓
Predicted Quantity
```

### Why XGBoost?

* Handles nonlinear relationships.
* Works effectively with mixed feature types.
* Efficient for large datasets.
* Captures interactions between features.

---

## 📈 Model Evaluation

The model is evaluated using:

* **MAE** – Mean Absolute Error
* **RMSE** – Root Mean Squared Error
* **R² Score** – Variance Explained
* **3-Fold Cross-Validation**

Hyperparameter tuning includes parameters such as:

* Number of estimators
* Learning rate
* Maximum tree depth

> Note: The project presentation does not provide the final numerical evaluation results, so those values should be added after the trained model output is available.

---

## 🖥️ Prediction Interface

The project uses **Gradio** as the user interface.

Restaurant staff can enter dish details and restaurant conditions, after which the system provides a preparation recommendation.

### Example Output

```text
Recommended Preparation: XX portions
Expected Demand: XX portions
```

The presentation specifies Gradio as the interface for the prediction system.

---

## 🌍 Real-World Applications

### Restaurant Owners & Managers

* Cost control
* Inventory planning
* Better preparation decisions

### Chefs

* Data-driven production planning
* Better preparation decisions

### Customers

* Improved dish availability

### Environment

* Reduction of unnecessary food waste

---

## 🚀 Future Improvements

The project can be extended with:

### Advanced NLP

* BERT
* Sentence Transformers

### Real-Time AI

* Live order data
* Weather information
* Food-waste tracking

### Cloud & Mobile

* Web application
* Mobile deployment

The current system uses TF-IDF + XGBoost, with advanced NLP, real-time AI, and cloud/mobile deployment identified as future directions.

---

## 🛠️ Technologies Used

| Technology   | Purpose                    |
| ------------ | -------------------------- |
| Python       | Programming                |
| Pandas       | Data Processing            |
| NumPy        | Numerical Computing        |
| Scikit-learn | Preprocessing & Evaluation |
| TF-IDF       | NLP Feature Extraction     |
| XGBoost      | Regression Model           |
| Gradio       | User Interface             |
| Matplotlib   | Visualization              |

---

## 📂 Project Structure

```text
Restaurant-Food-Preparation-Predictor/
│
├── dataset/
│   └── restaurant_food_data.csv
│
├── notebooks/
│   └── restaurant_food_prediction.ipynb
│
├── models/
│   └── xgboost_model.pkl
│
├── app.py
├── requirements.txt
├── README.md
└── Restaurant-Food-Preparation-Predictor.pptx
```

---

## 🔄 Project Workflow

```text
Restaurant Dataset
       ↓
Data Cleaning
       ↓
Text Preprocessing
       ↓
TF-IDF Vectorization
       ↓
Feature Engineering
       ↓
Feature Combination
       ↓
Train-Test Split
       ↓
XGBoost Regression
       ↓
Model Evaluation
       ↓
Gradio Interface
       ↓
Food Preparation Recommendation
```

---

## 💡 Key Outcome

The project demonstrates how **NLP and Machine Learning can work together** to transform dish descriptions and restaurant data into a practical food-preparation prediction system.

The overall goal is to move from simple prediction toward intelligent restaurant decision support while improving preparation planning and reducing unnecessary food waste.

---

## 👨‍💻 Project Information

**Project:** Restaurant Food Preparation Predictor
**Technologies:** NLP · TF-IDF · XGBoost
**Institution:** TRYCOD Tech School
**Project Type:** Academic Machine Learning Project

---

## ⭐ Future Vision

> From prediction → to intelligent real-time restaurant decision support.

If you find this project useful, consider giving the repository a ⭐ on GitHub.
