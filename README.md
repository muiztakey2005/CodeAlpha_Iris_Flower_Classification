# Iris Flower Classification

## CodeAlpha Data Science Internship — Task 1

### Objective

Build a machine learning classification model to predict the species of an Iris flower using its sepal and petal measurements.

---

## 📌 Project Overview

This project focuses on classifying Iris flowers into their respective species using machine learning classification algorithms.

The project follows a complete data science workflow:

**Dataset → Data Understanding → Data Cleaning → Exploratory Data Analysis → Preprocessing → Feature Engineering → Model Building → Evaluation → Interpretation → Final Model**

Three machine learning algorithms were implemented and evaluated:

* Logistic Regression
* K-Nearest Neighbors (KNN)
* Decision Tree

The models were evaluated using a held-out test set and 5-fold cross-validation.

---

## 📂 Dataset

The project uses the **Iris dataset**, which contains measurements of Iris flowers.

### Features

| Feature         | Description                        |
| --------------- | ---------------------------------- |
| `SepalLengthCm` | Length of the sepal in centimeters |
| `SepalWidthCm`  | Width of the sepal in centimeters  |
| `PetalLengthCm` | Length of the petal in centimeters |
| `PetalWidthCm`  | Width of the petal in centimeters  |

### Target

The target variable is:

```text
Species
```

The dataset contains three species:

* Iris-setosa
* Iris-versicolor
* Iris-virginica

The dataset contains **150 samples**, with **50 samples from each species**.

---

## 🔄 Project Workflow

### 1. Data Understanding

The dataset was loaded and examined to understand:

* Number of rows and columns
* Data types
* Feature distributions
* Target classes
* Class distribution

### 2. Data Cleaning

The dataset was checked for:

* Missing values
* Duplicate rows
* Duplicate IDs
* Invalid measurement values

No missing values or duplicate rows were found.

### 3. Exploratory Data Analysis

The following visualizations were created:

* Species distribution plot
* Feature histograms with KDE
* Boxplots by species
* Correlation heatmap
* Pairplot

EDA showed that the petal measurements provide strong separation between the Iris species.

### 4. Feature and Target Preparation

The four measurement features were used as input variables:

```text
SepalLengthCm
SepalWidthCm
PetalLengthCm
PetalWidthCm
```

The target variable was encoded using `LabelEncoder`.

### 5. Train-Test Split

The dataset was divided into:

* **80% training data**
* **20% testing data**

A stratified split was used to maintain class distribution.

### 6. Feature Scaling

`StandardScaler` was used for models that benefit from feature scaling.

The scaler was fitted only on the training data and then used to transform the test data.

### 7. Model Building

Three classification models were trained:

#### Logistic Regression

A linear classification model used as one of the baseline models.

#### K-Nearest Neighbors

KNN was implemented with:

```text
n_neighbors = 5
```

#### Decision Tree

A Decision Tree classifier was trained using the original, unscaled feature values.

---

## 📊 Model Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* 5-Fold Cross-Validation

### Test Set Results

| Model               | Test Accuracy | Precision | Recall | F1-Score |
| ------------------- | ------------: | --------: | -----: | -------: |
| Logistic Regression |        93.33% |     93.3% |  93.3% |    93.3% |
| KNN                 |        93.33% |     94.4% |  93.3% |    93.3% |
| Decision Tree       |        93.33% |     93.3% |  93.3% |    93.3% |

All three models correctly classified **28 out of 30 test samples**.

---

## 🔬 Cross-Validation Results

5-fold cross-validation was performed on the training dataset.

| Model               | Mean CV Accuracy |
| ------------------- | ---------------: |
| Logistic Regression |           95.83% |
| KNN                 |       **96.67%** |
| Decision Tree       |           94.17% |

KNN obtained the highest mean cross-validation accuracy among the three evaluated models.

---

## 🌳 Feature Importance

Feature importance was analyzed using the Decision Tree model.

The approximate importance ranking was:

1. `PetalLengthCm`
2. `PetalWidthCm`
3. `SepalWidthCm`
4. `SepalLengthCm`

The analysis indicates that petal measurements contributed most strongly to the Decision Tree's classification decisions.

This is also consistent with the exploratory data analysis, where petal measurements showed strong separation between the species.

---

## 🧪 New Sample Prediction

After model evaluation, a final KNN model was trained using the complete dataset.

The final model was tested using a new Iris flower sample:

```text
Sepal Length = 5.1 cm
Sepal Width  = 3.5 cm
Petal Length = 1.4 cm
Petal Width  = 0.2 cm
```

The model predicted:

```text
Iris-setosa
```

---

## 💾 Saved Model Files

The final trained model and preprocessing components were saved using `joblib`.

```text
models/
├── iris_knn_model.pkl
├── iris_scaler.pkl
└── iris_label_encoder.pkl
```

### Files Description

| File                     | Purpose                          |
| ------------------------ | -------------------------------- |
| `iris_knn_model.pkl`     | Trained KNN classification model |
| `iris_scaler.pkl`        | Feature scaling object           |
| `iris_label_encoder.pkl` | Target label encoder             |

These files allow the trained model to be reused without retraining from scratch.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib
* Google Colab
* Jupyter Notebook

---

## 📁 Project Structure

```text
CodeAlpha_Iris_Flower_Classification/
│
├── README.md
├── requirements.txt
│
├── data/
│   └── Iris.csv
│
├── notebook/
│   └── Iris_Flower_Classification.ipynb
│
└── models/
    ├── iris_knn_model.pkl
    ├── iris_scaler.pkl
    └── iris_label_encoder.pkl
```

## 📈 Key Findings

* The dataset contains **150 Iris flower samples** belonging to three species.
* Each species contains **50 samples**, resulting in a balanced dataset.
* Petal length and petal width provide strong separation between the three species.
* Logistic Regression, KNN, and Decision Tree each achieved **93.33% test accuracy**.
* KNN achieved the highest mean 5-fold cross-validation accuracy at **96.67%**.
* Decision Tree feature importance identified `PetalLengthCm` and `PetalWidthCm` as the most influential features.
* The final KNN model successfully predicted a new sample as **Iris-setosa**.

---

## 🎯 Conclusion

This project demonstrates a complete machine learning classification workflow using the Iris dataset.

The workflow covered data understanding, cleaning, exploratory data analysis, preprocessing, model training, evaluation, cross-validation, feature importance analysis, and final model deployment preparation.

Three classification algorithms were evaluated using both a held-out test set and 5-fold cross-validation. The final KNN model was trained on the complete dataset and successfully used to predict the species of a new Iris flower sample.

---

## 🎓 Internship Task

This project was completed as part of:

**CodeAlpha Data Science Internship**

### Task 1 — Iris Flower Classification

---

## 👤 Author

**Muiz Takey**

Computer Science & Engineering — Artificial Intelligence & Machine Learning

---

## ⭐ Acknowledgement

This project was developed as part of the CodeAlpha Data Science Internship to apply practical machine learning and data science concepts to a real classification problem.
