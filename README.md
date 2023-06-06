# Ex-09-Data-Visualization-

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

import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

df.head()

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'])

plt.title("Highest Total Bill Amount by day")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

plt.show()

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.barplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

plt.show()


sns.barplot(x=df['sex'], y=df['tip'])

plt.title("Highest tips based on gender")

plt.show()

sns.barplot(x=df['day'],y=df['total_bill'])


plt.title("Total bill amount by day of the week")

plt.show()

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplotdata=df,(x=df['size'],y=df['total_bill'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.violinplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.barplot(x="time", y="tip", data=df)


plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()




# OUPUT

![op1](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/16739396-95f5-4718-a12e-880819742785)
![op2](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/dae48bff-8de6-4e08-84dd-61e4f14a7eb0)
![op3](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/7ba5c454-d644-4cf0-b411-7b5e0485c846)
![op4](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/96d1bb76-d76f-42e5-b08d-dc0e4a031048)
![op5](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/94d2c80e-a80e-438c-b6ec-ae417e02ba75)
![op6](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/c7bf9439-1e14-4279-805b-5c0815d37e01)
![op7](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/cf98f293-f141-4ac1-9fa2-f553293e4e42)
![op8](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/fbfb11e2-74ea-459d-b52e-be7932245d6a)
![op9](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/bcc40e04-5014-4b97-b813-c4b0d06cd863)
![op10](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/ad6fd5d5-3925-4e69-befc-038259e853ba)
![op11](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/2697bfcf-34d0-4787-a5f5-96303553c79d)
![op12](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/a2cfca9c-939f-48ed-8949-e546680bf70c)
![op13](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/c0900349-72fc-49bf-88a2-93aa308add2f)
![op14](https://github.com/Thirisaa/Ex-08-Data-Visualization_1/assets/112301582/10848604-6780-4307-addc-83f59f3ea702)

# RESULT
Thus data visualization on complex dataset was performed successfully.
