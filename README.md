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
![oimg1 (1)](https://user-images.githubusercontent.com/94508142/172656661-e77ce8e1-4934-49a7-a87f-a7d7f3ed00a6.png)
![oimg1 (2)](https://user-images.githubusercontent.com/94508142/172656729-323f104e-5801-4727-a69c-614b5dc28d21.png)
![oimg1 (3)](https://user-images.githubusercontent.com/94508142/172656794-16a1c200-d9f8-43da-b237-f18cf62b15bc.png)
![oimg1 (4)](https://user-images.githubusercontent.com/94508142/172656890-2bf252bf-5e15-434e-90f7-e7d457b8b6c3.png)
![oimg1 (5)](https://user-images.githubusercontent.com/94508142/172657006-51e015e7-9016-4167-8fd2-5aa42f23923a.png)
![oimg1 (6)](https://user-images.githubusercontent.com/94508142/172657079-0387dab8-bdd9-407e-8db2-30b95cd904b0.png)
![oimg1 (7)](https://user-images.githubusercontent.com/94508142/172657132-4bf8b558-a16d-4580-bf98-f14b6e12eb94.png)
![oimg1 (8)](https://user-images.githubusercontent.com/94508142/172657205-06a369c6-2e91-476f-bf88-f7782db44e28.png)
![oimg1 (9)](https://user-images.githubusercontent.com/94508142/172657249-31b9a9ae-6fb2-4cad-b166-f46da07fa520.png)
![oimg1 (10)](https://user-images.githubusercontent.com/94508142/172657318-a48ec2aa-0c3a-4155-be47-c0b288ba4079.png)
#Result:
Data Visualization on a complex dataset and save the data to a file has been performed.




