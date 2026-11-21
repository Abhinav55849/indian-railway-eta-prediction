# 🚆 Indian Railway ETA Prediction Using Machine Learning

A Machine Learning-based project that estimates train arrival time (ETA) using historical railway delay records, train schedules, route information, and feature engineering.

The project explores how historical train delay patterns and remaining journey information can be used to predict the expected time required for a train to reach its destination.

---

## 📌 Project Overview

Indian Railways operates one of the largest railway networks in the world. Train delays can create uncertainty for passengers and affect travel planning.

This project aims to estimate the remaining journey time of a train by combining:

- Historical train delay information.
- Scheduled remaining journey time.
- Train route and station information.
- Historical average, maximum, and minimum delays.
- Remaining distance to the destination.

A Random Forest Regression model is trained to predict the expected ETA in minutes.

---

## 🎯 Project Objectives

- Analyze historical Indian railway delay data.
- Process train schedules and route information.
- Calculate remaining distance for each train.
- Extract historical delay statistics.
- Perform feature engineering.
- Train and evaluate multiple Machine Learning regression models.
- Predict estimated arrival time in minutes.
- Save the trained model and preprocessing artifacts for reuse.

---

## 🛠️ Tech Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Data Processing | Pandas, NumPy |
| Machine Learning | Scikit-learn |
| Algorithms | Random Forest, Decision Tree, Linear Regression |
| Data Visualization | Matplotlib |
| Data Format | CSV, JSON, Pickle |
| Model Serialization | Joblib |
| Development Environment | Jupyter Notebook |

---

## 🧠 Machine Learning Workflow

The project follows these steps:

### 1. Data Collection
Load historical delay records, train details, schedules, station information, and train route datasets.

### 2. Data Preprocessing
- Handle missing and inconsistent values.
- Convert delay durations into minutes.
- Clean train numbers.
- Extract route and station information.
- Process arrival times and day rollovers.

### 3. Feature Engineering

Calculate important features:

| Feature | Description |
|---|---|
| SEQ | Station sequence number |
| Remaining_Distance | Distance remaining to destination |
| Scheduled_Remaining_Minutes | Scheduled time remaining |
| Historical_Avg_Delay | Average historical delay |
| Historical_Max_Delay | Maximum historical delay |
| Historical_Min_Delay | Minimum historical delay |

### 4. Target Variable

The target variable is:

`Expected_ETA_Minutes`

It is calculated using:

**Expected ETA = Scheduled Remaining Time + Historical Average Delay**

### 5. Model Training

The dataset is divided into:
- 80% Training Data
- 20% Testing Data

StandardScaler is used for feature scaling.

The following regression algorithms are implemented:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor

### 6. Model Evaluation

Models are evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

### 7. ETA Prediction

A prediction function is implemented that accepts a train number and station name and returns the predicted remaining ETA in minutes.

---

## 📂 Project Structure

```text
indian-railway-eta-prediction/
│
├── eta_model.ipynb
│
├── Train_details_22122017.csv
├── indian_railway_delay_data_.csv
│
├── schedules.json
├── stations.json
├── trains.json
│
├── random_forest_eta_model.pkl
├── eta_feature_scaler.pkl
├── eta_feature_columns.pkl
├── eta_ml_dataset.pkl
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## ⚙️ Installation & Setup

### Prerequisites

- Python 3.9+
- Jupyter Notebook
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/Abhinav55849/indian-railway-eta-prediction.git
```

### Step 2: Navigate to the Project

```bash
cd indian-railway-eta-prediction
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Launch Jupyter Notebook

```bash
jupyter notebook
```

### Step 5: Run the Notebook

Open:

`eta_model.ipynb`

Execute the notebook cells sequentially to perform data preprocessing, feature engineering, model training, evaluation, and ETA prediction.

---

## 🔍 Example Prediction

The notebook includes a prediction function:

```python
predict_eta("12002", "BHOPAL")
```

Example output format:

```python
{
    "predictedEtaMinutes": 125.45
}
```

The predicted value represents the estimated remaining journey time in minutes.

Actual output depends on the trained model and input data.

---

## 📊 Model Evaluation

The
