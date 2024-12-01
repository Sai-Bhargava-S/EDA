# EDA
basic practices of Exploratory data analysis
Exploratory Data Analysis
EDA is process of that Involves understanding,Summerzing,Visualizing data to uncover patterns and test the hypothese ,It helps data scientists gain insights into datasets and prepare them for modeling by cleaning, transforming, and understanding the relationships within the data.

Key Points to Remember for Exploratory Data Analysis (EDA)

1. Understand the Data: Analyze dataset structure (rows, columns, types) and summarize it using .info() and .describe(). Handle Missing Data: Identify and manage missing values using imputation or removal techniques.

2.Univariate Analysis: Explore individual variables (distributions, counts) using histograms and bar plots.

3.Bivariate and Multivariate Analysis: Examine relationships between variables with scatter plots, correlation heatmaps, and pair plots.

4.Detect Outliers: Use box plots or z-scores to identify and handle outliers effectively.

5.Feature Insights: Derive meaningful patterns, insights, or transformations (e.g., scaling, encoding) for better data understanding.

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.preprocessing import LabelEncoder

#Data collection

df=pd.read_csv("/content/data (1).csv")
df

#Exploratory Data Analysis

#printing the first few rows
df.head()
#printing the last no of rows
df.tail()
#finding the no of rows and columns
df.shape

#removeing the unamed column
df.drop(columns="Unnamed: 32",axis=1,inplace=True)
df.shape

#checking the datatypes
df.info()

#removing id column
df.drop(columns="id",axis=1,inplace=True)
df.isnull()
#digonsis is categorical variable
df.isnull().sum()


descriptive statisitcs
# Summary statistics for numerical columns
df.describe() :Summarizes numerical columns by providing metrics like count, mean, standard deviation, min, 25th percentile, median (50th percentile), 75th percentile, and max.
df.describe()

df['diagnosis'].value_counts()

#encoding the target column
label_encode=LabelEncoder()

labels= label_encode.fit_transform(df['diagnosis'])

df['target']=labels

df.drop(columns="diagnosis",axis=1,inplace=True)

df.head()
Benign-->0
Malgnint-->1

