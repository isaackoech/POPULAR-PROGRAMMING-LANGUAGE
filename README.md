# POPULAR-PROGRAMMING-LANGUAGE
## Problem Statement
This project aims at evaluating the popular programming among the developers that helps any interested person in knowing the language that they can focus on. It also ensures that any new developer will be able to align their goals to the popular programming language that would help them do collaborations in future. That can only be achieved if the righful programming language is picked.

### Software Used
- Jupyter Notebook

### Installation
```python
- pip install pandas
- pip install numpy
- pip install matplotlib
```
### Steps Followed
- Step 1: Load Anaconda prompt
- Step 2: Open Jupyter homepage
- Step 3: Upload the csv file named 'data.csv' into Jupyter Notebook using 'Upload' tab
- Step 4: Creating a new notebook using 'New' tab on Jupyter Notebook homepage and named it 'POPULAR PROGRAMMING LANGUAGE'
- Step 5: importing python libraries;
```python
import csv
import pandas as pd
import numpy as np
from collections import Counter
from matplotlib import pyplot as plt
```
- Step 6: Creating a dataframe from csv file using pandas:
```python
  df = pd.read_csv('data.csv')
```
- Step 7: Creating a variable for counting the programming languages:
  ```python
  language_counter = Counter()
  ```
- Step 8: Cleaning the data on 'LanguagesWorkedWith' column using .split() function and making every language appear on each row using .explode() function. Then using Counter() to count the number that each unique programming language would appear
```python
df['LanguagesWorkedWith'] = df['LanguagesWorkedWith'].str.split(';')
df = df.explode('LanguagesWorkedWith')

df = Counter(df['LanguagesWorkedWith'])
print(df)
```
- Step 9: Sorting the 15 popular languages using .most_common() function
  ```python
  df.most_common(15)
  ```
  - Step 10: Preparing variables for ploting a bar graph. Languages and Popularity variables which are empty lists, are created then using for loop, the variables are filled using .append() functions. The variables are rearranged using .reverse() functions so that the largest value would appear top. Print() function is used to check the content of the two variables.
```python
Languages = []
Popularity = []

for item in df.most_common(15):
    Languages.append(item[0])
    Popularity.append(item[1])
Languages.reverse()
Popularity.reverse()
print(Languages)
print(Popularity)
```
  <img width="1469" height="319" alt="Image" src="https://github.com/user-attachments/assets/524fc4a2-eeee-4dc6-a2c3-a32cdbb32d1e" />
- Step 11: Plotting the bar graph using matplotlib as plt.
```python
plt.barh(Languages, Popularity)
plt.title('15 Most Popular Languages in Development')
plt.ylabel('Programming Languages')
plt.xlabel('Number of People Using')


plt.tight_layout()
plt.show()
```
### The Display of the Bar Graph showing 15 Most Popular Progranmming Languages
  <img width="1026" height="610" alt="Screenshot 2026-02-06 221549" src="https://github.com/user-attachments/assets/352419d6-c88a-4c7b-9283-843265b8fb5c" />
