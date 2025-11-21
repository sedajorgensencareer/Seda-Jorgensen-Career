# Machine Learning Project Checklist

---

## 1. Frame the Problem & Look at the Big Picture

### Define the Objective

1. Define the objective in business terms.  
2. How will the solution be used?  
3. What are the current solutions or workarounds (if any)?  

### Frame the Problem

4. How should you frame the problem?  
   - Supervised / Unsupervised  
   - Online / Offline  
   - Classification / Regression / Clustering  

### Performance

5. How should performance be measured?  
6. Is the performance metric aligned with the business objective?  
7. What is the minimum performance needed to achieve the business objective?  

### Assumptions, Context & Expertise

8. What are comparable problems? Can you reuse experience or tools?  
9. Is human expertise available? How would a human solve this manually?  
10. List the assumptions made so far.  
11. Verify assumptions whenever possible.  

---

## 2. Get the Data

**Goal:** Automate as much as possible.

1. List the data you need and the amount required.  
2. Document where to get the data.  
3. Check data size requirements (storage, memory).  
4. Check legal obligations & required authorizations.  
5. Get data-access approvals.  
6. Create a workspace with adequate storage.  
7. Retrieve the data.  
8. Convert the data into a usable format (without altering it).  
9. Remove or anonymize sensitive information.  
10. Check the type of data (time series, tabular, geo, etc.).  
11. Create a test set immediately and set it aside (no data snooping!).  

---

## 3. Explore the Data

Try to get insights from a domain expert when possible.

1. Create a working copy of the dataset (sample down if needed).  
2. Use a Jupyter notebook to document exploration.  
3. Study each attribute:  
   - Name  
   - Data type (categorical, numeric, text, structured, etc.)  
   - Missing values  
   - Noisiness / outliers  
   - Distribution (Gaussian, uniform, log, etc.)  
   - Potential usefulness  

### Visual Exploration

4. Visualize the data.  
5. Analyze correlations between features.  
6. Understand how a human would manually solve the task.  
7. Identify promising feature transformations.  
8. Identify additional data that may be useful.  
9. Document every insight discovered.  

---

## 4. Prepare the Data

Always work on copies; keep the original dataset intact.  
Write functions for all transformations to ensure reproducibility.

### Data Cleaning

1. Fix or remove outliers (optional).  
2. Handle missing data:  
   - Fill with zero, mean or median  
   - Drop rows or columns  
   - Use imputation strategies  

### Feature Selection (Optional)

3. Remove features that provide no useful information.  

### Feature Engineering

4. Discretize continuous features.  
5. Decompose complex attributes (dates, categories).  
6. Add transformed features (log, sqrt, power, interactions).  
7. Aggregate features into more useful composite features.  
8. Perform feature scaling (standardization or normalization).  

---

## 5. Short-List Promising Models

Automate whenever possible.  
Use smaller training subsets if the data is huge.

1. Train multiple quick baseline models across categories:  
   - Linear models  
   - Naive Bayes  
   - SVM  
   - Random Forest / Tree-based models  
   - Neural networks  
2. Measure and compare performance:  
   - Use N-fold cross-validation  
   - Track mean and standard deviation  
3. Analyze the most important features for each model.  
4. Analyze the types of errors the models make.  
5. What would a human use to avoid these errors?  
6. Perform quick feature selection & engineering iterations.  
7. Repeat steps once or twice.  
8. Short-list the top 3–5 models with diverse error patterns.  

---

## 6. Fine-Tune the System

Use as much data as possible.  
Automate everything.

1. Fine-tune hyperparameters using cross-validation.  
   - Treat data-preprocessing choices as hyperparameters.  
   - Prefer random search over grid search.  
   - Use Bayesian optimization for expensive models.  
2. Try ensemble methods (boosting, bagging, stacking).  
3. When confident in the final model, evaluate on the test set.  
4. Do not change the model after viewing test-set performance.  

---

## 7. Present Your Solution

1. Document everything you have done.  
2. Create a clear, structured presentation.  
3. Start with the big picture.  
4. Explain how your solution meets the business objective.  
5. Share key findings:  
   - What worked  
   - What didn’t work  
   - Assumptions made  
   - Limitations  
6. Communicate insights using simple statements and strong visuals  
   (e.g., “Median income is the strongest predictor of housing prices”).  

---

## 8. Launch!

Prepare the solution for production:

- Connect to production data  
- Write unit tests  
- Package your pipeline  

Add monitoring:

- Track model performance  
- Alert on drops or anomalies  
- Watch for slow model degradation (“model rot”)  
- Monitor input data quality  

Retrain regularly on fresh data and automate the process.  
