# Responsible_Machine_Learning_Individual_Assignment_1 - COMPAS Analysis

## The Purpose of the Analysis

The purpose of this individual assignment (and analysis) is to evaluate the fairness and predictive performance of the COMPAS risk assessment. Using real-world data, the analysis examines whether COMPAS scores have differences in the recidivism outcomes across demographic groups, specifically, when looking at African-American defendants vs. White defendants. The notebook continues to assess the state of the model using explainable tools to test transparency.

This analysis used statistical tools such as logistic regression, Cox proportional hazards models, and Kaplan-Meier survival analysis to deeply investigate how well the model predicts recidivism, and if those predictions are consistent across groups. Additionally, SHAP, LIME, and DiCE were used to investigate how risk scores are assigned and whether they result in racially disparate outcomes. Here is how these tools were used more specifically: 

- Logistic Regression was used to model the likelihood of a defendant receiving a high COMPAS risk score, while controlling for factors such as age, prior offenses, gender, and race. This helped identify whether certain groups were more likely to be assigned higher risk scores, holding other variables constant.

- Cox Proportional Hazards Models were used to examine the relationship between risk scores and the timing of recidivism. This allowed for an assessment of how well the COMPAS scores align with actual outcomes over time, and whether the model’s predictive performance differs across demographic groups.

- Kaplan-Meier Survival Analysis was used to estimate the probability of not recidivating over time for different risk score categories. By comparing survival curves across groups, this method provided a visual and statistical way to evaluate how well the score separates low, medium, and high-risk individuals.

- LIME (Local Interpretable Model-agnostic Explanations) was used to examine individual predictions, revealing that being African-American can directly increase a defendant's predicted risk score

- SHAP (Shapley Additive Explanations) was utilized to provide a global view of feature importance in the risk score predictions, both globally and looking at individuals of high risk and low risk for both Black and White defendants.

- DiCE (Diverse Counterfactual Explanations) identified how the highest-risk and lowest-risk White and Black defendants could change their features in the model to be perceived the opposite way and receive a different predicted outcome. So, it goes beyond telling us what the output is, but how it could have gotten a different output.

Overall, the goal is to assess accuracy, and identify potential disparities in how risk is assigned. Implications of this give better understanding of using such tools in decision-making systems, and the risk is brings when training on biased data. 

---

## Python Libraries Used

The following Python libraries were used in this analysis (and, the purpose and use of these tools are listed next to it:

- `pandas` – used for data cleaning, filtering, and structuring the dataset. This involved removing invalid observations, making new variables such as categorical factors for race and score levels, and preparing the data.
- `numpy` – used for numerical operations and transformations (handling arrays, converting data types) and performing calculations needed for probability and the interpretation of modeling.
- `matplotlib` – used to visualize results of the Kaplan-Meier survival curves, acting as a visual ad for identifying different recidivism patterns across different risk score groups and demographics.
- `scikit-learn` – used to implement logistic regression models that estimate the likelihood of being assigned a high COMPAS risk score. This allowed for analysis of how different variables, including race, are associated with predicted risk. 
- `lifelines` – used for survival analysis, including Cox proportional hazards models and Kaplan-Meier estimation.
- `lime` was used for local interpretability to explain individual defendent risk scores
- `shap` was used for both local and global feature importance analysis
- `dice-ml` was used to generate counterfactual explanations for model predictions
---

## Instructions for Reproducing the Results

To reproduce the results of this analysis, follow the steps below:

1. **Install required packages**  
   Run the following command in a notebook cell or terminal:

   ```python
   !pip install pandas numpy matplotlib scikit-learn lifelines lime shap dice-ml
2. **Download .ipynb file and run all cells**
3. **Review the Audit Findings by referring to the Responsible Machine Learning Governance memo**
4. **Note: No manual download of files is required. URLs retrieve data in the notebook, getting CSV files from another GitHub repository: https://github.com/propublica/compas-analysis/tree/master**

A Statement on AI Usage: Google Gemini, embedded in Google Colab (the tool used to create the notebook), was used to identify a complex error message and guide thinking on how to solve it. Additionally, external internet sources, such as OpenStack, were used to identify Python packages that most closely reflect the R packages used in the notebook that needed to be translated into Python. All code was written and reviewed by me, ensuring that important statistical analyses from the R notebook were present in the Python version, and extensive conclusions and interpretations were made from the outputs given by the code. 
