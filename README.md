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
```
Data Preprocessing

import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
print(df)

df.isnull().sum()

Handling Outliers
plt.figure(figsize=(8,8))
plt.title("Data with Outliers")
df.boxplot()
plt.show()

Removing Outliers
plt.figure(figsize=(8,8))
cols = ['size','tip','total_bill']
Q1 = df[cols].quantile(0.25)
Q3 = df[cols].quantile(0.75)
IQR = Q3 - Q1
df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]
plt.title("Dataset after removing outliers")
df.boxplot()
plt.show()

1) Which day of the week has the highest total bill amount?
sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])
plt.legend(loc="center")
plt.title("Highest Total Bill Amount by day of the week")
plt.show()

2) What is the average tip amount given by smokers and non-smokers?
sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])
plt.title("Average Tip Amount given by smokers and non-smokers")

3) How does the tip percentage vary based on the size of the dining party?
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

4) Which gender tends to leave higher tips?
sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")

5) Is there any relationship between the total bill amount and the day of the week?
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")

6) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()

7) Which dining party size group tends to have the highest average total bill amount?
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()

8) What is the distribution of tip amounts for each day of the week?
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()

9) How does the tip amount vary based on the type of service (lunch vs. dinner)?
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()

10) Is there any correlation between the total bill amount and the tip amount?
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```

# OUPUT


![Screenshot 2023-05-27 160742](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/323a3bce-67cf-478b-a036-cb8b63343799)

![Screenshot 2023-05-27 160750](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/e9e84ab1-5f3b-4dc6-a894-1b346e3f31ed)

![Screenshot 2023-05-27 160820](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/d44ba894-b9d5-4b24-a723-c7ddea1dc163)


![Screenshot 2023-05-27 160833](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/20097b97-a0c7-45b5-be30-3aa4e5d0218e)


![Screenshot 2023-05-27 160839](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/75b3ba5b-bf24-4afd-b995-a506528c4bf7)

![Screenshot 2023-05-27 160847](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/096cba4f-c043-48c2-be52-43fabca14835)


![Screenshot 2023-05-27 160855](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/d053e09e-db7b-4c6d-9fa0-2b5e2cc69042)


![Screenshot 2023-05-27 160901](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/ef17591d-8aab-42e9-9afd-f923bcc1e2eb)


![Screenshot 2023-05-27 160907](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/a894a449-c720-4c81-b0aa-d2d691ac58ea)


![Screenshot 2023-05-27 160913](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/13d5af4a-a0ad-4e8c-b113-ad901456a0fb)


![Screenshot 2023-05-27 160919](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/334574d5-cb78-4c1e-b135-28e5810854fd)

![Screenshot 2023-05-27 160926](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/c87552d5-31c9-4647-b959-53d8caa8f3c1)

![Screenshot 2023-05-27 160934](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/462baf62-2553-4f07-9b6b-7175bbb0a86c)

![Screenshot 2023-05-27 160942](https://github.com/Dharshan011/Ex-08-Data-Visualization_1/assets/113497491/d01cee27-f2cd-476d-b9e3-f106179fc7cd)

## RESULT
Thus the Data Visualization method is performed to the given data and to predict the outcome for the given question




