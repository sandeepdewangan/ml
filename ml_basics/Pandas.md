# Pandas

# Pandas Series


```python
import numpy as np
import pandas as pd

labels = ['a', 'b', 'c']
mylist = [10, 20, 30]
arr = np.array([10, 20, 30])
d = {'a': 10, 'b': 20, 'c': 30}
```


```python
# Add data, with default index
pd.Series(data=mylist)
```




    0    10
    1    20
    2    30
    dtype: int64




```python
# Add data with labels
pd.Series(data=mylist, index=labels)
```




    a    10
    b    20
    c    30
    dtype: int64




```python
# Using dictionary
pd.Series(d)
```




    a    10
    b    20
    c    30
    dtype: int64




```python
salesQ1 = pd.Series(data=[100, 200, 150], index=["Pakisthan", "India", "Nepal"])
```


```python
salesQ1
```




    Pakisthan    100
    India        200
    Nepal        150
    dtype: int64




```python
salesQ1['India']  # or by index `salesQ1[1]`
```




    200




```python
# Missing values

salesQ1 = pd.Series(data=[100, 200, 150], index=["Pakisthan", "India", "Nepal"])
salesQ2 = pd.Series(data=[50, 200, 600], index=["Pakisthan", "India", "America"])
```


```python
salesQ1 + salesQ2
```




    America        NaN
    India        400.0
    Nepal          NaN
    Pakisthan    150.0
    dtype: float64



# Data Frame
Data frame is simply multiple pandas series that share same index. 
Data frame is like a spreadsheet.


```python
cols = ['W', 'X', 'Y', 'Z']
index = ['A', 'B', 'C', 'D', 'E']

from numpy.random import randint

np.random.seed(42)
data = randint(-100, 100, (5,4))
data
```




    array([[  2,  79,  -8, -86],
           [  6, -29,  88, -80],
           [  2,  21, -26, -13],
           [ 16,  -1,   3,  51],
           [ 30,  49, -48, -99]])




```python
df = pd.DataFrame(data, index, cols)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>79</td>
      <td>-8</td>
      <td>-86</td>
    </tr>
    <tr>
      <th>B</th>
      <td>6</td>
      <td>-29</td>
      <td>88</td>
      <td>-80</td>
    </tr>
    <tr>
      <th>C</th>
      <td>2</td>
      <td>21</td>
      <td>-26</td>
      <td>-13</td>
    </tr>
    <tr>
      <th>D</th>
      <td>16</td>
      <td>-1</td>
      <td>3</td>
      <td>51</td>
    </tr>
    <tr>
      <th>E</th>
      <td>30</td>
      <td>49</td>
      <td>-48</td>
      <td>-99</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Index Selection
# Grap Cols
df['W']
```




    A     2
    B     6
    C     2
    D    16
    E    30
    Name: W, dtype: int32




```python
# Grap multiple cols
# Pass through list []
df[['W', 'X']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>79</td>
    </tr>
    <tr>
      <th>B</th>
      <td>6</td>
      <td>-29</td>
    </tr>
    <tr>
      <th>C</th>
      <td>2</td>
      <td>21</td>
    </tr>
    <tr>
      <th>D</th>
      <td>16</td>
      <td>-1</td>
    </tr>
    <tr>
      <th>E</th>
      <td>30</td>
      <td>49</td>
    </tr>
  </tbody>
</table>
</div>




```python
## Add a col

df['New'] = df['W'] + df['Y']
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
      <th>New</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>79</td>
      <td>-8</td>
      <td>-86</td>
      <td>-6</td>
    </tr>
    <tr>
      <th>B</th>
      <td>6</td>
      <td>-29</td>
      <td>88</td>
      <td>-80</td>
      <td>94</td>
    </tr>
    <tr>
      <th>C</th>
      <td>2</td>
      <td>21</td>
      <td>-26</td>
      <td>-13</td>
      <td>-24</td>
    </tr>
    <tr>
      <th>D</th>
      <td>16</td>
      <td>-1</td>
      <td>3</td>
      <td>51</td>
      <td>19</td>
    </tr>
    <tr>
      <th>E</th>
      <td>30</td>
      <td>49</td>
      <td>-48</td>
      <td>-99</td>
      <td>-18</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Remove a col
df = df.drop('New', axis=1)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>79</td>
      <td>-8</td>
      <td>-86</td>
    </tr>
    <tr>
      <th>B</th>
      <td>6</td>
      <td>-29</td>
      <td>88</td>
      <td>-80</td>
    </tr>
    <tr>
      <th>C</th>
      <td>2</td>
      <td>21</td>
      <td>-26</td>
      <td>-13</td>
    </tr>
    <tr>
      <th>D</th>
      <td>16</td>
      <td>-1</td>
      <td>3</td>
      <td>51</td>
    </tr>
    <tr>
      <th>E</th>
      <td>30</td>
      <td>49</td>
      <td>-48</td>
      <td>-99</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Grabing a row
df.loc['A']
```




    W     2
    X    79
    Y    -8
    Z   -86
    Name: A, dtype: int32




```python
# Grabing multiple row
df.loc[['A','B']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>79</td>
      <td>-8</td>
      <td>-86</td>
    </tr>
    <tr>
      <th>B</th>
      <td>6</td>
      <td>-29</td>
      <td>88</td>
      <td>-80</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Grab by index loc - first row
df.iloc[0]
```




    W     2
    X    79
    Y    -8
    Z   -86
    Name: A, dtype: int32




```python
# Play with iloc.
df.iloc[0:2, 0:1]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
    </tr>
    <tr>
      <th>B</th>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Grab row A and C, Also cols W and Y
df.loc[['A','C'],['W','Y']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>-8</td>
    </tr>
    <tr>
      <th>C</th>
      <td>2</td>
      <td>-26</td>
    </tr>
  </tbody>
</table>
</div>



# Conditional Operation


```python
# Show only data with positive numberie. > 0
df[df > 0]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>79.0</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>B</th>
      <td>6</td>
      <td>NaN</td>
      <td>88.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>C</th>
      <td>2</td>
      <td>21.0</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>D</th>
      <td>16</td>
      <td>NaN</td>
      <td>3.0</td>
      <td>51.0</td>
    </tr>
    <tr>
      <th>E</th>
      <td>30</td>
      <td>49.0</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Extract data where col X > 0
df[df['X'] > 0]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>79</td>
      <td>-8</td>
      <td>-86</td>
    </tr>
    <tr>
      <th>C</th>
      <td>2</td>
      <td>21</td>
      <td>-26</td>
      <td>-13</td>
    </tr>
    <tr>
      <th>E</th>
      <td>30</td>
      <td>49</td>
      <td>-48</td>
      <td>-99</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Two conditions
df[(df['W'] > 0) & (df['Y'] > 1)]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>B</th>
      <td>6</td>
      <td>-29</td>
      <td>88</td>
      <td>-80</td>
    </tr>
    <tr>
      <th>D</th>
      <td>16</td>
      <td>-1</td>
      <td>3</td>
      <td>51</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Get index value
df.reset_index()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>2</td>
      <td>79</td>
      <td>-8</td>
      <td>-86</td>
    </tr>
    <tr>
      <th>1</th>
      <td>B</td>
      <td>6</td>
      <td>-29</td>
      <td>88</td>
      <td>-80</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>2</td>
      <td>21</td>
      <td>-26</td>
      <td>-13</td>
    </tr>
    <tr>
      <th>3</th>
      <td>D</td>
      <td>16</td>
      <td>-1</td>
      <td>3</td>
      <td>51</td>
    </tr>
    <tr>
      <th>4</th>
      <td>E</td>
      <td>30</td>
      <td>49</td>
      <td>-48</td>
      <td>-99</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Creating new index
new_index = ['CG', 'MH', 'OR', 'MP', 'AP']
df['States'] = new_index
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
      <th>States</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>2</td>
      <td>79</td>
      <td>-8</td>
      <td>-86</td>
      <td>CG</td>
    </tr>
    <tr>
      <th>B</th>
      <td>6</td>
      <td>-29</td>
      <td>88</td>
      <td>-80</td>
      <td>MH</td>
    </tr>
    <tr>
      <th>C</th>
      <td>2</td>
      <td>21</td>
      <td>-26</td>
      <td>-13</td>
      <td>OR</td>
    </tr>
    <tr>
      <th>D</th>
      <td>16</td>
      <td>-1</td>
      <td>3</td>
      <td>51</td>
      <td>MP</td>
    </tr>
    <tr>
      <th>E</th>
      <td>30</td>
      <td>49</td>
      <td>-48</td>
      <td>-99</td>
      <td>AP</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Make states col the index instead of A,B,C...
df = df.set_index('States')
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
    <tr>
      <th>States</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>CG</th>
      <td>2</td>
      <td>79</td>
      <td>-8</td>
      <td>-86</td>
    </tr>
    <tr>
      <th>MH</th>
      <td>6</td>
      <td>-29</td>
      <td>88</td>
      <td>-80</td>
    </tr>
    <tr>
      <th>OR</th>
      <td>2</td>
      <td>21</td>
      <td>-26</td>
      <td>-13</td>
    </tr>
    <tr>
      <th>MP</th>
      <td>16</td>
      <td>-1</td>
      <td>3</td>
      <td>51</td>
    </tr>
    <tr>
      <th>AP</th>
      <td>30</td>
      <td>49</td>
      <td>-48</td>
      <td>-99</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Get cols name
df.columns
```




    Index(['W', 'X', 'Y', 'Z'], dtype='object')




```python
# Describe the data frame
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>W</th>
      <th>X</th>
      <th>Y</th>
      <th>Z</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>5.00000</td>
      <td>5.000000</td>
      <td>5.000000</td>
      <td>5.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>11.20000</td>
      <td>23.800000</td>
      <td>1.800000</td>
      <td>-45.400000</td>
    </tr>
    <tr>
      <th>std</th>
      <td>11.96662</td>
      <td>42.109381</td>
      <td>51.915316</td>
      <td>63.366395</td>
    </tr>
    <tr>
      <th>min</th>
      <td>2.00000</td>
      <td>-29.000000</td>
      <td>-48.000000</td>
      <td>-99.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2.00000</td>
      <td>-1.000000</td>
      <td>-26.000000</td>
      <td>-86.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>6.00000</td>
      <td>21.000000</td>
      <td>-8.000000</td>
      <td>-80.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>16.00000</td>
      <td>49.000000</td>
      <td>3.000000</td>
      <td>-13.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>30.00000</td>
      <td>79.000000</td>
      <td>88.000000</td>
      <td>51.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Index: 5 entries, CG to AP
    Data columns (total 4 columns):
     #   Column  Non-Null Count  Dtype
    ---  ------  --------------  -----
     0   W       5 non-null      int32
     1   X       5 non-null      int32
     2   Y       5 non-null      int32
     3   Z       5 non-null      int32
    dtypes: int32(4)
    memory usage: 120.0+ bytes
    


```python
df.dtypes
```




    W    int32
    X    int32
    Y    int32
    Z    int32
    dtype: object



# Missing Values


```python
# Leave missing data - NaN or missing
# For categorical data, it is a better choice
```


```python
# Remove missing data
# Guess the data how much is missing, if small percentage it is ok.
```


```python
# Fill in the missing data
# Mode, Median, Mean
# or based on cols.

df = pd.DataFrame({'A': [1, 2, np.nan, 4], 
                   'B': [5, np.nan, np.nan, 8], 
                   'C': [10, 20, 30, 40], 
                  })
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>5.0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2.0</td>
      <td>NaN</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>30</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>8.0</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Dropping Missing Values
# removes rows
df.dropna()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>5.0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>8.0</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>




```python
# drop cols
df.dropna(axis=1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>30</td>
    </tr>
    <tr>
      <th>3</th>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>




```python
# drop based on the threshold (count) - Require that many non-NA values.
df.dropna(axis=1, thresh=3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2.0</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>30</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Fill in the missing data
df.fillna(value=0)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>5.0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2.0</td>
      <td>0.0</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>30</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>8.0</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Filling only specific cols
df['A'] = df['A'].fillna(value=0)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>5.0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2.0</td>
      <td>NaN</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.0</td>
      <td>NaN</td>
      <td>30</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>8.0</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Filling value with mean
df['B'].fillna(value=df['B'].mean())
```




    0    5.0
    1    6.5
    2    6.5
    3    8.0
    Name: B, dtype: float64




```python
# Filling value with mean - entire file bases on that cols. - col basis
df.fillna(df.mean())
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>5.0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2.0</td>
      <td>6.5</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.0</td>
      <td>6.5</td>
      <td>30</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>8.0</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
</div>



# Group by Operations
Often referred to as Split-Apply-Combine
Split data into multiple.
Apply any aggregation method. (sum, min, max, mean)


```python
df = pd.read_csv('Universities.csv')
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Sector</th>
      <th>University</th>
      <th>Year</th>
      <th>Completions</th>
      <th>Geography</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Private for-profit, 2-year</td>
      <td>Pima Medical Institute-Las Vegas</td>
      <td>2016</td>
      <td>591</td>
      <td>Nevada</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Private for-profit, less-than 2-year</td>
      <td>Healthcare Preparatory Institute</td>
      <td>2016</td>
      <td>28</td>
      <td>Nevada</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Private for-profit, less-than 2-year</td>
      <td>Milan Institute-Las Vegas</td>
      <td>2016</td>
      <td>408</td>
      <td>Nevada</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Private for-profit, less-than 2-year</td>
      <td>Utah College of Massage Therapy-Vegas</td>
      <td>2016</td>
      <td>240</td>
      <td>Nevada</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Public, 4-year or above</td>
      <td>Western Nevada College</td>
      <td>2016</td>
      <td>960</td>
      <td>Nevada</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby('Year').sum().sort_index(ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Completions</th>
    </tr>
    <tr>
      <th>Year</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2016</th>
      <td>26224</td>
    </tr>
    <tr>
      <th>2015</th>
      <td>26279</td>
    </tr>
    <tr>
      <th>2014</th>
      <td>24730</td>
    </tr>
    <tr>
      <th>2013</th>
      <td>21046</td>
    </tr>
    <tr>
      <th>2012</th>
      <td>20333</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Multiple col group by
df.groupby(['Year', 'Sector']).sum()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Completions</th>
    </tr>
    <tr>
      <th>Year</th>
      <th>Sector</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="7" valign="top">2012</th>
      <th>Private for-profit, 2-year</th>
      <td>3072</td>
    </tr>
    <tr>
      <th>Private for-profit, 4-year or above</th>
      <td>632</td>
    </tr>
    <tr>
      <th>Private for-profit, less-than 2-year</th>
      <td>1327</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 2-year</th>
      <td>665</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 4-year or above</th>
      <td>1059</td>
    </tr>
    <tr>
      <th>Public, 2-year</th>
      <td>1170</td>
    </tr>
    <tr>
      <th>Public, 4-year or above</th>
      <td>12408</td>
    </tr>
    <tr>
      <th rowspan="7" valign="top">2013</th>
      <th>Private for-profit, 2-year</th>
      <td>3053</td>
    </tr>
    <tr>
      <th>Private for-profit, 4-year or above</th>
      <td>775</td>
    </tr>
    <tr>
      <th>Private for-profit, less-than 2-year</th>
      <td>1281</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 2-year</th>
      <td>471</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 4-year or above</th>
      <td>1016</td>
    </tr>
    <tr>
      <th>Public, 2-year</th>
      <td>1633</td>
    </tr>
    <tr>
      <th>Public, 4-year or above</th>
      <td>12817</td>
    </tr>
    <tr>
      <th rowspan="7" valign="top">2014</th>
      <th>Private for-profit, 2-year</th>
      <td>2957</td>
    </tr>
    <tr>
      <th>Private for-profit, 4-year or above</th>
      <td>1506</td>
    </tr>
    <tr>
      <th>Private for-profit, less-than 2-year</th>
      <td>1328</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 2-year</th>
      <td>449</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 4-year or above</th>
      <td>1042</td>
    </tr>
    <tr>
      <th>Public, 2-year</th>
      <td>2286</td>
    </tr>
    <tr>
      <th>Public, 4-year or above</th>
      <td>15162</td>
    </tr>
    <tr>
      <th rowspan="7" valign="top">2015</th>
      <th>Private for-profit, 2-year</th>
      <td>3280</td>
    </tr>
    <tr>
      <th>Private for-profit, 4-year or above</th>
      <td>1306</td>
    </tr>
    <tr>
      <th>Private for-profit, less-than 2-year</th>
      <td>1629</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 2-year</th>
      <td>425</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 4-year or above</th>
      <td>1228</td>
    </tr>
    <tr>
      <th>Public, 2-year</th>
      <td>2355</td>
    </tr>
    <tr>
      <th>Public, 4-year or above</th>
      <td>16056</td>
    </tr>
    <tr>
      <th rowspan="7" valign="top">2016</th>
      <th>Private for-profit, 2-year</th>
      <td>3286</td>
    </tr>
    <tr>
      <th>Private for-profit, 4-year or above</th>
      <td>748</td>
    </tr>
    <tr>
      <th>Private for-profit, less-than 2-year</th>
      <td>1552</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 2-year</th>
      <td>322</td>
    </tr>
    <tr>
      <th>Private not-for-profit, 4-year or above</th>
      <td>1208</td>
    </tr>
    <tr>
      <th>Public, 2-year</th>
      <td>2431</td>
    </tr>
    <tr>
      <th>Public, 4-year or above</th>
      <td>16677</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby('Year').describe().transpose()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>2012</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="8" valign="top">Completions</th>
      <th>count</th>
      <td>38.000000</td>
      <td>40.000000</td>
      <td>42.000000</td>
      <td>44.000000</td>
      <td>43.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>535.078947</td>
      <td>526.150000</td>
      <td>588.809524</td>
      <td>597.250000</td>
      <td>609.860465</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1036.433239</td>
      <td>1040.474782</td>
      <td>1150.355857</td>
      <td>1183.371791</td>
      <td>1235.952796</td>
    </tr>
    <tr>
      <th>min</th>
      <td>13.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>114.250000</td>
      <td>98.500000</td>
      <td>104.500000</td>
      <td>87.750000</td>
      <td>90.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>229.500000</td>
      <td>189.000000</td>
      <td>203.500000</td>
      <td>191.000000</td>
      <td>208.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>420.500000</td>
      <td>413.000000</td>
      <td>371.750000</td>
      <td>405.750000</td>
      <td>414.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>5388.000000</td>
      <td>5278.000000</td>
      <td>5093.000000</td>
      <td>5335.000000</td>
      <td>5367.000000</td>
    </tr>
  </tbody>
</table>
</div>



# Pandas Operations


```python
df_one = pd.DataFrame({
        'k1': ['A', 'A', 'B', 'B', 'C', 'C'],
        'col1': [100, 200, 300, 300, 400, 500],
        'col2': ['NY', 'CA', 'WA', 'WA', 'AK', 'NV']
})

df_one
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>k1</th>
      <th>col1</th>
      <th>col2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>100</td>
      <td>NY</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A</td>
      <td>200</td>
      <td>CA</td>
    </tr>
    <tr>
      <th>2</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
    </tr>
    <tr>
      <th>4</th>
      <td>C</td>
      <td>400</td>
      <td>AK</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>500</td>
      <td>NV</td>
    </tr>
  </tbody>
</table>
</div>




```python
# How many unique values
df_one['k1'].unique()
```




    array(['A', 'B', 'C'], dtype=object)




```python
df_one['k1'].nunique()
```




    3




```python
df_one['col2'].value_counts()
```




    WA    2
    NY    1
    AK    1
    NV    1
    CA    1
    Name: col2, dtype: int64




```python
# Drop duplicates
df_one.drop_duplicates()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>k1</th>
      <th>col1</th>
      <th>col2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>100</td>
      <td>NY</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A</td>
      <td>200</td>
      <td>CA</td>
    </tr>
    <tr>
      <th>2</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
    </tr>
    <tr>
      <th>4</th>
      <td>C</td>
      <td>400</td>
      <td>AK</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>500</td>
      <td>NV</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Custom function for applying to every row.
def grab_first_char(state):
    return state[0]

df_one['first_letter'] = df_one['col2'].apply(grab_first_char)
df_one
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>k1</th>
      <th>col1</th>
      <th>col2</th>
      <th>first_letter</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>100</td>
      <td>NY</td>
      <td>N</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A</td>
      <td>200</td>
      <td>CA</td>
      <td>C</td>
    </tr>
    <tr>
      <th>2</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
      <td>W</td>
    </tr>
    <tr>
      <th>3</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
      <td>W</td>
    </tr>
    <tr>
      <th>4</th>
      <td>C</td>
      <td>400</td>
      <td>AK</td>
      <td>A</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>500</td>
      <td>NV</td>
      <td>N</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Mapping
df_one['k1']
```




    0    A
    1    A
    2    B
    3    B
    4    C
    5    C
    Name: k1, dtype: object




```python
my_map = {'A': 1, 'B': 2, 'C': 3}
df_one['num'] = df_one['k1'].map(my_map)
df_one
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>k1</th>
      <th>col1</th>
      <th>col2</th>
      <th>first_letter</th>
      <th>num</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>100</td>
      <td>NY</td>
      <td>N</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A</td>
      <td>200</td>
      <td>CA</td>
      <td>C</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
      <td>W</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
      <td>W</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>C</td>
      <td>400</td>
      <td>AK</td>
      <td>A</td>
      <td>3</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>500</td>
      <td>NV</td>
      <td>N</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Get min, max location
df_one['col1'].idxmax()
```




    5




```python
# Sorting
df_one.sort_values('col1')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>k1</th>
      <th>col1</th>
      <th>col2</th>
      <th>first_letter</th>
      <th>num</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>100</td>
      <td>NY</td>
      <td>N</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A</td>
      <td>200</td>
      <td>CA</td>
      <td>C</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
      <td>W</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
      <td>W</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>C</td>
      <td>400</td>
      <td>AK</td>
      <td>A</td>
      <td>3</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>500</td>
      <td>NV</td>
      <td>N</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>




```python
# ---- Data Set -------
features = pd.DataFrame({'A': [100, 200, 300, 400, 500],
                         'B': [12, 13, 14, 15, 16]
                        })
predictions = pd.DataFrame({'pred': [0, 1, 1, 0, 1]})
```


```python
features
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>100</td>
      <td>12</td>
    </tr>
    <tr>
      <th>1</th>
      <td>200</td>
      <td>13</td>
    </tr>
    <tr>
      <th>2</th>
      <td>300</td>
      <td>14</td>
    </tr>
    <tr>
      <th>3</th>
      <td>400</td>
      <td>15</td>
    </tr>
    <tr>
      <th>4</th>
      <td>500</td>
      <td>16</td>
    </tr>
  </tbody>
</table>
</div>




```python
predictions
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>pred</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Joining Col wise
pd.concat([features, predictions], axis=1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>pred</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>100</td>
      <td>12</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>200</td>
      <td>13</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>300</td>
      <td>14</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>400</td>
      <td>15</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>500</td>
      <td>16</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_one
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>k1</th>
      <th>col1</th>
      <th>col2</th>
      <th>first_letter</th>
      <th>num</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>100</td>
      <td>NY</td>
      <td>N</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A</td>
      <td>200</td>
      <td>CA</td>
      <td>C</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
      <td>W</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>B</td>
      <td>300</td>
      <td>WA</td>
      <td>W</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>C</td>
      <td>400</td>
      <td>AK</td>
      <td>A</td>
      <td>3</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>500</td>
      <td>NV</td>
      <td>N</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>




```python
# One hot encoding
pd.get_dummies(df_one['k1'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>



# Data Input and Output


```python
# Various data sources, procssed by pandas

# Saving Data back to csv or new csv
df.to_csv('features', index=False)
```


```python
pwd
```




    'C:\\Users\\sande'


