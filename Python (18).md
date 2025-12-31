# Python Fundamentals Study (2025-12-27)

---

## Learning Goals

- Understand the basics of Python and data manipulation with **Pandas**.
- Gain proficiency in **Pandas DataFrame** and **Series** for data analysis.
- Master techniques for cleaning, transforming, and analyzing data.
- Learn to handle data from various formats (CSV, Excel, etc.) and apply best practices in real-world data science problems.

---

## Pandas Overview

Pandas is an essential Python library for data manipulation and analysis, providing high-performance, easy-to-use data structures like **Series** and **DataFrame**.

### Import Libraries

To begin using **Pandas** and **NumPy**, we first import them:

```python
import pandas as pd
import numpy as np
```
---

## Pandas Data Types

## Series
A Series is a one-dimensional labeled array capable of holding any data type.
It's similar to a column in a spreadsheet or a single column from a Dataframe.

### Example : Creating a Series from a Dictionary
```python
dict_data = {'a': 1, 'b': 2, 'c': 3}
series_data = pd.Series(dict_data)

print(type(series_data))
print(series_data)
```
```text
<class 'pandas.core.series.Series'>
a    1
b    2
c    3
dtype: int64
```

### Creating a Series from a List
```python
list_data = ['2022-10-11', 3.14, 'ABC', 100, True]
series_data = pd.Series(list_data)

print(type(series_data))
print(series_data)
```
```text
<class 'pandas.core.series.Series'>
0     2022-10-11
1           3.14
2            ABC
3            100
4           True
dtype: object
```
---

## DataFrames
A DataFrame is a two-dimensional, size-mutablek potentially heterogeneous tablar data structure with labeled axes.
It is one of the most widely used object in Pandas

### Example : Creating a DataFrame from a Dictionary
```python
dict_data = {
    'col1': [0, 1, 2],
    'col2': [1, 4, 7],
    'col3': [1.4, 0.8, 3.9],
    'col4': ['a', 'b', 'c']
}
df = pd.DataFrame(dict_data)

print(type(df))
print(df)
```
```text
<class 'pandas.core.frame.DataFrame'>
   col1  col2  col3 col4
0     0     1   1.4    a
1     1     4   0.8    b
2     2     7   3.9    c
```
---

## Working wth Data from External Files

Pandas provides functions to easily load data from external sources, such as CSV files, into a DataFrame for analysis.

### Example : Reading a CSV File
```python
titanic_data = pd.read_csv("/content/titanic.csv")
```
This function can read data directly into Pandas from CSV files, which is especially useful in real-world applications like handling customer, financial, or sales data.

---

## Practical Applications

The knowledge of Pandas and NumPy is crucial in fields like data science, machine liearning, and business analytics.

By using these tools, you can effectively manage large datasets, clean messy data, and derive actionable insights from structured data.

### Example Projects
Customer Segmentation )

Analyzing customer data to segment them based on purchasing behavior and demographics.

Sales Forecasting )

Using historical sales data to predict future sales trends.

---

## Key Achievements

- Gained hands-on experience in creating, manipulating, and analyzing Pandas DataFrames and Series.
- Worked with real-world datasets and applied data cleaning and transformation techniques.
- Developed practical skills to read data from various file formats (CSV, Excel, etc.) and perform complex data manipulations.

---

## Pandas Data Inspection

When working with data in **Pandas**, it's important to quickly inspect the contents, dimensions, and general structure of the dataset. Here are a few useful methods:

## Inspecting Columns

To view the columns of a **DataFrame**, use the `columns` attribute. This is helpful to get an overview of the available data.

```python
print(titanic.columns)
```
```text
Index(['PassengerId', 'Survived', 'Pclass', 'Name', 'Sex', 'Age', 'SibSp',
       'Parch', 'Ticket', 'Fare', 'Cabin', 'Embarked'],
      dtype='object')
```

## Viewing the First Few Rows

To preview the first few rows of the dataset, use the head() method.

This is useful for getting a quick sense of the data's structure and content.

```python
titanic.head()
```
```text
   PassengerId  Survived  Pclass                                               Name     Sex   Age  SibSp  Parch            Ticket     Fare Cabin Embarked
0            1         0      3                            Braund, Mr. Owen Harris    male  22.0      1      0         A/5 21171   7.25   NaN        S
1            2         1      1  Cumings, Mrs. John Bradley (Florence Briggs Thayer) female  38.0      1      0          PC 17599  71.2833 C85        C
2            3         1      3                             Heikkinen, Miss. Laina    female  26.0      0      0     STON/O2. 3101282   7.925  NaN        S
3            4         1      1  Futrelle, Mrs. Jacques Heath (Lily May Peel)   female  35.0      1      0            113803  53.1  C123      S
4            5         0      3                           Allen, Mr. William Henry    male  35.0      0      0           373450   8.05    NaN        S
```

## Viewing the Last Few Rows

To view the last few rows of the datast, use the tail() method. 

This is helpful for checking how the data ends or for inspecting incomplete data.

```python
titanic.tail()
```
```text
   PassengerId  Survived  Pclass  ...    Fare Cabin Embarked
886          887         0      2   ...    13.0   NaN        S
887          888         1      1   ...   30.0   B42        S
888          889         0      3   ...    23.45  NaN        S
889          890         1      1   ...    30.0   C93        S
890          891         0      3   ...    7.75    NaN       S
```

## Data Dimensions

To check the number of rows and columns in a DataFrame, use the shape attribute.

It returns a tuple containing the number of rows and columns

```python
titanic.shape
```
```text
(891, 12)
```
This means the dataset contains 891 rows and 12 columns.

## General Data Information

To get a concise summary of the DataFrame, including data types and non-null values, use the info() method.

This is essential for understanding the overall structure of the dataset and identifying any missing or non-null data.

```python
titanic.info()
```
```text
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 891 entries, 0 to 890
Data columns (total 12 columns):
 #   Column       Non-Null Count  Dtype  
---  ------       --------------  -----  
 0   PassengerId  891 non-null    int64  
 1   Survived     891 non-null    int64  
 2   Pclass       891 non-null    int64  
 3   Name         891 non-null    object 
 4   Sex          891 non-null    object 
 5   Age          714 non-null    float64
 6   SibSp        891 non-null    int64  
 7   Parch        891 non-null    int64  
 8   Ticket       891 non-null    object 
 9   Fare         891 non-null    float64
 10  Cabin        204 non-null    object 
 11  Embarked     891 non-null    object 
dtypes: float64(2), int64(5), object(5)
memory usage: 83.7+ KB
```
These methods are crucial for performing quick exploratory data analysis (EDA) on a dataset.

By inspecting the data's shape, columns, and the first/last rows, you can efficiently understand its structure and identify potential issues, such as missing data or inconsistencies.

---

## Selecting Data in Pandas

One of the most common tasks in data analysis is selecting specific columns or rows. **Pandas** provides flexible ways to extract and manipulate data based on your needs.

## Selecting a Single Column

You can select a single column by referencing the column name. In this example, we're extracting the **Name** column from the Titanic dataset.

```python
names = titanic['Name']
print(names.head())
```
```text
0                             Braund, Mr. Owen Harris
1    Cumings, Mrs. John Bradley (Florence Briggs Thayer)
2                             Heikkinen, Miss. Laina
3          Futrelle, Mrs. Jacques Heath (Lily May Peel)
4                          Allen, Mr. William Henry
dtype: object
```
In this case, we used the head() method to view the first five rows of the Name column.

```python
print(type(names))
print(names.head())
```
```text
<class 'pandas.core.series.Series'>
0                             Braund, Mr. Owen Harris
1    Cumings, Mrs. John Bradley (Florence Briggs Thayer)
2                             Heikkinen, Miss. Laina
3          Futrelle, Mrs. Jacques Heath (Lily May Peel)
4                          Allen, Mr. William Henry
dtype: object
```
## Selecting Multiple Columns

To select multiple columns, you can pass a list of column names.
In this case, we are selecting the Sex and Age columns.

```python
passenger = titanic[['Sex', 'Age']]
passenger.head()
```
```text
     Sex   Age
0    male  22.0
1  female  38.0
2  female  26.0
3  female  35.0
4    male  35.0
```

## Checing Data Types and Structure

You can also check the data type of the selected data using the type() function and view its structure with head() or info().

```python
print(type(passenger))
print(passenger.head())
```
```text
<class 'pandas.core.frame.DataFrame'>
   Sex   Age
0  male  22.0
1 female 38.0
2 female 26.0
3 female 35.0
4 male 35.0
```

These operations are fundamental when working with datasets in Pandas.

Being able to select specific rows or columns allows you to clean and analyze data more effectively.

---

## Data Filtering in Pandas

**Pandas** offers powerful data filtering capabilities, which allow you to select rows based on conditions, like checking if certain values in a column meet specific criteria. This is commonly used in data cleaning and exploration.

### Filtering Rows Based on Condition

To filter rows based on a condition, you can apply a boolean condition to a **DataFrame** column.

For example, to filter the **Age** column and find passengers older than 35, you can do the following:

```python
print(passenger["Age"] > 35)
```
```text
0      False
1       True
2      False
3      False
4      False
        ...
890    False
Name: Age, Length: 891, dtype: bool
```

This operation generates a boolean Series where each row is marked as True if the condition is met (Age > 35) or False otherwise.

---

## Boolean Filtering

To filter the dataset using the boolean condition, you can apply the condition to the DataFrame directly

```python
above35 = passenger[passenger["Age"] > 35]
above35.head()
```
```text
     Sex   Age
1  female  38.0
6    male  54.0
11 female  58.0
13  male  39.0
14 female  55.0
```

This code will return only the rows where the Age is greater than 35.

## Filtering Multiple Conditions

You can also filter rows using multiple conditions by chaining conditions together.

For example, filtering by Age greater than 35 and Sex as male

```python
above35_male = passenger[(passenger["Age"] > 35) & (passenger["Sex"] == "male")]
above35_male.head()
```
This will return a subset of the data where both conditions are met.

### Example - Titanic Data, Filtering by Age and Other Criteria

Here's an example of how to filter the Titanic dataset for passengers who survived and are older than 35

```python
survived_above35 = titanic[(titanic["Survived"] == 1) & (titanic["Age"] > 35)]
survived_above35.head()
```

This allows you to extract valuable insights, such as finding the survivors of a certain age group.

These filtering techniques are fundamental for performing exploratory data analysis (EDA) and can help you focus on the data that matters for your analysis.

---

## Data Selection and Filtering in Pandas

### Using `.isin()` for Filtering

The `.isin()` method is used to filter data by checking if the values in a column belong to a specific list or set of values. It returns a boolean **Series** indicating whether each element is present in the list.

For example, to filter the **Pclass** column in the Titanic dataset for values that are either 1 or 2:

```python
print(titanic["Pclass"].isin([1, 2]))
```
```text
0      False
1       True
2       True
3       True
4      False
        ...
889     True
890    False
Name: Pclass, Length: 891, dtype: bool
```

This returns a boolean Series with True for rows where Pclass is 1 or 2, and False otherwise.

## Boolean Indexing with .isin()

You can use this boolean Series to filter the DataFrame.

For example, to get all passengers with Pclass 1 or 2:

```python
pclass_1_2 = titanic[titanic["Pclass"].isin([1, 2])]
pclass_1_2.head()
```

This will return a filtered DataFrame with only rows where Pclass is 1 or 2.

## Filtering Data by Range

You can also filter data based on a range of values using NumPy's np.arrange() function or logical conditions.

### Example : Filtering Ages between 20 and 40

To filter the Titanic dataset for passengers whose Age is between 20 and 40

```python
age2040 = passenger[passenger["Age"].between(20, 40)]
age2040.head()
```
```text
     Sex   Age
1  female  38.0
6    male  54.0
11 female  58.0
13  male  39.0
14 female  55.0
```
This filters the passengers whose Age is between 20 and 40.

### Example: Filtering with np.arange()

You can also use NumPy's np.arange() to define a range of values. 
For example, to select passengers with ages between 20 and 40

```python
age2040 = passenger[passenger["Age"].isin(np.arange(20, 41))]
age2040.head()
```

This achieves the same result as using .between() but with the flexibility of NumPy's array-like operations.

These filtering techniques are essential for refining your dataset to focus on specific subsets of data.

Whether you use .isin(), logical conditions, or range functions like np.arange(), these methods help you extract meaningful information for further analysis.

---

## Example: Extracting Rows with Missing Data

To filter and extract rows where Age is missing (i.e., NaN), you can do

```python
ages = passenger[passenger["Age"].isna()]
ages.head(2)
```
```text
    Sex  Age
5  male  NaN
17 male  NaN
```
This gives you the rows where Age is NaN.

---

## Handling Missing Data
Once you've identified the missing data, there are several ways to handle it, such as filling missing values with a default value, forward filling, or removing rows with missing data.

### Example : Removing Rows with Missing Data

To remove rows with missing data in a specific column, you can use the .dropna() method

```python
cleaned_data = passenger.dropna(subset=["Age"])
cleaned_data.head()
```

This will remove rows where Age is missing

## Example: Filling Missing Values with a Default Value

You can also fill missing values with a default value (such as the mean or median) using the .fillna() method

```python
passenger["Age"].fillna(passenger["Age"].mean(), inplace=True)
```

This replaces missing Age values with the mean of the existing values

Dealing with missing data is a crucial step in data preprocessing.

Pandas provides various methods for detecting, filtering, and filling missing data, allowing you to clean and prepare datasets for analysis effectively.

---

## Key Learnings

- Gained proficiency in **Pandas** library, focusing on **Series** and **DataFrame** structures for data manipulation.
- Learned how to filter, select, and clean data using various Pandas functions such as `.isin()`, `.isna()`, `.fillna()`, and `.dropna()`.
- Improved data handling skills and strengthened data analysis capabilities.

---

## Reflections

- Previously, I focused on **NumPy**, but this time I expanded my knowledge to include the **Pandas** library, which is a powerful tool for data analysis.
- Realized how important it is to master data manipulation and analysis to solve real-world problems using data.
- Looking forward to further exploring data analysis techniques and improving my coding skills!

---

## Resources

- **Handbook_Python_Final.pdf** – A comprehensive guide for Python programming.
- **Pandas Documentation** – The official guide to mastering Pandas for data analysis and manipulation.
- **Kaggle Competitions** – Actively participating in Kaggle to enhance my skills with real-world data challenges.

---

## Author

**RYU YEJIN**  

Aspiring Data Analyst  

Documenting the journey from Python fundamentals to practical data analysis projects  

📧 Email: datacorio00@gmail.com

Blog : https://blog.naver.com/datacori/224117579062

