# Ex.No: 01A PLOT A TIME SERIES DATA
##  Date: 
## AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
## ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
## PROGRAM:
### Name: RONICK AAKSHATH P
### Reg. No.: 212222240084
```python
import pandas as pd
import matplotlib.pyplot as plt

df=pd.read_csv("daily_website_visitors.csv", parse_dates=["Date"],index_col="Date")
df = df.drop(['Row', 'Day.Of.Week', 'Day'], axis = 1)

columns_to_convert = ['Page.Loads', 'Unique.Visits', 'First.Time.Visits', 'Returning.Visits']

for column in columns_to_convert:
    df[column] = pd.to_numeric(df[column].str.replace(',', ''), errors='coerce')

df.head()

df_filtered = df["2014":"2019"]

annual_mean = df_filtered.resample('Y').mean()
mean = annual_mean.plot(kind='line')
plt.xlabel("Year")
plt.ylabel("Web Visitors")
plt.title("Average Annual Web Visitors")
plt.show()
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/49aab60f-d19b-48a0-a4a9-e6dd1bddc54f)

## RESULT:
Thus we have created the python code for plotting the time series of given data.
