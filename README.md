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
~~~
Developed by:Thirugnanamoorthi G
Reg no:212221230117
~~~
~~~
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#5.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#6.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#7.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#8.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
~~~

# OUPUT

![1](https://user-images.githubusercontent.com/94980741/171547759-798dec1f-8678-46c5-9f66-078f30c80a8a.png)

# Data Visualization Using Seaborn:
![2](https://user-images.githubusercontent.com/94980741/171547837-abde0087-6017-4f35-9a3c-1a3e60468f0c.png)
![3](https://user-images.githubusercontent.com/94980741/171547843-09474541-57b1-4f04-aaf2-2d8e7733e5f9.png)
![4](https://user-images.githubusercontent.com/94980741/171547856-e637f446-0deb-42e4-8783-be6fd8bd344c.png)
![5](https://user-images.githubusercontent.com/94980741/171547868-16b208fa-dbd4-423a-bd31-06f52bada438.png)
![6](https://user-images.githubusercontent.com/94980741/171547884-7a047fc6-4b31-4d91-963c-2c19d4747796.png)
![7](https://user-images.githubusercontent.com/94980741/171547900-83194a57-6b6f-4e12-b131-d3ab29478646.png)
![8](https://user-images.githubusercontent.com/94980741/171547909-2cf71b6e-31f2-4f80-b2fc-b6c94621f351.png)
![9](https://user-images.githubusercontent.com/94980741/171547924-b3bf846f-829d-47d6-a34a-cb2bb6b862b1.png)
![10](https://user-images.githubusercontent.com/94980741/171547941-19d96718-be0d-47a0-80ef-5cbb7565d7dd.png)

# Data Visualization Using Matplotlib:
![11](https://user-images.githubusercontent.com/94980741/171547997-0c9a75b4-a49f-4587-be09-41b2939fec18.png)
![12](https://user-images.githubusercontent.com/94980741/171548002-0bd160f5-b49d-4655-8ccd-832ffccf7bc6.png)
![13](https://user-images.githubusercontent.com/94980741/171548068-5a9af1db-badc-4cdd-8c08-18a6966c0596.png)
![14](https://user-images.githubusercontent.com/94980741/171548083-9e7f573e-f4cd-4468-a24f-c8082adf9db1.png)
![15](https://user-images.githubusercontent.com/94980741/171548099-edefa8cb-cc29-4c82-b3c4-4fad303b915b.png)
![16](https://user-images.githubusercontent.com/94980741/171548111-d5f03080-34b1-4cdf-a42f-67c7db3be929.png)


# RESULT:
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

