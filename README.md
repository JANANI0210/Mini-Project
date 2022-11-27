# Mini-Project

The dataset is about life expectancy, health factors for 193 countries from the  WHO data repository website and its corresponding economic data. 

Among all categories of health-related factors only those critical factors were chosen which are more representative.

It has been observed that in the past 15 years , there has been a huge development in health sector resulting in improvement of human mortality rates especially in the developing nations in comparison to the past 30 years.

Therefore, in this project we have considered data from year 2000-2015 for 193 countries for further analysis. The individual data files have been merged together into a single dataset. 

## CODE:

### Data Cleaning

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

![Screenshot (267)](https://user-images.githubusercontent.com/86832944/204128534-688c8dd5-af07-4011-a245-44314dca5466.png)

![Screenshot (268)](https://user-images.githubusercontent.com/86832944/204128549-8b6b493d-db58-4bdc-89a3-01d3d5f3fc7d.png)

![Screenshot (271)](https://user-images.githubusercontent.com/86832944/204128562-02be9df0-6d40-4a92-b1a7-57304d17fa6b.png)

![Screenshot (273)](https://user-images.githubusercontent.com/86832944/204128617-ea363d5d-0557-424c-bbdc-a26d77eab0f7.png)


### 
