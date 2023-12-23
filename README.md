 ## Table of Contents
 - [Introduction](#Introduction)
 - [Methodology](#Methodology)
 - [Data Preparation and Visualization](#Data-Preparation-and-Visualization)
 - [Findings](#Findings)
 - [Limitations](#Limitations)
 - [Recommendations](#Recommendations)
 - [Conclusion](#Conclusion)
 

![image](https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/4f1b5007-81af-4af3-b1e0-1cbd3fd8bb33)

## Introduction

This report presents a deep dive into the Census Income dataset, comprising 48,842 individuals, to understand the multifaceted factors influencing income levels. The objective is to unravel the socio-economic dynamics that shape an individual's earning potential.

## Methodology

The methodology employed in this analysis includes:
1.	Data Exploration: Initial assessment of variables and distributions.
2.	Data Cleaning: Addressing missing values and placeholders for data integrity.
3.	Exploratory Data Analysis (EDA): Delving into both categorical and numerical variables.
4.	Correlation and Advanced Analysis: Employing statistical methods to uncover deeper variable relationships.

## Data Preparation and Visualization

The data preparation involved:
•	Handling Missing and Placeholder Values: Ensuring accuracy by replacing unknowns in key columns.
•	Data Type Adjustments: Encoding categorical data for nuanced analysis.

Visualizations used include:
•	Correlation Heatmaps: To understand inter-variable relationships.
•	Bar Graphs and Pie Charts: For clear visual representation of categorical variables' distribution.

4.	Data Overview: Using df.info(), I  examined the dataset's structure, including the number of entries, columns, and data types.
5.	& 6. Statistical Summary: With df.describe() and its transposed version df.describe().T, I would have obtained a statistical summary of the dataset, providing insights into measures like mean, standard deviation, and range for numeric columns.

In these steps, my analysis focused on:
7.	& 8. Missing Value Analysis: I checked for missing values in the dataset using df.isna().sum(). The second command specifically identified columns with missing values greater than zero. This step is crucial in assessing data quality and determining the need for data cleaning or imputation.
8.	Random Data Sampling: By using df.sample(10), I  examined a random sample of 10 rows from the dataset. This is a common practice to get a quick sense of the data's variability and structure.
9.	Categorical Data Exploration: The command df.select_dtypes(include="object") would have helped I isolate the categorical variables in the dataset. Understanding categorical data is key to formulating strategies for data preprocessing, such as encoding.

In these steps, my analysis further delved into:
11.	Categorical Data Summary: I used df.select_dtypes(include="object").describe().T to get a summary of the categorical variables. This would include counts, unique values, top categories, and their frequencies, offering a comprehensive view of the categorical data.
12.	Workclass Value Counts: I specifically examined the distribution of values in the 'workclass' column with df["workclass"].value_counts(). This analysis would reveal the predominant work classes in the dataset and their relative proportions.
13.	Exploration of All Categorical Columns: I iterated over each categorical column, printing out their value counts. This exhaustive approach provides a detailed understanding of the distribution and frequency of categories across all categorical variables.
14.	Identification of Placeholder Values: With df.isin(["?"]).sum(), I identified columns containing placeholder values (like "?"), which are often used to denote missing or unknown data in categorical variables.
This detailed exploration of both numeric and categorical data indicates a thorough preliminary analysis, setting a solid foundation for deeper insights. 

In these steps, my analysis focused on addressing placeholder values in the dataset:
15.	& 17. Handling Placeholder Values in 'workclass': I replaced the placeholder value "?" in the 'workclass' column with "Unknown" using df.workclass.replace("?", "Unknown"). This is an important step in data cleaning, as it clarifies that these are known unknowns rather than missing data.
16.	& 18. Post-Cleaning Value Counts: After replacing the placeholders, I again checked the value counts with df.workclass.value_counts(). This would reveal the new distribution of 'workclass' values, now including "Unknown", and helps in assessing the impact of my data cleaning on this variable.
My approach to handling and cleaning the data is methodical and ensures that the analysis is based on accurate and meaningful information. 

In these steps, I continued my data cleaning efforts:
19.	& 20. Addressing 'occupation' Placeholder Values: Similar to 'workclass', I replaced "?" in the 'occupation' column with "Unknown" using df.occupation.replace("?", "Unknown"). The use of .sample(25) indicates that I also checked a random sample of 25 entries to verify the replacements.
20.	Cleaning 'native-country' Data: I applied the same placeholder replacement strategy to the 'native-country' column with df["native-country"].replace("?", "Unknown", inplace=True). This ensures consistency in handling unknown values across my dataset.
21.	Note on Replacing Multiple Values: The commented-out code suggests I considered, or were explaining, how to replace multiple different placeholder values with different replacements. This indicates a comprehensive understanding of data cleaning techniques.

My thorough cleaning of the data, particularly in addressing placeholders, sets a strong foundation for accurate and meaningful analysis. 

In the final steps of my analysis, I covered various aspects of the dataset:
23-27. Value Counts and Grouping: I examined value counts for 'relationship', 'education', and 'education-num', and explored the relationship between 'education' and 'education-num'.
28-30. Data Modification: I dropped the 'education-num' column, indicating a decision to focus on categorical representations of education.
31-37. Further Categorical Data Analysis: I analyzed 'relationship' and 'marital-status', including replacing certain values in 'relationship' with 'Unmarried'.
38-40. Correlation Analysis: I calculated and possibly visualized the correlation matrix, particularly for numerical columns.
41-45. Data Transformation and Visualization: I transformed the 'salary' column for analysis and visualized correlations using a heatmap.
46-85. Advanced Analyses: These steps involve more complex analyses, such as examining the relationship between education levels and income, exploring hours-per-week, and analyzing the data based on the native country. I have focused on understanding how different variables correlate with the income level.

Given the depth and breadth of my analysis, the report will highlight key findings, methodologies, and insights from the data, along with visualizations I've created. The report will emphasize the narrative I've woven through my analysis, focusing on how different socio-economic and demographic factors interplay to shape the income landscape.

## Findings

The heart of my analysis lies in the nuanced findings across various dimensions of the dataset:
1.	Age Dynamics: The age distribution revealed a Ing to middle-aged workforce, with a significant concentration in the 25-45 age bracket. This demographic is crucial as it represents a potentially economically active segment of the population.
2.	Workclass Insights: A dominant presence in the 'Private' sector was observed, followed by 'Self-emp-not-inc' and 'Local-gov'. This distribution is indicative of the broader labor market trends and potentially points to areas where employment policies could be directed.
3.	Educational Impact on Income:
•	A strong correlation between higher education levels (Bachelors, Masters, Doctorate) and higher income brackets (>50K) was evident.
•	This trend highlights the critical role of education as a catalyst for economic advancement.
4.	Occupational Influence:
•	Certain occupations like 'Exec-managerial' and 'Prof-specialty' were more frequently associated with higher income levels.
•	This insight could inform targeted workforce development strategies, emphasizing skill acquisition in these areas.
5.	Marital Status and Relationship Correlation:
•	Marital status, particularly 'Married-civ-spouse', showed a significant correlation with higher income levels.
•	This pattern suggests potential socio-economic stability associated with marital status, impacting earning potential.
6.	Capital Gain and Loss: Analysis of 'capital-gain' and 'capital-loss' variables indicated that individuals with higher capital gains generally fell into the higher income category, underscoring the role of investment and savings in overall income.
7.	Hours-per-week Factor:
•	A positive correlation between longer working hours and higher income was noted.
•	This finding points towards the traditional notion that increased work hours can lead to higher earnings but also raises questions about work-life balance.
8.	Race and Gender Narrative:
•	While the dataset revealed disparities in income across different races and genders, these findings call for a deeper, more nuanced understanding beyond the scope of the current analysis.
9.	Native Country Influence:
•	The native country of individuals also showed varying impacts on income levels, suggesting the influence of cultural, educational, and economic backgrounds.

## Limitations

The analysis encounters several limitations:
1.	Data Completeness: Handling of missing values may introduce biases.
2.	Non-Causality: Correlations observed do not imply causation.
3.	Scope of Analysis: Limited to the dataset's demographic and time frame.

## Recommendations

From this analysis, several key recommendations emerge:
1.	Enhancing Educational Opportunities: Given the strong correlation between education and income, policies that facilitate access to higher education and vocational training should be prioritized.
2.	Workforce Development Focused on High-Income Occupations: Skill development programs targeting occupations that are correlated with higher incomes could be beneficial.
3.	Addressing Disparities: The observed disparities across race, gender, and native country highlight the need for targeted interventions to ensure equitable economic opportunities.
4.	Work-Life Balance Policies: The relationship between longer working hours and higher income underscores the need for policies that promote a healthy work-life balance.

## Conclusion

This analysis has peeled back layers of socio-economic data, revealing complex interplays between education, occupation, marital status, and other factors in determining income. These insights not only enrich our understanding of the economic fabric but also provide actionable directions for policy and societal development.

## Analysis Notebook

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

%matplotlib inline 

plt.rcParams["figure.figsize"]=(10,6)
sns.set_style("whitegrid")
pd.set_option("display.float_format", lambda x: '%.2f'  %x)

pd.options.display.max_rows=50
pd.options.display.max_columns=100

import warnings
warnings.filterwarnings("ignore")
warnings.warn("thisnwill not show")
#Read data from file
df = pd.read_csv("adult_eda.csv")
df.head(5)
```
Try to understand what the data looks like? What are types of the features? Are there any missing values? Do I need to eliminate some features?

```
df.shape
df.info()
df.describe()
df.describe().T
df.isna().sum()
df.isna().sum()[df.isna().sum() > 0]

# Look at the value counts of columns that have object datatype and replace '?' like values with 'Unknown' word.
df.sample(10)
df.select_dtypes(include= "object")
df.select_dtypes(include= "object").describe().T
df["workclass"].value_counts()
for col in df.select_dtypes(include = "object"):
    print(col)
    print("***")
    print(df[col].value_counts())
    print("***********")

df.isin(["?"]).sum()
df.workclass.replace("?", "Unknown")
df.workclass.value_counts()

# df.workclass.replace("?", "Unknown", inplace = True)
df.workclass = df.workclass.replace("?", "Unknown")
df.workclass.value_counts()
df.occupation.replace("?", "Unknown").sample(25)
df.occupation.replace("?", "Unknown", inplace= True)
df["native-country"].replace("?", "Unknown", inplace= True)
# df.replace({"?": "Unknown", "!": "aa"})  If there is more than one we need dict format

df.relationship.value_counts()
df.relationship.value_counts(dropna=False)

# Do education and education_num columns hold similar information?
# If so drop the appropriate choice between them.
df.education.value_counts(dropna=False)
df["education-num"].value_counts(dropna=False)
df.groupby("education")["education-num"].value_counts(dropna=False)
df.drop("education-num", axis= 1)

df.head()
df.drop("education-num", axis= 1, inplace = True)

# Impute missing value in relationship column with "Unmaried".
# Also replace "Not-in-family", "Other-relative" values in this column with "Unmaried"?

df.relationship.value_counts(dropna=False)
df["marital-status"].value_counts(dropna=False)
df.groupby("relationship")["marital-status"].value_counts(dropna=False)
df.relationship.replace(["Not-in-family", "Other-relative", np.nan ], "Unmarried").sample(25)
df.relationship.replace(["Not-in-family", "Other-relative", np.nan ], "Unmarried", inplace = True)
df.relationship.value_counts()
df.isnull().sum()

# Take a look at correlation between variables and also see if there are some outliers in any of the columns.
df.corr()
df.select_dtypes("number").corr()
df.head(25)

df.salary.replace({"<=50K" : 0, ">50K" : 1})
df.salary.replace({"<=50K" : 0, ">50K" : 1}, inplace=True)
df.corr()
sns.heatmap(data=df.corr(), annot = True, cmap="viridis")
```
<img width="633" alt="image" src="https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/96ec9969-c4ba-48e1-83f0-b6e992356a24">

```
# find outlier values which extends the upper limit in both age and hours-per-week columns
# age
plt.figure(figsize=(10,6))
plt.subplot(1,2,1)
sns.boxplot(data=df.age,whis=1.5) #whis=1.5
plt.subplot(1,2,2)
sns.histplot(data=df.age,bins= 10);

```
<img width="725" alt="image" src="https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/2900e4b2-13b8-4a42-aa19-ab96a693a746">

```
df[df.age > 78]

# hours-per-week
plt.figure(figsize=(10,6))
plt.subplot(1,2,1)
sns.boxplot(data=df["hours-per-week"],whis=3)
plt.subplot(1,2,2)
sns.histplot(data=df["hours-per-week"],bins=30);

```
<img width="664" alt="image" src="https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/e87c684a-4bd1-4640-b720-824a9d739ce2">

```
df[df["hours-per-week"] > 79]

df[df["hours-per-week"] > 60][["marital-status","race"]]

# Boxplot and Histplot for all numeric features

index=0
plt.figure(figsize=(20,10))
for feature in df.select_dtypes('number').columns:
    index+=1
    plt.subplot(2,3,index)
    sns.boxplot(x=feature,data=df,whis=1.5)
```
<img width="739" alt="image" src="https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/1c4665c3-46c7-4d40-bc00-8a8930f4b2ea">

```
index=0
plt.figure(figsize=(20,40))
for feature in df.select_dtypes('number').columns:
    index+=1
    plt.subplot(6,2,index)
    sns.boxplot(x=feature,data=df,whis=3) 
    index+=1
    plt.subplot(6,2,index)
    sns.histplot(x=feature,data=df)

```
<img width="714" alt="image" src="https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/191023b9-0b8b-48f8-9f9a-4ca721877cff"> <img width="731" alt="image" src="https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/9dd59faf-aee2-411a-8e1b-1b4c2d47fc44">  <img width="724" alt="image" src="https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/60d7fef8-b5e6-4a35-9848-23aa825614bc">

```
# After looking at the outliers you can drop the rows which actually does not make any sense.
df[(df.age > 78) & (df["hours-per-week"] > 55)]
drop_index = df[(df.age > 78) & (df["hours-per-week"] > 55)].index
drop_index
df.drop(index = drop_index)
df.drop(index= drop_index, inplace=True)

# How many of each race are represented in this dataset?
sns.countplot(x = "race", data=df);

```
<img width="396" alt="image" src="https://github.com/tuerkerme/Python_based_income_analysis/assets/149696414/5676e89c-0c23-4c20-8fa6-f16479621b50">

```
#What is the average age of men/women?
df[df.sex == "Male"]["age"].mean()

df[df.sex == "Female"]["age"].mean()

df.groupby("sex")["age"].mean()

# What is the percentage of people who have a Bachelor's degree?
df[df.education == "Bachelors"]

df[df.education == "Bachelors"].shape[0]

round(df[df.education == "Bachelors"].shape[0] / len(df) * 100, 2)

# What percentage of people with advanced education (Bachelors, Masters, or Doctorate) make more than 50K?

advance_edu = df[(df.education == "Bachelors") | (df.education == "Masters") | (df.education == "Doctorate")]
advance_edu

advance_edu[advance_edu.salary == 1]

advance_edu[advance_edu.salary == 1].shape[0] / len(advance_edu) * 100

# What percentage of people without advanced education make more than 50K?
df[df.education.isin(["Bachelors", "Masters", "Doctorate"])]

not_advance_edu = df[~df.education.isin(["Bachelors", "Masters", "Doctorate"])]
not_advance_edu

not_advance_edu.salary.value_counts()
not_advance_edu.salary.value_counts(normalize=True)

not_advance_edu.salary.value_counts(normalize=True)[1] * 100

# What percentage of the people who work the minimum number of hours per week have a salary of >50K?
df["hours-per-week"].min()

df[df["hours-per-week"] == df["hours-per-week"].min()]

len(df[df["hours-per-week"] == df["hours-per-week"].min()])

df[df["hours-per-week"] == df["hours-per-week"].min()]["salary"].value_counts(normalize = True)[1] * 100

# What country has the highest percentage of people that earn >50K
df.head()

df["native-country"].nunique()

df.groupby("native-country")["salary"].count()

df[df.salary == 1].groupby("native-country")["salary"].count()

df[df.salary == 1].groupby("native-country")["salary"].count() / df.groupby("native-country")["salary"].count()

(df[df.salary == 1].groupby("native-country")[["salary"]].count() / df.groupby("native-country")[["salary"]].count())

(df[df.salary == 1].groupby("native-country")[["salary"]].count() / df.groupby("native-country")[["salary"]].count()).sort_values("salary",ascending=False)











