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
PROGRAM DEVELOPED BY : Mirudhula D

REGISTER NUMBER : 212221230060

~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df=pd.read_csv("Superstore.csv", encoding='windows-1252')
df

df.head()

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
Dataset

![image](https://user-images.githubusercontent.com/94828147/203357722-ffc0d23a-f6ea-4160-b246-d43370e032a5.png)

Head

![image](https://user-images.githubusercontent.com/94828147/203357822-1e707f4d-0a79-4e00-a5a7-b6d0dedea362.png)

Line plot

![image](https://user-images.githubusercontent.com/94828147/203357909-7f703c1b-3bca-458a-93da-d40e9255a618.png)

Scatter plot 1

![image](https://user-images.githubusercontent.com/94828147/203357983-bcf6fd56-d023-4a7c-aee2-2ec6e31e454a.png)

Box plot 1

![image](https://user-images.githubusercontent.com/94828147/203358089-5e327191-a8d8-4bce-80ec-55652b257d72.png)

Bar plot

![image](https://user-images.githubusercontent.com/94828147/203358170-550aad90-7030-4e71-a03a-70122723d6f6.png)

Point plot

![image](https://user-images.githubusercontent.com/94828147/203358246-0cc97e59-d057-4e46-ba0b-0f80930e6c89.png)

Count plot

![image](https://user-images.githubusercontent.com/94828147/203358328-48368544-cc03-4c01-9d86-fb7e56fbf2cc.png)

Histogram plot 1

![image](https://user-images.githubusercontent.com/94828147/203358386-361ed977-6f2f-4602-8a44-2c2d0c4ad59f.png)

KDE plot

![image](https://user-images.githubusercontent.com/94828147/203358448-bf1bac38-a5f4-42af-a936-ed1ff9a5d51a.png)

Data Visualization Using MatPlotlib

Plot

![image](https://user-images.githubusercontent.com/94828147/203358575-17405bc4-4fc0-4c80-8bcf-e88c554e1d65.png)

Heatmap

![image](https://user-images.githubusercontent.com/94828147/203358631-af4e9a84-35d9-4494-b6a2-547bb0051537.png)

Pie chart

![image](https://user-images.githubusercontent.com/94828147/203358694-45eae67e-8f9b-48f9-8581-1a3f860b357f.png)

![image](https://user-images.githubusercontent.com/94828147/203358745-62f0b80d-42aa-4b10-b940-96d17ba494a9.png)

Histogram plot 2

![image](https://user-images.githubusercontent.com/94828147/203358866-d8641c88-75d9-4274-bef5-40d1f96b62f6.png)

Bar graph

![image](https://user-images.githubusercontent.com/94828147/203358911-f5c88e4b-9073-49c6-bdb6-825a1a37a586.png)

Scatter plot 2

![image](https://user-images.githubusercontent.com/94828147/203358976-96b2f77f-2c43-4c98-9000-3ca2506ac828.png)

Box plot 2

![image](https://user-images.githubusercontent.com/94828147/203359084-325e3ba2-fa05-4d8c-91e4-1bac09088697.png)

## RESULT:
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

