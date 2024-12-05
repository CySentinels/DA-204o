# Phishing Analysis
Project repository for DA 204o Data Science in Practice (Aug semester 2024) @ IISc BLR

## Project Purpose
The purpose of this project is to develop a reliable machine learning-based system for detecting phishing URLs by analyzing their structure, content, and behavior.

## Dataset
**Source**: [PhiUSIIL Phishing URL (Website)](https://archive.ics.uci.edu/dataset/967/phiusiil+phishing+url+dataset)

**Summary**: PhiUSIIL Phishing URL Dataset is a substantial dataset comprising 134,850 legitimate and 100,945 phishing URLs. Most of the URLs we analyzed, while constructing the dataset, are the latest URLs. Features are extracted from the source code of the webpage and URL. Features such as CharContinuationRate, URLTitleMatchScore, URLCharProb, and TLDLegitimateProb are derived from existing features.

**Additional Info**:
1. Column "FILENAME" can be ignored.
2. Label 1 corresponds to a legitimate URL, label 0 to a phishing URL

## Project Steps
### 1. Exploratory Data Analysis (EDA)

**Dataset Overview**
1. Basic exploration: info(), describe(), shape, and isnull().
2. Dataset contains 235,795 rows, no missing or duplicate values.
   
**Key Groupings of Features**
1. URL Characteristics: Length, special characters, obfuscation metrics.
2. Legitimacy Indicators: HTTPS usage, TLD legitimacy, subdomains.
3. Web Page Content: Title, favicon, and descriptions.
4. Web Page Features: Redirects, popups, and social network links.

**Hypotheses and Findings**
1. URL Length: Longer URLs are more likely to be phishing.
2. TLDs: Suspicious TLDs are common in phishing URLs.
3. HTTPS: Both phishing and legitimate URLs use HTTPS, reducing its reliability as a single indicator.
4. Obfuscation: Phishing URLs frequently use obfuscation techniques.
   
For detailed visualizations and analysis, refer to 01-EDA.ipynb.

### 2. Model Training and Evaluation

**Models Trained:** Decision Tree, Random Forest, SVM, Naive Bayes.

**Steps:**

  **1. Data Preparation:** Categorical encoding, feature-target definition, train-test split.

  **2. Model Training:** Built initial models.

  **3. Hyperparameter Tuning:** Used GridSearchCV with cross-validation to optimize parameters.

  **4. Evaluation:** Assessed performance using accuracy, precision, recall, F1-score, ROC-AUC, and PR curves.

**Best Model:**
 Random Forest achieved the highest performance.
 
 Saved as rf_model_phiusiil_grid_search.pkl.
 
**Feature Importance:** Visualized the Top 10 Most Important Features.

Refer to the below files for details analysis and documentation:

**Decision Tree:** 02-a-ModelTraining-DecisionTree.ipynb

**SVM:** 02-b-ModelTraining-SVM.ipynb

**Naive Bayes:** 02-c-ModelTraining-NaiveBayes.ipynb

**Random Forest:** 02-d-ModelTraining-RandomForest.ipynb

**ComparisonAndBestModelSelection:** 02-e-ModelTraining-ComparisonAndBestModelSelection.ipynb

**requirements.txt** contains list of required Python libraries

### 3. Model Deployment & Demo

![image](https://github.com/user-attachments/assets/035ad6af-140f-4f61-bade-dd89b389df11)               ![image](https://github.com/user-attachments/assets/419a98f6-4a69-465c-9751-bab77d106911)

**Future Work**

**(1) Real-Time Phishing Detection:** Develop and deploy real-time systems, such as browser extensions or exchange platforms, to detect and block phishing URLs as they appear, providing immediate protection for users.
 
**(2) Model Retraining and Updates:** Continuously update and retrain the model with new phishing data to adapt to evolving tactics and improve detection accuracy.

**(3) Advanced Feature Integration:** Incorporate additional features such as user interaction data and behavioural analysis to improve model robustness and detect more sophisticated phishing attacks.



## Team Members
1. Deepansh Sood
2. Shambo Samanta
3. Sudipta Ghosh
4. Sourajit Bhar
