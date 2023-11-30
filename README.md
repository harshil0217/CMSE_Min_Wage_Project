# CMSE_Min_Wage_Project
Project Analyzing Minimum Wage Alongisde other Factors that Contribute to Income Inequality

Harshil Chidura, Viraj Shah, Shayna McConville, Tanmay Shekhar, Abigail Werthmann

# Abstract

# Repository Guide
To run this repository, simply clone the repo and run the files of your choosing. All code is reproducible, so this should present no errors.

This repo is divided into two main directories. "Data" and "Regression".

The "Data" directory contains all the files used to generate the data used in the regression. The dataset used contains information on a variety of economic indicators for every state from years 2010-2019. Within the "Data" directory, there is a folder for each variable that is present in the final dataset. If the data for that variable is sourced from a csv file, the raw csv file, a preprocessing ipynb notebook, and the final output csv will be present in that directory. However, if the data for that variable is sourced from an API, then the variable file will only contain the preprocessing notebook (which also sources the data from the relevant API) and the final output csv. The state_compiled.ipynb notebook is also present in the Data directory. It reads in the path for all of the final output csvs for each variable and compiles them into a single data frame that is then exported to a csv file titles "state_econ", which is then used in our regressions.

# Roles and Responsibilities

```python

```
