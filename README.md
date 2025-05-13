# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
df=sns.load_dataset("tips")
df
```
![image](https://github.com/user-attachments/assets/d73024cc-3968-44a1-9b4d-2c0c09ad3fa4)

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto",palette="Set1")
```
![image](https://github.com/user-attachments/assets/8c72360e-ecce-4aad-94b4-6731f56d3d21)
```
tips=sns.load_dataset("tips")
avg_total_bill=tips.groupby("day")["total_bill"].mean()
avg_tip=tips.groupby("day")["tip"].mean()
```
![image](https://github.com/user-attachments/assets/19aaa622-aba3-49bd-9c1e-6f3bec62a31a)


```
plt.figure(figsize=(8,6))
plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill")
plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip")
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/30c2e622-c97a-4905-b644-39ca79e7a9bb)
```
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()
```
![image](https://github.com/user-attachments/assets/dd7d7d15-50f2-4607-8797-8e59a0b74046)

```
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip",width=0.4)
plt.xlabel("Time of Day")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Time of Day")
plt.legend()
plt.show()
```
![image](https://github.com/user-attachments/assets/13cf6902-ac7f-4520-96ab-1bf0d5dac973)

```
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette="Set3")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Sex")
plt.show()
```
![image](https://github.com/user-attachments/assets/09c4fe27-1dd4-41e6-a33a-900b71ac69a2)

```
import pandas as pd
tit=pd.read_csv("/content/titanic_dataset .csv")
tit
```
![image](https://github.com/user-attachments/assets/8e1d004c-8e75-4cc7-897c-c8a0fe991365)

```
plt.figure(figsize=(8,5))
sns.barplot(x="Embarked",y="Fare",data=tit,palette="rainbow")
plt.title("Fare of Passengers by Embarkation Town")
```
![image](https://github.com/user-attachments/assets/f3ebd171-ce32-4ae5-99a7-7416bf55baf6)

```
plt.figure(figsize=(8,5))
sns.barplot(x="Embarked",y="Fare",data=tit,palette="rainbow",hue="Pclass")
plt.title("Fare of Passengers by Embarkation Town, Divide by class")
```
![image](https://github.com/user-attachments/assets/498985fd-af5f-46b3-be2f-45e04e1d2dd5)

```
df=sns.load_dataset("tips")
sns.scatterplot(x="total_bill",y="tip",hue="sex",data=df,palette="Set1")
plt.xlabel("Total Bill")
plt.ylabel("Tip")
plt.title("Total Bill vs. Tip by Sex")
plt.show()
```
![image](https://github.com/user-attachments/assets/5101554a-51ad-4eb9-b272-ac9448612ea1)

```
sns.histplot(data=df,x="total_bill",hue="smoker",kde=True,palette="Set1",color="red")
plt.xlabel("Total Bill")
plt.ylabel("Frequency")
plt.title("Distribution of Total Bill")
```
![image](https://github.com/user-attachments/assets/f872287b-756a-4a4f-91b0-cd600c954cf0)

```
df=sns.load_dataset("tips")
sns.boxplot(x="day",y="total_bill",hue="sex",data=df,palette="Set2")
```
![image](https://github.com/user-attachments/assets/8e3562ae-91cd-4d30-92f2-66e437808556)

```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=df,linewidth=2,width=0.6,
            fliersize=7,flierprops={"marker":"o","markerfacecolor":"grey"},
            boxprops={"facecolor":"red","edgecolor":"black"},
            whiskerprops={"color":"darkblue","linestyle":"--","linewidth":2},
            capprops={"color":"darkblue","linestyle":"--","linewidth":2},palette="Set1")
```
![image](https://github.com/user-attachments/assets/a8ff1985-5ba6-4e2d-a70d-3aef0592b47d)

```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette="Set1",inner="quartile")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill")
plt.title("Distribution of Total Bill by Day and Smoker Status")
```
![image](https://github.com/user-attachments/assets/f4d44df9-e257-4069-9597-a096e042b6d5)

```
sns.set(style="whitegrid")
tip=sns.load_dataset("tips")
sns.violinplot(x="day",y="tip",data=tip,palette="Set2")
```
![image](https://github.com/user-attachments/assets/e3317500-b0be-40ea-b1b1-1402a72dd2f4)

```
import seaborn as sns
sns.set(style="whitegrid")
tips=sns.load_dataset("tips")
sns.violinplot(x=tip["total_bill"],palette="Set1")
```
![image](https://github.com/user-attachments/assets/9df886e1-355b-4c9c-9159-be8f54196b98)

```
sns.set(style="whitegrid")
tips=sns.load_dataset("tips")
sns.violinplot(x="tip",y="day",data=tip,palette="rainbow")
```
![image](https://github.com/user-attachments/assets/82f0b3b1-dc38-47ad-a927-fd781a29a92c)

```
sns.kdeplot(data=tips,x='total_bill',hue="time",multiple="layer",linewidth=3,palette="Set2",alpha=0.8)
```
![image](https://github.com/user-attachments/assets/b5165a46-2ab8-401c-97a2-2b1d8bdc5635)

```
sns.kdeplot(data=tips,x='total_bill',hue="time",multiple="stack",linewidth=3,palette="Set3",alpha=0.8)
```
![image](https://github.com/user-attachments/assets/4e75f0ca-fc85-4514-a032-7d9f5f0e8329)

```
sns.kdeplot(data=tips,x='total_bill',hue="time",multiple="fill",linewidth=3,palette="Set1",alpha=0.8)
```
![image](https://github.com/user-attachments/assets/8dc141a6-63be-4a03-ad8e-1c54ab56c15f)

```
tips=sns.load_dataset("tips")
num=tips.select_dtypes(include=['float64','int64']).columns
corr=tips[num].corr()
sns.heatmap(corr,annot=True,cmap="YlGnBu")
```
![image](https://github.com/user-attachments/assets/1851dc98-25a4-4422-a9eb-39015e34dc05)

```
sns.heatmap(corr,cmap="YlGnBu")
```
![image](https://github.com/user-attachments/assets/8a6d5389-6b20-49d4-8481-f9572a02fe23)

# Result:
Thus the data visualization techniques of seaborn has been implemented Successfully.
