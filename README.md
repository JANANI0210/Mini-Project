# MINI-PROJECT

## DESCRIPTION OF THE PROJECT
The dataset is about life expectancy, health factors for 193 countries from the  WHO data repository website and its corresponding economic data. 

Among all categories of health-related factors only those critical factors were chosen which are more representative.

It has been observed that in the past 15 years , there has been a huge development in health sector resulting in improvement of human mortality rates especially in the developing nations in comparison to the past 30 years.

Therefore, in this project we have considered data from year 2000-2015 for 193 countries for further analysis. The individual data files have been merged together into a single dataset. 

## CODE:

### DATA CLEANING

import pandas as pd

import numpy as np

from datetime import datetime

import matplotlib.pyplot as plt

import seaborn as sns

%matplotlib inline

from sklearn.impute import SimpleImputer 

from sklearn.preprocessing import StandardScaler

from sklearn.preprocessing import MinMaxScaler

from sklearn.preprocessing import OneHotEncoder

from sklearn.model_selection import train_test_split

df = pd.read_csv('/content/Life Expectancy Data.csv')

df.head()

df.tail()

###  REMOVING OUTLIERS

sns.boxplot(x="Alcohol", data=df)

sns.boxplot(x="infant deaths", data=df)

sns.scatterplot(df['Year'],df['infant deaths'])


### EXPLORATORY DATA ANALYSIS

sns.countplot(x="Adult Mortality",data=df)

sns.barplot(x=df['infant deaths'],y=df['Adult Mortality'],data=df)

sns.histplot(x="Year",data=df)

sns.distplot(df["Adult Mortality"])


### FEATURE GENERATION TECHNIQUES

from sklearn.preprocessing import OrdinalEncoder

enc = OrdinalEncoder()

enc.fit(df[["Country","Status"]])

df[["Country","Status"]] = enc.transform(df[["Country","Status"]])

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['Year'] = le.fit_transform(df['Year'])

sns.set(style ="darkgrid")

sns.countplot(df['Year'])

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['Country']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['Country'], axis=1)

df.head(10)

### FEATURE TRANSFORMATION TECHNIQUES

sm.qqplot(df.Year, fit=True , line='45')

plt.show()


sm.qqplot(df.Year, fit=True , line='45')

plt.show()

from sklearn.preprocessing import QuantileTransformer

df4=df.copy()

qt=QuantileTransformer(output_distribution='normal')

df4['Year']=pd.DataFrame(qt.fit_transform(df4[['Year']]))

sm.qqplot(df4['Year'],fit=True,line='45')

plt.show()

categ_cols = ['Country', 'Status']

numeric_cols = [] 

for i in df.columns:

if i != 'Status' and df[i].dtype in (np.float64, np.int64):
    
numeric_cols.append(i)




plt.figure(figsize=(20,30))

for i,col in enumerate(numeric_cols, 1):

plt.subplot(5, 4, i)
    
plt.boxplot(df[col])
    
plt.title(col)
    
plt.show()

### DATA VISUALISATION

import seaborn as sns

sns.lineplot(x="Year",y="infant deaths",data=df,marker='o')

plt.title("Year vs infant deaths")

plt.xticks(rotation = 90)

plt.show()

sns.lineplot(x="Year",y="Population",data=df,marker='o')

plt.xticks(rotation = 90)

plt.title("Year vs Population")

plt.show()

df.hist(bins=50, figsize=(20,15))

plt.show()

plotting correlation heatmap

plt.figure(figsize= (12,12)) 

dataplot = sns.heatmap(df.corr(), cmap="YlGnBu", annot=True)

  
displaying heatmap

plt.savefig('plot1.eps')

plt.show()

sns.set(rc={'figure.figsize':(5,5)})

sns.violinplot( df['Status'],df['Life expectancy '])


country_data = px.data.gapminder()

country_data.tail()

map_fig = px.scatter_geo(country_data,locations = 'iso_alpha', projection = 'orthographic'

                        
### SCREENSHOTS OF OUTPUT


![Screenshot (299)](https://user-images.githubusercontent.com/86832944/204755055-f2892c9e-e290-495f-b469-70ca119512a4.png)

![Screenshot (267)](https://user-images.githubusercontent.com/86832944/204128534-688c8dd5-af07-4011-a245-44314dca5466.png)

![Screenshot (268)](https://user-images.githubusercontent.com/86832944/204128549-8b6b493d-db58-4bdc-89a3-01d3d5f3fc7d.png)

![Screenshot (271)](https://user-images.githubusercontent.com/86832944/204128562-02be9df0-6d40-4a92-b1a7-57304d17fa6b.png)

![Screenshot (273)](https://user-images.githubusercontent.com/86832944/204128617-ea363d5d-0557-424c-bbdc-a26d77eab0f7.png)



![Screenshot (271)](https://user-images.githubusercontent.com/86832944/204746182-cf173490-4e33-4ed1-b792-3a22bd674a47.png)

![Screenshot (272)](https://user-images.githubusercontent.com/86832944/204746677-b7e2f4ec-ed99-4d0f-a682-4ca8b068fbe4.png)

![Screenshot (273)](https://user-images.githubusercontent.com/86832944/204747111-8b5ac42c-86ee-46a7-bda6-e6c9e188d39a.png)



![Screenshot (274)](https://user-images.githubusercontent.com/86832944/204748318-028da2c8-63d9-426b-a6d8-f821b364f328.png)

![Screenshot (275)](https://user-images.githubusercontent.com/86832944/204748395-f2a2ab6b-cbb9-4d83-9298-34c0fafa1740.png)

![Screenshot (276)](https://user-images.githubusercontent.com/86832944/204748472-60294f9b-ec80-41b5-bcfb-f121a4666b0e.png)

![Screenshot (277)](https://user-images.githubusercontent.com/86832944/204748571-0246b966-6dc0-4b9d-8247-c140673987da.png)



![Screenshot (278)](https://user-images.githubusercontent.com/86832944/204749763-47c50a31-2f6a-40c0-8767-8eff256b9e76.png)

![image](https://user-images.githubusercontent.com/86832944/204750623-4f18240b-005f-4e03-89eb-8247bf27d6cd.png)

![image](https://user-images.githubusercontent.com/86832944/204750825-c2320e99-4609-4551-a9f2-51908418b527.png)

![image](https://user-images.githubusercontent.com/86832944/204751820-fbddadbf-1415-44df-9479-f4e3f1c2acb7.png)


 ![image](https://user-images.githubusercontent.com/86832944/204753152-f4f923a0-239c-4201-aacf-5ca211d6da57.png)

![image](https://user-images.githubusercontent.com/86832944/204753254-d6bb7a00-111a-41f1-bb21-071b04437e13.png)

![image](https://user-images.githubusercontent.com/86832944/204753455-b0bc9389-6730-45da-b3d0-1aa3e9f75883.png)

![image](https://user-images.githubusercontent.com/86832944/204753615-c716953a-0fdb-4a39-8a94-cbad2d6017ba.png)

![image](https://user-images.githubusercontent.com/86832944/204753914-0be25b19-68bf-4343-9389-065a086a374f.png)

![Screenshot (299)](https://user-images.githubusercontent.com/86832944/204754596-bb936b66-c37c-43e8-9d7f-52c87a8ff139.png)












