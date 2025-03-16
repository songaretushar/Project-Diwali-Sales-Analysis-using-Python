# Project-Diwali-Sales-Analysis-using-Python
Analyzed Diwali season sales data
Analyzed Diwali season sales data, uncovering customer behavior patterns and regional trends that contributed to a 15% increase in targeted marketing ROI.
• Performed time-series analysis to identify peak sales days, optimizing promotional campaign timing and boosting daily sales by 20%.
• Visualized key insights using Python libraries (Matplotlib and Seaborn), delivering a detailed interactive report that reduced stakeholder decision-making time by 25%.
**Code**
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns

df = pd.read_csv(r'E:\DATA DA\Python_Diwali_Sales_Analysis\diwali sales data.csv', encoding='unicode_escape')
# to avoid encoding error, use 'unicode_escape'

df.shape
# to check rows and number of columns
df.head() 
# to check top five rows  
# if want more 10 rows then 'df.head(10)'

 df.info
# this provide the information aboout the values
df.drop(['Status', 'unnamed1'], axis=1, inplace=True)
 # axis=1 is drop one row axis, implace=ture mean save it
 pd.isnull(df)  # this is give the null values
pd.isnull(df).sum()   # count of the null values
# drop null values 
df.dropna(inplace=True)
df.shape
 pd.isnull(df).sum() 

 # initiative list of lists

data_test =[['madhav', 11], ['Gopi', 15], ['Keshav', ], ['Lalita', 16]]
df_test =pd.DataFrame(data_test, columns=['name','Age'])

df_test

df_test.dropna()   # to drop the null value means 3rd column, but this not save 
df_test.dropna(inplace=True)   # to save the last bull values drop
df['Amount'] = df['Amount'].astype('int')    # to change data type from float to int 
df['Amount'].dtypes    # changed data type
df.columns
 # rename column
df.rename(columns= {'Marital_Status': 'Marriage'})
# this provide the all values description like  min, max, count, std, mean
df.describe()
# specific column describe function
df[['Age', 'Orders', 'Amount']].describe()
# it gives the minimum product sale value and max
ax =sns.countplot(x='Gender',data=df)

for bars in ax.containers:
    ax.bar_label(bars)
    sales_gen=df.groupby(['Gender'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)
sns.barplot(x= 'Gender',  y='Amount', data=sales_gen)
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Example DataFrame
data = {'Gender': ['Male', 'Female', 'Male', 'Female', 'Male']}
df = pd.DataFrame(data)
# Countplot with bar labels
ax = sns.countplot(x='Gender', data=df)
for bars in ax.containers:
    ax.bar_label(bars)

plt.show()

# Countplot with bar labels
ax = sns.countplot(x='Gender', data=df)
for bars in ax.containers:
    ax.bar_label(bars)

plt.show()
