# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt


df = pd.read_csv("Superstore.csv")


df.head()

df1=df.loc[:,["Ship Mode","Sales"]]

df1=df.groupby(by=["Ship Mode"]).sum()

labels=[]
for i in df1.index:
    labels.append(i)
colors = sns.color_palette('bright')
plt.pie(df1["Sales"],labels=labels,autopct = '%0.0f%%')
plt.show

df.head()

df1

df1.info()

df1=df1.groupby(by=["Category"]).sum()
labels=[]
for i in df1.index:
    plt.pie(df1["Profit"],colors = colors,labels=labels,autopct='0.0f%%')


sates=df.loc[:,["State","Sales"]]

plt.figure(figsize=(10,10))
sns.barplot(x="State",y="Sales",data=states)
plt.xticks(rotation=90)
plt.xlabel=("STATE")
plt.ylabel=("SALES")
plt.show()

sns.set_style('whitegrid')
sns.countplot(x='Segment',data= df, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Category',data=df, palette='rainbow')


sns.set_style('whitegrid')
sns.countplot(x='Sub-Category',data=df, palette='rainbow')


sns.set_style('whitegrid')
sns.countplot(x='Region',data=df, palette='rainbow')


sns.set_style('whitegrid')
sns.countplot(x='Ship Mode',data=df, palette='rainbow')


category_hist = sns.FacetGrid(df, col='Ship Mode', palette='rainbow')
category_hist.map(plt.hist, 'Category')
category_hist.set_ylabels('Number')


subcategory_hist = sns.FacetGrid(df, col='Segment', height=10.5, aspect=4.6)
subcategory_hist.map(plt.hist, 'Sub-Category')
subcategory_hist.set_ylabels('Number')


grid = sns.FacetGrid(df, row='Category', col='Sub-Category', height=2.2, aspect=1.6)
grid.map(sns.barplot, 'Profit', 'Segment', alpha=.5, ci=None)
grid.add_legend()
```

# OUPUT
