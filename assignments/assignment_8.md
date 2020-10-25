# Assignment 8 - Regression Analysis

# Tutorials to review

Review [this notebook with regression analysis](https://github.com/justmarkham/DAT4/blob/master/notebooks/08_linear_regression.ipynb)

Note that the code for a linear regression is:

```python
import statsmodels.formula.api as smf # convention for importing statsmodels

# assuming you have a dataframe `df` with variables `Return` and `Unemployment`
model = smf.ols(formula="Return ~ Unemployment", data=df)
result = model.fit()
result.summary()
```

## Assignment

Create a dataset with the following variables:

```
Month,Revenue,Advertising
March,50000,2000
April,70000,3000
May,55000,1500
June,65000,3500
July,55000,1000
August,65000,2000
September,45000,1500
October,80000,4000
November,55000,2500
December,60000,2500
```

Load the dataset and run the regression where revenue is explained by advertising. See [https://www.shanelynn.ie/python-pandas-read_csv-load-data-from-csv-files/](https://www.shanelynn.ie/python-pandas-read_csv-load-data-from-csv-files/) on how to read a csv into a dataframe.

> Note: `result.summary()` will display a warning (in a red box) that the sample size is small; this warning can be safely ignored