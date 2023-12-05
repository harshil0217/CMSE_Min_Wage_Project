# CMSE_Min_Wage_Project
Project Analyzing Minimum Wage Alongisde other Factors that Contribute to Income Inequality

Harshil Chidura, Viraj Shah, Shayna McConville, Tanmay Shekhar, Abigail Werthmann

# Abstract
## Summary of the questions addressed :- Factors affecting wealth inequality

In our study, we delved into the factors influencing wealth inequality, focusing on the Gini coefficient as a measure of income distribution. Central to our investigation was the role of minimum wage in shaping economic disparities. We examined the complex interplay between minimum wage adjustments and the Gini coefficient, seeking insights into how wage policy impacts wealth distribution. This analysis is pivotal amidst debates over wage regulations and their broader economic implications. Our aim was to deepen the understanding of the economic determinants of wealth inequality, highlighting how policy decisions like minimum wage alterations can influence the economic divide in society.

## Basic Methods applied:

### OLS Regression:

Relevance and Usefulness:
- Direct Relationship Analysis: Ordinary Least Squares (OLS) regression is ideal for examining direct, linear relationships between variables. In your case, it helps to identify how minimum wage and other economic factors linearly relate to the Gini coefficient.
- Simplicity and Interpretability: OLS provides a straightforward model with easily interpretable coefficients, making it suitable for initial explorations into complex economic data.
- Statistical Significance Testing: It allows for rigorous statistical testing to ascertain the significance of each variable, enabling you to focus on the most impactful factors on wealth inequality.

### Support Vector Regression (SVR)

Relevance and Usefulness:
- Handling Non-Linear Relationships: SVR is particularly adept at dealing with non-linear relationships, which are common in economic data. This makes it suitable for capturing complex patterns in your dataset.
- Robustness to Outliers: SVR is less sensitive to outliers, ensuring that extreme values in economic indicators do not unduly influence the model's performance.
- Flexibility with Kernel Choice: The use of different kernels (like linear or RBF) in SVR provides flexibility, allowing for the exploration of both linear and non-linear relationships in your data.

### Random Forest Regression

Relevance and Usefulness:
- Handling Multiple Features: Random Forest is effective when dealing with datasets with a large number of variables. It can efficiently process and evaluate the importance of various economic factors affecting the Gini coefficient.
- Capturing Complex Interactions: This method is capable of capturing complex, non-linear interactions between variables, which is crucial in understanding the multifaceted nature of wealth inequality.
- Reduced Overfitting Risk: Random Forest reduces the risk of overfitting, a common problem in economic modeling, by averaging multiple decision trees, leading to more reliable predictions.
- Insightful Feature Importance: It provides insightful information on feature importance, helping to identify key drivers of wealth inequality.

## Results:

The results of the OLS regression were predictably disappointing as the Gini Coefficient is a nonlinear measure and so a linear regression failed to capture the data had a r^2 value of 0.06.
The results for support vector classification were equally disappointing till we realized that the Gini is continuous variable and splitting it up into categories was a ham handed way to make continuous data into categorical. We decided that because SVR can handle multiple-dimensional data effectively which is what the Gini Coefficient is. It had a R^2 value of R^2 = 0.65 which is miles better performance than the OLS regression. RFR combines multiple decision trees very efficiently and decreases overfitting when compared to SVR. It is also far easier to access important visualizations like feature importance. This resulted in improved performance with an R^2 value of 0.81 and an infinitesimally small mean squared error.

## Conclusion:

Our project's exploration into the relationship between minimum wage and wealth inequality, as quantified by the Gini coefficient, revealed significant insights through varied regression methodologies. The Ordinary Least Squares (OLS) regression displayed limited effectiveness, evidenced by a low R² value of 0.06, owing to its linear approach which was inadequate for the nonlinear nature of the Gini coefficient. In contrast, Support Vector Regression (SVR) adapted better to the multidimensional data, resulting in a markedly improved R² of 0.65. The most compelling results were obtained from Random Forest Regression (RFR), which not only addressed overfitting issues seen in SVR but also provided accessible, insightful visualizations like feature importance. RFR's superior performance was highlighted by an impressive R² value of 0.81 and a minimal mean squared error. These findings underscore the importance of selecting appropriate models for economic data, with SVR and RFR offering substantial improvements over OLS in understanding the complexities of wealth inequality.

### citation: The above was text was formatted and well documented using Open AI ChatGPT 4.0

# Repository Guide
To run this repository, simply clone the repo and run the files of your choosing. All code is reproducible, so this should present no errors.
```python
git clone https://github.com/harshil0217/CMSE_Min_Wage_Project.git
```

This repo is divided into two main directories. "Data" and "Regression".

The "Data" directory contains all the files used to generate the data used in the regression. The dataset used contains information on a variety of economic indicators for every state from years 2010-2019. Within the "Data" directory, there is a folder for each variable that is present in the final dataset. If the data for that variable is sourced from a csv file, the raw csv file, a preprocessing ipynb notebook, and the final output csv will be present in that directory. However, if the data for that variable is sourced from an API, then the variable file will only contain the preprocessing notebook (which also sources the data from the relevant API) and the final output csv. The state_compiled.ipynb notebook is also present in the Data directory. It reads in the path for all of the final output csvs for each variable and compiles them into a single data frame that is then exported to a csv file titles "state_econ", which is then used in our regressions. The Data folder also contains a number of Folium maps that show state by state comparisons for each variable (for example, the gini map shows which states have the highest and lowest values for gini coefficient).

The "Regression" directory contains the three regressions we generated from our data (OLS, SVR, and RFR). Each notebook file imports state_econ.csv and runs the regression using that data. Each regression file also contains the results and accompanying visualizations associated with that regression.

# Roles and Responsibilities

Harshil - Collected data on variables, wrote OLS regression

Shayna - Wrote the Random Forest Regression and Decision Tree visualization, made slides for the Check-in and Final Project  

Tanmay - Collected household income data, wrote results part of abstract, wrote Support Vector Regression and made plots 

Viraj - Collected data on factors affecting wealth inequality, worked on visualisations for the inital presentation and completed every section of abstract except the results.
