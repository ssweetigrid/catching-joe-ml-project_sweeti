# Catching Joe - User Session Identification using Machine Learning

## Project Overview

This project focuses on identifying whether a browser session belongs to a specific user called **"Joe"** based on browsing behavior.

The goal is to analyze user session data and build a machine learning model that can distinguish Joe's browsing sessions from other users.

This project demonstrates the **complete Data Science workflow**, including:

- Problem understanding
- Data exploration
- Feature engineering
- Model training
- Model evaluation
- Prediction on new sessions

---

# Problem Statement

The **Catching Joe problem** aims to detect whether a browser session belongs to a specific user (Joe) using browsing session data.

Each session contains information such as:

- Browser
- Operating System
- Location
- Websites visited
- Time spent on each site
- Session time
- Date

Using this information, the task is to **build a model that predicts whether a session belongs to Joe or not.**

---

# Dataset Description

The dataset consists of browser session logs.

### Training Dataset

File: `dataset.json`

Contains:

- Multiple user sessions
- User IDs
- Browsing behavior
- Used for training the machine learning model

Important fields:

- browser
- os
- locale
- gender
- location
- sites
- time
- date
- user_id

Target variable:
user_id == 0 → Joe
user_id != 0 → Not Joe


---

### Test Dataset

File: `verify.json`

Contains session data without user IDs.

Used to:

- Apply feature engineering
- Generate predictions for Joe sessions.

---


---

# Notebooks Description

### final.ipynb

Main notebook containing the **complete machine learning pipeline**.

Steps included:

1. Data loading  
2. Data exploration  
3. Feature engineering  
4. Model training  
5. Model evaluation  
6. Prediction generation  
7. Visualization and analysis  

This notebook is the **main implementation of the project**.

---

### dummy.ipynb

This notebook was used for experimentation.

It contains:

- testing ideas
- verifying feature engineering
- trying different approaches

Examples of experiments:

- feature creation testing
- threshold tuning
- visualization experiments

---

# Feature Engineering

Several features were extracted from the raw session data.

### Time Based Features

- hour
- weekday

These help capture Joe's browsing patterns.

---

### Session Behavior Features

- num_sites
- total_time
- avg_time_per_site

These features describe session behavior.

---

### Website Visit Features

Top frequently visited websites were extracted.

Example features:

- visit_youtube.com
- visit_slack.com
- visit_toptal.com
- visit_lenta.ru
- visit_vk.com

These features help capture browsing preferences.

---

### Categorical Features

One-hot encoding was applied to:

- browser
- operating system
- locale
- gender
- location

---

# Machine Learning Model

The model used in this project:

Logistic Regression

Why Logistic Regression?

- Suitable for binary classification
- Produces probabilities
- Fast and interpretable
- Works well with engineered features

---

# Model Evaluation

The model was evaluated using:

- ROC-AUC Score
- Accuracy
- Precision
- Recall
- F1-score

Example results:

ROC-AUC: ~0.989  
Accuracy: ~0.97  
Recall: ~0.92  
Precision: ~0.11  

Due to extreme class imbalance, **ROC-AUC and Recall are more meaningful metrics than accuracy.**

---

# Visualizations Included

The project includes several visualizations:

- ROC Curve
- Precision-Recall Curve
- Threshold tuning analysis
- Feature importance
- Session behavior scatter plots
- Prediction probability distribution

These visualizations help understand how the model distinguishes Joe sessions.

---


The model outputs:

Joe Probability

Then applies a threshold to classify the session.

---

# Technologies Used

Python

Libraries:

- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- jupyter

---


---

# Key Learning Outcomes

This project demonstrates:

- Data preprocessing
- Feature engineering
- Handling nested JSON data
- Machine learning modeling
- Model evaluation
- Threshold tuning
- Building a full ML pipeline

---

# Future Improvements

Possible improvements include:

- testing advanced models (Random Forest, XGBoost)
- hyperparameter tuning
- automated feature pipelines
- model deployment
- real-time session prediction

---

# Author

Sweeti Swami

Machine Learning Project – Catching Joe

