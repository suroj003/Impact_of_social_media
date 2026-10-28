# 📊 Impact of Social Media on Student Life — ML Classification

A beginner-friendly Machine Learning mini-project that explores the relationship between social media usage and student life and builds a classification model to predict the overall impact as **Beneficial, Neutral, or Negative**.

This project is my first practical step into Machine Learning, where I explored data preprocessing, exploratory data analysis (EDA), feature encoding, model training, and evaluation using Python.

## 🎯 Project Objective

The objective is to build a Machine Learning classification model that predicts the overall impact of social media on student life based on features related to usage habits, sleep, mental well-being, and academic performance.

The project also aims to understand how to prepare real-world-style tabular data for Machine Learning and evaluate model performance beyond accuracy alone.

## 📁 Dataset Overview

**Dataset:** Impact of Social Media on Student Life

The dataset contains approximately **4,500 student records** and features related to social media usage, lifestyle, well-being, and academics.

### Main features

| Feature | Description |
|---|---|
| Age | Student's age |
| Gender | Student's gender |
| Academic_Level | Student's academic level |
| Primary_Platform | Most-used social media platform |
| Daily_Usage_Hours | Daily social media usage |
| Weekend_Extra_Hours | Additional usage during weekends |
| Late_Night_Usage | Whether the student uses social media late at night |
| Device_Type | Device used to access social media |
| Sleep_Duration_Hours | Duration of sleep |
| Sleep_Quality_Score | Score representing sleep quality |
| Social_Comparison_Frequency | Frequency of social comparison |
| Perceived_Stress_Score | Perceived stress score |
| Mental_Health_Index | Mental health-related index |
| Academic_Performance_GPA | Academic performance measure |
| Overall_Impact | Target variable for classification |

The original dataset also contains `Student_ID`, which is excluded from the model features because it is an identifier rather than a meaningful behavioral feature.

*Note: Verify the exact dataset size, feature definitions, and GPA scale against the original dataset before publishing.*

## 🛠️ Technologies Used

- **Python** — programming language
- **Pandas** — data manipulation and preprocessing
- **NumPy** — numerical operations
- **Matplotlib** — data visualization
- **Seaborn** — statistical visualization
- **Scikit-learn** — model training and evaluation
- **Jupyter Notebook** — development environment

## 🔄 Project Workflow

### 1. Data Loading

Loaded the dataset into a Pandas DataFrame and inspected the initial records, column names, and data types.

### 2. Exploratory Data Analysis (EDA)

Explored the dataset using:

- Histograms to understand numerical feature distributions.
- Boxplots to inspect potential outliers.
- Correlation heatmaps to examine linear relationships between numerical features.
- Category counts to understand categorical variables.

### 3. Data Preprocessing

Performed preprocessing steps to prepare the dataset for model training:

- Checked for duplicate records.
- Identified missing values.
- Handled missing numerical values.
- Converted categorical variables into numerical representations.
- Converted gender into a Boolean `IsMale` feature.
- Applied one-hot encoding to selected categorical variables.
- Excluded `Student_ID` from the model features.

### 4. Model Selection

Selected the **Random Forest Classifier** as the first classification algorithm to explore.

Random Forest combines predictions from multiple decision trees and can learn nonlinear patterns and interactions in tabular data.

The model was configured with:

- `n_estimators = 100`
- `random_state = 42`
- `class_weight = 'balanced'`

The balanced class weights were used to give additional importance to underrepresented classes during training.

### 5. Model Training

The dataset was divided into training and testing sets using an 80:20 split, with stratification to preserve the approximate class proportions.

The classifier was trained on the training set and evaluated on the unseen test set.

### 6. Model Evaluation

The evaluation includes:

- **Accuracy:** Overall proportion of correct predictions.
- **Precision:** How many predictions for a class were correct.
- **Recall:** How many actual examples of a class were identified.
- **Macro F1-score:** The average F1-score across classes, treating each class equally.
- **Balanced accuracy:** Average recall across classes.
- **Confusion matrix:** Shows correct predictions and class-wise misclassifications.
- **Log loss:** Evaluates the quality of predicted class probabilities.

## 📈 Initial Results

The initial Random Forest model achieved approximately **97.44% test accuracy**.

This is an encouraging initial result for a first ML practice project. However, accuracy alone does not establish that the model performs equally well across all classes.

The target classes are imbalanced, so the model's precision, recall, macro F1-score, and confusion matrix should also be considered.

The reported accuracy should be treated as an initial result until the preprocessing pipeline, data leakage risks, and performance on unseen data have been thoroughly checked.

## 📊 Visualizations

The project includes visualizations such as:

- Dataset preview
- Feature distribution plots
- Correlation heatmap
- Confusion matrix
- Feature importance chart

These visualizations help understand the dataset, inspect relationships between features, and examine the model's predictions.

## ⚠️ Limitations

- The project is an initial learning exercise, not a production-ready prediction system.
- Class imbalance may affect performance on the less frequent classes.
- Correlation and feature importance do not establish causation.
- The quality and meaning of the target labels depend on how the dataset was collected and labelled.
- The model's generalization ability has not yet been established on an independent external dataset.
- A high test accuracy can be misleading if information related to the target leaks into the input features.

The predictions should not be interpreted as clinical assessments of students' mental health or as evidence that social media causes a particular outcome.

## 🚀 Future Improvements

### 1. Compare Multiple Classification Algorithms

Experiment with:

- Logistic Regression
- Decision Tree Classifier
- Extra Trees Classifier
- Gradient Boosting
- Support Vector Machine

Compare the models using the same train-test split and appropriate classification metrics.

### 2. Improve Class Imbalance Handling

Investigate different class-weight settings and other imbalance-handling techniques. Focus on improving recall and F1-score for the `Negative` and `Neutral` classes without unnecessarily harming performance on other classes.

### 3. Hyperparameter Tuning

Use cross-validation and `GridSearchCV` or `RandomizedSearchCV` to tune parameters such as tree depth, number of trees, and minimum samples required for a split.

### 4. Build a Reliable ML Pipeline

Use Scikit-learn pipelines to handle imputation, encoding, and model training consistently. Fit preprocessing steps on training data only to avoid data leakage.

### 5. Investigate Feature Importance

Study which features contribute most to the model's predictions. Consider permutation importance or SHAP for a more detailed explanation of model behavior.

### 6. Add Cross-Validation

Use stratified cross-validation to determine whether the model's performance remains consistent across different data splits.

### 7. Deploy a Simple Web Application

Build a small interactive application using Streamlit or Flask that accepts feature values and displays the predicted class and model confidence.

Clearly communicate that the output is an experimental model prediction, not a diagnosis or causal conclusion.

### 8. Improve Documentation and Reproducibility

Document the dataset source, feature definitions, preprocessing decisions, model configuration, evaluation results, and software dependencies. Add a `requirements.txt` file and reproducible instructions for running the notebook.

## 📚 What I Learned

This project helped me understand that Machine Learning involves much more than simply training a model.

Key takeaways:

- Understanding and cleaning data is an essential first step.
- Categorical data must be represented appropriately for the selected algorithm.
- A model should be evaluated on unseen data.
- Accuracy is not enough when the target classes are imbalanced.
- Visualizations help identify patterns and potential data issues.
- Model results must be interpreted carefully rather than accepted at face value.

## 🌱 Project Status

**Status:** Initial implementation completed; further evaluation and improvement are planned.

This is my first step towards learning Machine Learning through hands-on experimentation. I plan to improve the model, compare algorithms, and explore model deployment as I continue learning.

## 🤝 Contributions

Suggestions, feedback, and ideas for improvement are welcome.

## 📜 Disclaimer

This project is intended for educational purposes. Its predictions should not be used to make medical, psychological, or academic decisions about individuals.

---

**Built as part of my Machine Learning learning journey.** 🚀
