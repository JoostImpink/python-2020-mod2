# Assignment 10 - Pandas dataframe

In this assignment you will be using pandas, which is a data mananagement package.

### First

First read these two overviews:

- [pandas overview (more general, 'dataframes' section is most relevant)](https://joostimpink.github.io/python-materials/07_pandas) 
- [pandas dataframe overview (more specific)](https://joostimpink.github.io/python-materials/07_pandas_dataframe)


### Background

Medicare has made data available over 2011-2016 for about 3,000 hospitals in the US, see [Cms.gov website](https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Inpatient.html)

### Dataset

You can download the excel sheet with [2016 data](https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Downloads/Inpatient_Data_2016_XLSX.zip).

Download the Excelsheet and save it in the same folder as your python script.

You can then load the dataset as follows:

```python
import pandas as pd

df = pd.read_excel('Medicare_Provider_Charge_Inpatient_DRGALL_FY2016.xlsx', skiprows=5)

# take a look at the first few records
df.head()

# how many records
len(df)
```

### Assignment

Answer the following questions:

- how many (unique) hospitals are in the dataset
- how many (unique) hospitals are in the States 'AR' and 'AK'
- choose a DRG and compute the average cost for each hospital ('provider') in the State of Florida

Hints: use `nunique`, `groupby(property).count()`; also see [https://stackoverflow.com/questions/17071871/select-rows-from-a-dataframe-based-on-values-in-a-column-in-pandas](https://stackoverflow.com/questions/17071871/select-rows-from-a-dataframe-based-on-values-in-a-column-in-pandas)


## Examples

```python
#how many unique providers in total
print(df["Provider Name"].nunique())

# a new dataframe with records from Alaska
df_AK = df[df['Provider State'] == "AK" ] 

# a new dataframe with records from Florida, and DRG definition containing '001'
df_FL_001 = df.loc[ ( df['Provider State'] == 'FL')  &  (  df['DRG Definition'].str.contains("001") )]
```