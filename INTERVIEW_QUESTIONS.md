## Interview Questions – Data Preprocessing (Titanic Dataset)

1. **What are the different types of missing data?**  
   - **MCAR (Missing Completely at Random):** Missing values have no pattern. Example: Some `Cabin` entries are missing randomly.  
   - **MAR (Missing at Random):** Missing depends on other observed features. Example: `Age` missing more often for certain passenger classes.  
   - **MNAR (Missing Not at Random):** Missing depends on the value itself. Example: Expensive tickets might have missing `Fare` info.  

2. **How do you handle categorical variables?**  
   - Convert categories to numbers so models can process them.  
   - In Titanic:  
     - `Sex` → Label Encoding (`male=1, female=0`)  
     - `Embarked` → Ordinal codes or One-Hot Encoding (`C=0, Q=1, S=2`)  

3. **What is the difference between normalization and standardization?**  
   - **Normalization:** Scales values between 0 and 1 (used for `Age` and `Fare`).  
   - **Standardization:** Centers values around 0 with standard deviation 1. Useful for features with large value ranges.  

4. **How do you detect outliers?**  
   - Visualizations: Boxplots, histograms  
   - Statistical methods: Z-score, Interquartile Range (IQR)  
   - Example: `Fare` has some very high values compared to the rest.  

5. **Why is preprocessing important in ML?**  
   - Ensures clean, consistent data for the model.  
   - Example in Titanic:  
     - Filling missing `Age` values avoids errors  
     - Scaling `Fare` prevents domination of large values  
     - Encoding `Sex` and `Embarked` makes categorical data usable  

6. **What is one-hot encoding vs label encoding?**  
   - **Label Encoding:** Converts categories to numbers (`male=1, female=0`)  
   - **One-Hot Encoding:** Creates a binary column for each category (`Embarked_C, Embarked_Q, Embarked_S`)  

7. **How do you handle data imbalance?**  
   - Oversample minority class, undersample majority class, or use class weights.  
   - Example: Survival is slightly imbalanced, more passengers did not survive.  

8. **Can preprocessing affect model accuracy?**  
   - Yes.   
   - Proper preprocessing ensures features are meaningful and scaled correctly, which can significantly boost accuracy. Poor preprocessing can mislead the model or reduce performance.  
