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

