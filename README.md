
🎯 Bank Marketing Prediction: Decision Tree Classifier
Project Overview
This project focuses on building a classification model to predict whether a bank client will subscribe to a term deposit (the target variable, 'y'). Using the Decision Tree algorithm, we analyze client attributes and past campaign results to help the bank optimize its marketing strategy, ensuring resources are targeted at the most likely customers.

⚙️ Data Preparation and Feature Engineering
The initial data required cleaning and transformation to be usable by the machine learning model.

1. Data Handling
Data Source: The bank-full.csv dataset was loaded, correctly specifying the semi-colon (;) separator.

Missing Values: The dataset was checked and determined to have no missing values (df.isnull().sum() showed all zeros).

2. Feature Encoding
The dataset contains numerous categorical features (e.g., job, marital, education).

One-Hot Encoding: The categorical columns were transformed into numerical features using pd.get_dummies(). This is essential because the Decision Tree model only accepts numerical input.

Target Variable: The target column, y, was converted into a binary format (y_yes: 1, y_no: 0).

🌳 Model & Methodology
1. Model Selection: Decision Tree Classifier
A Decision Tree was chosen for its interpretability. Unlike "black-box" models, a Decision Tree allows us to visualize the exact rules and thresholds the model uses to make a prediction, which is highly valuable for providing actionable insights to a marketing team.

2. Model Tuning for Imbalance
The dataset is highly imbalanced (the number of clients subscribing is much smaller than those who don't).

class_weight='balanced': This critical hyperparameter was set to automatically adjust weights inversely proportional to class frequencies. This forces the model to pay equal attention to the rare 'Yes' class (subscribers) as it does to the common 'No' class (non-subscribers), preventing it from simply predicting 'No' all the time.

max_depth=5: Limiting the tree's depth prevents overfitting (where the model learns the training data too well) and keeps the tree simple enough to be easily plotted and interpreted.

3. Training and Evaluation
The dataset was split with a standard 70% for training and 30% for testing (test_size=0.3).

✅ Results and Interpretation
Overall Performance
The model achieved an Accuracy of 80.49% on the test set. While overall accuracy is important, the Classification Report provides deeper insights into how well the model identifies the critical 'Yes' class.

