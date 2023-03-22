# Ex02-Outlier

You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR 

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

    (i) Using IQR detect weight outliers and print them

    (ii) Using IQR, detect height outliers and print them
    
    
## Aim:

 TO detect and remove the outliers in the given data set and save the final data.

## Algorithm:

## Step 1

Import the required packages(pandas,numpy,scipy)

## Step 2

Read the given csv file

## Step 3

Convert the file into a dataframe and get information of the data.

## Step 4

Remove the non numerical data columns using drop() method.

## Step 5

Detect the outliers in the data set using z scores method.

## Step 6

Remove the outliers by z scores and list manupilation or by using Interquartile Range(IQR)

## Step 7

Check if the outliersare removed from data set using graphical methods.

## Step 8

Save the final data set into the file.

## Program:

## 1) & (2) Examine price_per_sqft column and use IQR to remove outliers and create new dataframe.

Program developed by : D.Dhanumalya

Register number : 212222230030

import pandas as pd

import numpy as np

import seaborn as sns

df = pd.read_csv("/content/bhp.csv")

df



df.head()

df.describe()

df.info()

df.isnull().sum()

df.shape

sns.boxplot(x="price_per_sqft",data=df)

q1 = df['price_per_sqft'].quantile(0.25)

q3 = df['price_per_sqft'].quantile(0.75)



print("First Quantile =",q1,"\nSecond Quantile =",q3)

IQR = q3-q1

ul = q3+1.5*IQR

ll = q1-1.5*IQR

df1 =df[((df['price_per_sqft']>=ll)&(df['price_per_sqft']<=ul))]

df1



df1.shape

sns.boxplot(x="price_per_sqft",data=df1)

## (3)Examine price_per_sqft column and use zscore of 3 to remove outliers.

from scipy import stats

z = np.abs(stats.zscore(df['price_per_sqft']))

df2 = df[(z<3)]

df2



print(df2.shape)


sns.boxplot(x="price_per_sqft",data=df2)

## (4)(i) For the data set height_weight.csv detect weight outliers using IQR method.

import pandas as pd

import numpy as np

import seaborn as sns

df = pd.read_csv("/content/height_weight - Sheet1.csv")

df



df.head()

df.info()

df.describe()

df.isnull().sum()

df.shape

print("First Quantile =",q1,"\nSecond Quantile =",q3)

IQR = q3-q1

ul = q3+1.5*IQR

ll = q1-1.5*IQR

df1 =df[((df['weight']>=ll)&(df['weight']<=ul))]

df1



df1.shape

sns.boxplot(x="weight",data=df1)

## (4)(ii) For the data set height_weight.csv detect height outliers using IQR method.

sns.boxplot(x="height",data=df)

q1 = df['height'].quantile(0.25)

q3 = df['height'].quantile(0.75)



print("First Quantile =",q1,"\nSecond Quantile =",q3)

IQR = q3-q1

ul = q3+1.5*IQR

ll = q1-1.5*IQR

df2 =df[((df['height']>=ll)&(df['height']<=ul))]

df2


df2.shape

sns.boxplot(x="height",data=df2)

## Output:

## (1)(2) Examine price_per_sqft column and use IQR to remove outliers and create new dataframe.

## Dataset:
![11](https://user-images.githubusercontent.com/119218812/227016689-39c858d8-5ff7-438b-82a4-fc7a89d44fdf.png)

## Dataset Head :
![12](https://user-images.githubusercontent.com/119218812/227016857-b45f7407-3385-4014-8de9-413e2edf2eef.png)


## Dataset Info :
![13](https://user-images.githubusercontent.com/119218812/227016896-fde5ba18-535c-45cc-8f5a-ad83b6cdd443.png)


## Dataset Describe:
![14](https://user-images.githubusercontent.com/119218812/227016918-34ac1210-dd5b-4769-9262-3f8550b3f319.png)


## Null Values:
![15](https://user-images.githubusercontent.com/119218812/227016947-79755bb6-da65-42e7-8ba6-99ba54384039.png)


## Dataset Shape:
![16](https://user-images.githubusercontent.com/119218812/227017008-94be1f86-0aa7-4322-870e-d1eb295019ea.png)


## Box plot of price_per_sqft column with outliers:
![17](https://user-images.githubusercontent.com/119218812/227017028-1c2d5ed3-550f-4e7a-9372-42e3e4a22781.png)


## price_per_sqft - Dataset after removing outliers:
![18](https://user-images.githubusercontent.com/119218812/227017051-39e680dc-de12-4b92-b933-3ea76ebb05c4.png)


## price_per_sqft - Shape of Dataset after removing outliers :
![19](https://user-images.githubusercontent.com/119218812/227017071-0af3c48f-70ca-4de8-b216-2fb51319411f.png)


## Box Plot of price_per_sqft column without outliers:
![110](https://user-images.githubusercontent.com/119218812/227017122-b0521dd1-9550-4edf-b97b-3588014fced2.png)


## (3) Examine price_per_sqft column and use zscore of 3 to remove outliers.

## Dataset after removal of outlier using z score:
![31](https://user-images.githubusercontent.com/119218812/227017172-1167e69c-d787-4f40-9cb4-1c06c98aa264.png)


## Shape of Dataset after removal of outlier using z score:
![32](https://user-images.githubusercontent.com/119218812/227017202-38bbb6de-9e69-4f02-870b-30157e8ba0b2.png)

![33](https://user-images.githubusercontent.com/119218812/227017235-0b95f9c8-1483-43e0-bb8d-22e4462a2f47.png)

## (4) For the data set height_weight.csv detect weight and height outliers using IQR method:

## Dataset:
![41](https://user-images.githubusercontent.com/119218812/227017305-c4e04585-c678-4d85-894e-94ab00d729f0.png)


## Dataset Head:
![42](https://user-images.githubusercontent.com/119218812/227017331-c4c0f195-1cd6-4c34-8bd2-48c618c9a592.png)


## Dataset Info:
![43](https://user-images.githubusercontent.com/119218812/227017349-32bd7beb-2024-48f6-a98e-5c62d4dbde15.png)


## Dataset Describe:
![44](https://user-images.githubusercontent.com/119218812/227017374-d30359a1-71ed-443f-a5ac-90345b9a3c79.png)


## Null Values:
![45](https://user-images.githubusercontent.com/119218812/227017387-1a54c166-5000-4acf-ad9a-be4f882710e1.png)


## Dataset Shape:
![46](https://user-images.githubusercontent.com/119218812/227017405-60fada04-bb60-4573-947d-47a2cc43916b.png)


## Weight - With outliers:
![47](https://user-images.githubusercontent.com/119218812/227017428-f72bb867-ae8e-48db-81cb-457bab2737bd.png)


## Weight - Dataset after removing Outliers using IQR method:
![48](https://user-images.githubusercontent.com/119218812/227017445-38927878-2d96-48bb-8625-6f8df1c188b6.png)


## Weight - Shape of Dataset after removing Outliers using IQR method:
![49](https://user-images.githubusercontent.com/119218812/227017461-db8fd42c-49ab-4cfa-9abe-ed0ac7474fef.png)


## Weight - Without Outliers using IQR method:
![410](https://user-images.githubusercontent.com/119218812/227017491-a7ab509a-334e-4ea6-a2fe-fdcadc03b5ac.png)


## Height - With outliers:
![411](https://user-images.githubusercontent.com/119218812/227017508-6b1fa067-9268-4b3b-ba66-486d005cfa95.png)


## Height - Dataset after removing Outliers using IQR method:
![412](https://user-images.githubusercontent.com/119218812/227017539-6aed9859-8d4b-4947-abad-3f2874f2470b.png)


## Height - Shape of Dataset after removing Outliers using IQR method:
![413](https://user-images.githubusercontent.com/119218812/227017586-a74be5e8-3b86-4bc8-8b66-9886dbeca3a8.png)


## Height - Without Outliers using IQR method:
![414](https://user-images.githubusercontent.com/119218812/227017604-922dcd61-4feb-45a2-89f6-32bf6e5c1d2f.png)


## Result:

Thus the outliers are detected and removed in the given file and the final data set is saved into the file.
