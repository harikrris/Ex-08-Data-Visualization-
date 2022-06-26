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
# Importing packages
import pandas as pd
import numpy as np

# Importing visualization libraries
import seaborn as sns
import matplotlib.pyplot as plt

df_super = pd.read_csv('Superstore.csv')

df_super.head(5)

df_super=df_super.groupby(by=["Category"]).sum()
labels=[]
for i in df_super.index:
    labels.append(i)  
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df_super["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()


sns.set_style('whitegrid')
sns.countplot(x='Segment',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Category',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Sub-Category',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Region',data=df_super, palette='rainbow')

sns.set_style('whitegrid')
sns.countplot(x='Ship Mode',data=df_super, palette='rainbow')

category_hist = sns.FacetGrid(df_super, col='Ship Mode', palette='rainbow')
category_hist.map(plt.hist, 'Category')
category_hist.set_ylabels('Number')

subcategory_hist = sns.FacetGrid(df_super, col='Segment', height=10.5, aspect=4.6)
subcategory_hist.map(plt.hist, 'Sub-Category')
subcategory_hist.set_ylabels('Number')

grid = sns.FacetGrid(df_super, row='Category', col='Sub-Category', height=2.2, aspect=1.6)
grid.map(sns.barplot, 'Profit', 'Segment', alpha=.5, ci=None)
grid.add_legend()

# OUPUT

![o1](https://user-images.githubusercontent.com/79370364/175799350-eeb9c39c-11c5-447e-b861-cc7ad515a8b8.png)
![o2](https://user-images.githubusercontent.com/79370364/175799352-57889fe9-692c-46c0-b9eb-eaa7b7554622.png)
![o3](https://user-images.githubusercontent.com/79370364/175799354-b8203c50-a196-4281-9b6e-d84f6fc3aa41.png)
![o4](https://user-images.githubusercontent.com/79370364/175799355-6ad22abe-bf68-422d-8b6b-e719880cf339.png)
![o5](https://user-images.githubusercontent.com/79370364/175799356-6e0ad4f2-bae4-411e-98f1-e57ed2e36c55.png)
![o6](https://user-images.githubusercontent.com/79370364/175799357-bc7ee086-b255-461e-b8c6-12f2fb2e59e4.png)
![o7](https://user-images.githubusercontent.com/79370364/175799358-70daaf34-8c36-4a38-9ef6-d7788b9c6cd5.png)
![o8](https://user-images.githubusercontent.com/79370364/175799359-a47610d3-7675-4840-9d7f-da7297795c2d.png)
![o9](https://user-images.githubusercontent.com/79370364/175799360-80005e0b-fb01-426e-b075-59ad7338b38e.png)
![o10](https://user-images.githubusercontent.com/79370364/175799361-c58ec301-58ac-49ef-a02c-77e9c28907aa.png)

# RESULT:
Data Visualization has been performed on a complex dataset and saved the data to a file
