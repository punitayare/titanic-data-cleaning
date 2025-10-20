# titanic-data-cleaning

This repository contains the **cleaned and preprocessed Titanic dataset** from Kaggle. The focus of this project is on preparing the data for machine learning tasks such as survival prediction.

## Dataset

- Original dataset: [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic/data)
- Cleaned files included:
  - `titanic_cleaned.csv` – Preprocessed dataset ready for modeling
  - `Titanic-Dataset.csv` – Original dataset (optional)
  - `Data_cleaning.ipynb` – Jupyter notebook with all cleaning steps

## Cleaning Steps

1. **Removed irrelevant columns**:
   - `PassengerId`, `Name`, `Ticket`, `Cabin`  
2. **Handled missing values**:
   - Filled missing `Age` with median  
   - Filled missing `Embarked` with the most frequent value  
3. **Encoded categorical variables**:
   - `Sex` → 0 (female), 1 (male)  
   - `Embarked` → 0, 1, 2 (ports)  
4. **Scaled numeric features**:
   - `Age` and `Fare` scaled to [0,1]  

## Usage

```python
import pandas as pd

# Load cleaned dataset
df = pd.read_csv('titanic_cleaned.csv')

# Features
X = df[['Pclass','Sex','Age','SibSp','Parch','Fare','Embarked']]

# Target
y = df['Survived']
