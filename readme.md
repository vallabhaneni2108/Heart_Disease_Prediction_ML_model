# ❤️ Heart Disease Prediction

A machine learning project that predicts the likelihood of heart disease based on various clinical and physiological attributes. The project includes exploratory data analysis (EDA), data preprocessing, machine learning model training and evaluation, and a Streamlit web application for making predictions.

> ⚠️ **Disclaimer:** This project is created for educational and demonstration purposes only. It is not a medical diagnostic tool and should not be used as a substitute for professional medical advice.

## 📌 Project Overview

This project uses a heart disease dataset containing **918 patient records** and **12 features**. The target variable is `HeartDisease`.

* `0` → No heart disease
* `1` → Heart disease

After preprocessing and evaluating multiple classification algorithms, a **K-Nearest Neighbors (KNN)** model is used in the Streamlit application for prediction.

The Streamlit application allows users to enter patient information and receive a predicted heart disease risk. The application loads the trained KNN model, scaler, and expected feature columns to ensure that user input is processed consistently with the training data.

## 📊 Dataset Features

| Feature          | Description                      |
| ---------------- | -------------------------------- |
| `Age`            | Age of the patient               |
| `Sex`            | Sex of the patient               |
| `ChestPainType`  | Type of chest pain               |
| `RestingBP`      | Resting blood pressure           |
| `Cholesterol`    | Cholesterol level                |
| `FastingBS`      | Fasting blood sugar > 120 mg/dL  |
| `RestingECG`     | Resting electrocardiogram result |
| `MaxHR`          | Maximum heart rate achieved      |
| `ExerciseAngina` | Exercise-induced angina          |
| `Oldpeak`        | ST depression                    |
| `ST_Slope`       | Slope of the ST segment          |
| `HeartDisease`   | Target variable                  |

## 🔎 Exploratory Data Analysis

The project performs Exploratory Data Analysis using **Pandas, Matplotlib, and Seaborn**.

The analysis includes:

* Checking dataset shape
* Understanding data types
* Descriptive statistics
* Checking missing values
* Checking duplicate records
* Analyzing the target variable
* Visualizing the data
* Understanding relationships between features and the target

The dataset contains **918 records**, with:

* **508** records where `HeartDisease = 1`
* **410** records where `HeartDisease = 0`

No duplicate records or missing values were found during the initial data analysis.

## ⚙️ Machine Learning Workflow

The project follows the following machine learning workflow:

```text
Dataset
   ↓
Exploratory Data Analysis
   ↓
Data Preprocessing
   ↓
Categorical Feature Encoding
   ↓
Train-Test Split
   ↓
Feature Scaling
   ↓
Model Training
   ↓
Model Evaluation
   ↓
KNN Model Selection
   ↓
Model Serialization
   ↓
Streamlit Application
```

### Data Preprocessing

The dataset contains both numerical and categorical features.

Categorical features are converted into numerical features using encoding, while numerical features are scaled before training the KNN model.

The trained preprocessing components are saved using Joblib so that the same preprocessing can be applied to new user input.

## 🤖 Machine Learning Models

The project evaluates multiple classification algorithms:

* Logistic Regression
* K-Nearest Neighbors (KNN)
* Naive Bayes
* Decision Tree
* Support Vector Machine (SVM)

The models are evaluated using classification metrics such as:

* Accuracy
* F1 Score
* Classification performance

The **KNN classifier** is used in the final Streamlit application.

## 🧠 K-Nearest Neighbors

KNN is a supervised machine learning algorithm used for classification.

For a new data point, KNN identifies the nearest training data points and predicts the class based on the majority class among its neighbors.

Since KNN is distance-based, feature scaling is important. Therefore, the input data is transformed using the saved scaler before being passed to the trained model.

## 🖥️ Streamlit Application

The project includes an interactive Streamlit web application.

Users can provide the following information:

* Age
* Sex
* Chest Pain Type
* Resting Blood Pressure
* Cholesterol
* Fasting Blood Sugar
* Resting ECG
* Maximum Heart Rate
* Exercise-Induced Angina
* Oldpeak
* ST Slope

After clicking the **Predict** button, the application:

1. Collects the user's input.
2. Converts the input into a DataFrame.
3. Creates the required encoded features.
4. Adds missing expected columns with `0`.
5. Reorders the columns to match the training data.
6. Scales the input using the saved scaler.
7. Passes the processed input to the KNN model.
8. Displays the prediction.

The application displays either:

```text
⚠️ High Risk of Heart Disease
```

or

```text
✅ Low Risk of Heart Disease
```

## 🛠️ Technologies Used

* **Python**
* **NumPy**
* **Pandas**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **Joblib**
* **Streamlit**
* **Jupyter Notebook**

## 📁 Project Structure

```text
heart-disease-prediction/
│
├── app.py
├── heart.ipynb
├── heart.csv
│
├── KNN_heart_model.pkl
├── heart_scaler.pkl
├── heart_columns.pkl
│
├── requirements.txt
├── .gitignore
└── README.md
```

### File Description

| File                  | Description                                       |
| --------------------- | ------------------------------------------------- |
| `app.py`              | Streamlit web application                         |
| `heart.ipynb`         | EDA, preprocessing, model training and evaluation |
| `heart.csv`           | Heart disease dataset                             |
| `KNN_heart_model.pkl` | Saved KNN model                                   |
| `heart_scaler.pkl`    | Saved feature scaler                              |
| `heart_columns.pkl`   | Saved feature-column order                        |
| `requirements.txt`    | Python dependencies                               |
| `.gitignore`          | Files and folders excluded from Git               |
| `README.md`           | Project documentation                             |

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone <your-repository-url>
```

### 2. Navigate to the project directory

```bash
cd heart-disease-prediction
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate the virtual environment

**Windows PowerShell:**

```bash
venv\Scripts\Activate.ps1
```

**Windows Command Prompt:**

```bash
venv\Scripts\activate
```

### 5. Install the dependencies

```bash
pip install -r requirements.txt
```

### 6. Run the Streamlit application

```bash
streamlit run app.py
```

The application will open in your default web browser.

## 📈 Prediction Flow

```text
User Input
    ↓
DataFrame Creation
    ↓
Categorical Encoding
    ↓
Feature Alignment
    ↓
Feature Scaling
    ↓
KNN Model
    ↓
Prediction
    ↓
Risk Result
```

## 💡 Key Learning Outcomes

Through this project, I gained practical experience in:

* Exploratory Data Analysis
* Data preprocessing
* Handling categorical variables
* Feature encoding
* Feature scaling
* Train-test splitting
* Classification algorithms
* Model evaluation
* KNN classification
* Saving and loading ML models using Joblib
* Building an interactive ML application using Streamlit

## 🔮 Future Improvements

Some possible improvements for this project are:

* Hyperparameter tuning for KNN
* Cross-validation
* More detailed model comparison
* Adding confusion matrix visualization
* Adding precision, recall and ROC-AUC metrics
* Creating a complete Scikit-learn preprocessing pipeline
* Improving the Streamlit user interface
* Adding better input validation
* Deploying the application to a cloud platform

## 👨‍💻 Author

**Vallabhaneni Chenchaiah**

---

⭐ If you found this project useful, consider giving the repository a star!
