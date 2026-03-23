# Responsible_Machine_Learning_Individual_Assignment_1 - COMPAS Analysis

## The Purpose of the Analysis

The purpose of this individual assignment (and analysis) is to evaluate the fairness and predictve performance of the COMPAS risk assessment. Using real-world data, the analysis examines whether COMPAS scores have differences in the recidivism outcomes across demogprahic groups, specifically, when looking at African-American defendants vs. White defendants, in addition to examining Male vs. Female defendants. 

This analysis used statistical tools such as logistic regression, Cox proportional hazards models, and Kaplan-Meier survival analysis to deeply investigate how well the model predicts recidivism, and if those predictions are consistent across groups. Here are how these tools were used more specifically: 

- Logistic Regression was used to model the likelihood of a defendant receiving a high COMPAS risk score, while controlling for factors such as age, prior offenses, gender, and race. This helped identify whether certain groups were more likely to be assigned higher risk scores, holding other variables constant.

- Cox Proportional Hazards Models were used to examine the relationship between risk scores and the timing of recidivism. This allowed for an assessment of how well the COMPAS scores align with actual outcomes over time, and whether the model’s predictive performance differs across demographic groups.

- Kaplan-Meier Survival Analysis was used to estimate the probability of not recidivating over time for different risk score categories. By comparing survival curves across groups, this method provided a visual and statistical way to evaluate how well the score separates low, medium, and high-risk individuals.

Overall, the goal is to assess accuracy, and identify potential disparities in how risk is assigned. Implications of this give better understanding of using such tools in decision-making systems, and the risk is brings when training on biased data. 

---

## Python Libraries Used

The following Python libraries were used in this analysis (and, the purpose and use of these tools are listed next to it:

- `pandas` – used for data cleaning, filtering, and structuring the dataset. This involved removing invalid observations, making new variables such as categorical factors for race and score levels, and preparing the data.
- `numpy` – used for numerical operations and transformations (handling arrays, converting data types) and performing calculations needed for probability and the interpretation of modeling.
- `matplotlib` – used to visualize results of the Kaplan-Meier survival curves, acting as a visual ad for identifying different recidivism patterns across different risk score groups and demographics.
- `scikit-learn` – used to implement logistic regression models that estimate the likelihood of being assigned a high COMPAS risk score. This allowed for analysis of how different variables, including race, are associated with predicted risk. 
- `lifelines` – used for survival analysis, including Cox proportional hazards models and Kaplan-Meier estimation. 
---

## Instructions for Reproducing the Results

To reproduce the results of this analysis, follow the steps below:

1. **Install required packages**  
   Run the following command in a notebook cell or terminal:

   ```python
   !pip install pandas numpy matplotlib scikit-learn lifelines
2. **Download .ipynb file and run all cells**
3. **Note: URL's in the notebook are using files from another GitHub repository: https://github.com/propublica/compas-analysis/tree/master
