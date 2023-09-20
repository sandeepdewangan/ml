# Dataframe
2-D Data


```python
import pandas as pd
```


```python
nba = pd.read_csv("datasets/nba.csv")
nba
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>458 rows × 9 columns</p>
</div>




```python
# List of all columns
nba.columns
```




    Index(['Name', 'Team', 'Number', 'Position', 'Age', 'Height', 'Weight',
           'College', 'Salary'],
          dtype='object')




```python
# list of rows and cols
nba.axes
```




    [RangeIndex(start=0, stop=458, step=1),
     Index(['Name', 'Team', 'Number', 'Position', 'Age', 'Height', 'Weight',
            'College', 'Salary'],
           dtype='object')]




```python
nba.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 458 entries, 0 to 457
    Data columns (total 9 columns):
     #   Column    Non-Null Count  Dtype  
    ---  ------    --------------  -----  
     0   Name      457 non-null    object 
     1   Team      457 non-null    object 
     2   Number    457 non-null    float64
     3   Position  457 non-null    object 
     4   Age       457 non-null    float64
     5   Height    457 non-null    object 
     6   Weight    457 non-null    float64
     7   College   373 non-null    object 
     8   Salary    446 non-null    float64
    dtypes: float64(4), object(5)
    memory usage: 32.3+ KB
    


```python
revenue = pd.read_csv("datasets/revenue.csv", index_col="Date")
revenue
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
      <th>New York</th>
      <th>Los Angeles</th>
      <th>Miami</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1/1/16</th>
      <td>985</td>
      <td>122</td>
      <td>499</td>
    </tr>
    <tr>
      <th>1/2/16</th>
      <td>738</td>
      <td>788</td>
      <td>534</td>
    </tr>
    <tr>
      <th>1/3/16</th>
      <td>14</td>
      <td>20</td>
      <td>933</td>
    </tr>
    <tr>
      <th>1/4/16</th>
      <td>730</td>
      <td>904</td>
      <td>885</td>
    </tr>
    <tr>
      <th>1/5/16</th>
      <td>114</td>
      <td>71</td>
      <td>253</td>
    </tr>
    <tr>
      <th>1/6/16</th>
      <td>936</td>
      <td>502</td>
      <td>497</td>
    </tr>
    <tr>
      <th>1/7/16</th>
      <td>123</td>
      <td>996</td>
      <td>115</td>
    </tr>
    <tr>
      <th>1/8/16</th>
      <td>935</td>
      <td>492</td>
      <td>886</td>
    </tr>
    <tr>
      <th>1/9/16</th>
      <td>846</td>
      <td>954</td>
      <td>823</td>
    </tr>
    <tr>
      <th>1/10/16</th>
      <td>54</td>
      <td>285</td>
      <td>216</td>
    </tr>
  </tbody>
</table>
</div>




```python
# SUM
revenue.sum()
```




    New York       5475
    Los Angeles    5134
    Miami          5641
    dtype: int64




```python
revenue.sum(axis="columns")
```




    Date
    1/1/16     1606
    1/2/16     2060
    1/3/16      967
    1/4/16     2519
    1/5/16      438
    1/6/16     1935
    1/7/16     1234
    1/8/16     2313
    1/9/16     2623
    1/10/16     555
    dtype: int64



### Select a single col


```python
nba = pd.read_csv("datasets/nba.csv")
nba
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>458 rows × 9 columns</p>
</div>




```python
nba.Name
```




    0      Avery Bradley
    1        Jae Crowder
    2       John Holland
    3        R.J. Hunter
    4      Jonas Jerebko
               ...      
    453     Shelvin Mack
    454        Raul Neto
    455     Tibor Pleiss
    456      Jeff Withey
    457              NaN
    Name: Name, Length: 458, dtype: object




```python
type(nba.Name)
```




    pandas.core.series.Series




```python
# OR
```


```python
nba["Name"]
```




    0      Avery Bradley
    1        Jae Crowder
    2       John Holland
    3        R.J. Hunter
    4      Jonas Jerebko
               ...      
    453     Shelvin Mack
    454        Raul Neto
    455     Tibor Pleiss
    456      Jeff Withey
    457              NaN
    Name: Name, Length: 458, dtype: object



### Select multiple cols


```python
nba[["Name", "Team"]]
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
      <th>Name</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
    </tr>
    <tr>
      <th>457</th>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>458 rows × 2 columns</p>
</div>



### Add new col


```python
nba = pd.read_csv("datasets/nba.csv")
nba.head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
nba["Sport"] = "Basketball"
nba.head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Sport</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
      <td>Basketball</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
      <td>Basketball</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>NaN</td>
      <td>Basketball</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
      <td>Basketball</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
      <td>Basketball</td>
    </tr>
  </tbody>
</table>
</div>




```python
nba = pd.read_csv("datasets/nba.csv")
```


```python
# Insert with index position
```


```python
nba.insert(loc = 3, column = "Sport", value="Basketball")
```


```python
nba.head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Sport</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>Basketball</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>Basketball</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>Basketball</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>Basketball</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>Basketball</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
    </tr>
  </tbody>
</table>
</div>



### Adding new col from existing ones


```python
nba = pd.read_csv("datasets/nba.csv")
nba.head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
nba["Age in a Decade"] = nba["Age"] + 10
nba.head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>NaN</td>
      <td>37.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
      <td>32.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
      <td>39.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
###  Count values
```


```python
# value_counts return the count of unique rows
```


```python
nba.value_counts().head()
```




    Name                    Team               Number  Position  Age   Height  Weight  College     Salary     Age in a Decade
    Aaron Brooks            Chicago Bulls      0.0     PG        31.0  6-0     161.0   Oregon      2250000.0  41.0               1
    Mike Muscala            Atlanta Hawks      31.0    PF        24.0  6-11    240.0   Bucknell    947276.0   34.0               1
    Mike Dunleavy           Chicago Bulls      34.0    SG        35.0  6-9     230.0   Duke        4500000.0  45.0               1
    Mike Conley             Memphis Grizzlies  11.0    PG        28.0  6-1     175.0   Ohio State  9588426.0  38.0               1
    Michael Kidd-Gilchrist  Charlotte Hornets  14.0    SF        22.0  6-7     232.0   Kentucky    6331404.0  32.0               1
    Name: count, dtype: int64




```python
nba["Position"].value_counts()
```




    Position
    SG    102
    PF    100
    PG     92
    SF     85
    C      78
    Name: count, dtype: int64




```python
# in percentage
nba["Position"].value_counts(normalize=True)
```




    Position
    SG    0.223195
    PF    0.218818
    PG    0.201313
    SF    0.185996
    C     0.170678
    Name: proportion, dtype: float64



### Drop rows with null values


```python
nba.tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# will remove a row if atleast one NaN present in cols.
nba.dropna().tail()
# nba.dropna().tail(how="any")
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>449</th>
      <td>Rodney Hood</td>
      <td>Utah Jazz</td>
      <td>5.0</td>
      <td>SG</td>
      <td>23.0</td>
      <td>6-8</td>
      <td>206.0</td>
      <td>Duke</td>
      <td>1348440.0</td>
      <td>33.0</td>
    </tr>
    <tr>
      <th>451</th>
      <td>Chris Johnson</td>
      <td>Utah Jazz</td>
      <td>23.0</td>
      <td>SF</td>
      <td>26.0</td>
      <td>6-6</td>
      <td>206.0</td>
      <td>Dayton</td>
      <td>981348.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>452</th>
      <td>Trey Lyles</td>
      <td>Utah Jazz</td>
      <td>41.0</td>
      <td>PF</td>
      <td>20.0</td>
      <td>6-10</td>
      <td>234.0</td>
      <td>Kentucky</td>
      <td>2239800.0</td>
      <td>30.0</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
      <td>36.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
nba.tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# we want to delete only, where for all the NaN cols.
nba.dropna(how="all").tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>452</th>
      <td>Trey Lyles</td>
      <td>Utah Jazz</td>
      <td>41.0</td>
      <td>PF</td>
      <td>20.0</td>
      <td>6-10</td>
      <td>234.0</td>
      <td>Kentucky</td>
      <td>2239800.0</td>
      <td>30.0</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
      <td>36.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
nba.tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# remove row where missing value in specific col.
# remove row where college col contains NaN
nba.dropna(subset=["College"]).tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>449</th>
      <td>Rodney Hood</td>
      <td>Utah Jazz</td>
      <td>5.0</td>
      <td>SG</td>
      <td>23.0</td>
      <td>6-8</td>
      <td>206.0</td>
      <td>Duke</td>
      <td>1348440.0</td>
      <td>33.0</td>
    </tr>
    <tr>
      <th>451</th>
      <td>Chris Johnson</td>
      <td>Utah Jazz</td>
      <td>23.0</td>
      <td>SF</td>
      <td>26.0</td>
      <td>6-6</td>
      <td>206.0</td>
      <td>Dayton</td>
      <td>981348.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>452</th>
      <td>Trey Lyles</td>
      <td>Utah Jazz</td>
      <td>41.0</td>
      <td>PF</td>
      <td>20.0</td>
      <td>6-10</td>
      <td>234.0</td>
      <td>Kentucky</td>
      <td>2239800.0</td>
      <td>30.0</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
      <td>36.0</td>
    </tr>
  </tbody>
</table>
</div>



### Fill missing Data Frame


```python
nba.tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# replace all NaN with 0
nba.fillna(0)
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Age in a Decade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
      <td>35.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>0.0</td>
      <td>37.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
      <td>32.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>0</td>
      <td>5000000.0</td>
      <td>39.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>0</td>
      <td>900000.0</td>
      <td>34.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>0</td>
      <td>2900000.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
      <td>36.0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>458 rows × 10 columns</p>
</div>




```python
# changing the college col NaN with Unknown
nba["College"] = nba["College"].fillna("Unknown")
nba.tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>Unknown</td>
      <td>900000.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>Unknown</td>
      <td>2900000.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Unknown</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### astype
Convert one datatype to another


```python
nba = pd.read_csv("datasets/nba.csv").dropna(how="all")
nba.tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>452</th>
      <td>Trey Lyles</td>
      <td>Utah Jazz</td>
      <td>41.0</td>
      <td>PF</td>
      <td>20.0</td>
      <td>6-10</td>
      <td>234.0</td>
      <td>Kentucky</td>
      <td>2239800.0</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# conver age col to int
nba["Age"].hasnans # First check if col contain null values, if yes fill those values
nba["Age"] = nba["Age"].astype("int")
```


```python
nba.head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
nba["Salary"].hasnans
nba["Salary"] = nba["Salary"].fillna(0)
nba["Salary"] = nba["Salary"].astype(int).astype("str")
nba.tail()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>452</th>
      <td>Trey Lyles</td>
      <td>Utah Jazz</td>
      <td>41.0</td>
      <td>PF</td>
      <td>20</td>
      <td>6-10</td>
      <td>234.0</td>
      <td>Kentucky</td>
      <td>2239800</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276</td>
    </tr>
  </tbody>
</table>
</div>




```python
# astype another method - categorical 
```


```python
# Position col contains many duplciates rows
```


```python
nba["Position"].nunique() # only 5 unique rows
```




    5




```python
nba["Position"] = nba["Position"].astype("category")
nba.head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Categories (5, object): ['C', 'PF', 'PG', 'SF', 'SG']
# Pandas do not repeat the value and keep the ref. It reduces mem.
```

### sort_values()


```python
nba.head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# OR
nba.sort_values(by="Name")
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>152</th>
      <td>Aaron Brooks</td>
      <td>Chicago Bulls</td>
      <td>0.0</td>
      <td>PG</td>
      <td>31</td>
      <td>6-0</td>
      <td>161.0</td>
      <td>Oregon</td>
      <td>2250000</td>
    </tr>
    <tr>
      <th>356</th>
      <td>Aaron Gordon</td>
      <td>Orlando Magic</td>
      <td>0.0</td>
      <td>PF</td>
      <td>20</td>
      <td>6-9</td>
      <td>220.0</td>
      <td>Arizona</td>
      <td>4171680</td>
    </tr>
    <tr>
      <th>328</th>
      <td>Aaron Harrison</td>
      <td>Charlotte Hornets</td>
      <td>9.0</td>
      <td>SG</td>
      <td>21</td>
      <td>6-6</td>
      <td>210.0</td>
      <td>Kentucky</td>
      <td>525093</td>
    </tr>
    <tr>
      <th>404</th>
      <td>Adreian Payne</td>
      <td>Minnesota Timberwolves</td>
      <td>33.0</td>
      <td>PF</td>
      <td>25</td>
      <td>6-10</td>
      <td>237.0</td>
      <td>Michigan State</td>
      <td>1938840</td>
    </tr>
    <tr>
      <th>312</th>
      <td>Al Horford</td>
      <td>Atlanta Hawks</td>
      <td>15.0</td>
      <td>C</td>
      <td>30</td>
      <td>6-10</td>
      <td>245.0</td>
      <td>Florida</td>
      <td>12000000</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>386</th>
      <td>Wilson Chandler</td>
      <td>Denver Nuggets</td>
      <td>21.0</td>
      <td>SF</td>
      <td>29</td>
      <td>6-8</td>
      <td>225.0</td>
      <td>DePaul</td>
      <td>10449438</td>
    </tr>
    <tr>
      <th>270</th>
      <td>Xavier Munford</td>
      <td>Memphis Grizzlies</td>
      <td>14.0</td>
      <td>PG</td>
      <td>24</td>
      <td>6-3</td>
      <td>180.0</td>
      <td>Rhode Island</td>
      <td>0</td>
    </tr>
    <tr>
      <th>402</th>
      <td>Zach LaVine</td>
      <td>Minnesota Timberwolves</td>
      <td>8.0</td>
      <td>PG</td>
      <td>21</td>
      <td>6-5</td>
      <td>189.0</td>
      <td>UCLA</td>
      <td>2148360</td>
    </tr>
    <tr>
      <th>271</th>
      <td>Zach Randolph</td>
      <td>Memphis Grizzlies</td>
      <td>50.0</td>
      <td>PF</td>
      <td>34</td>
      <td>6-9</td>
      <td>260.0</td>
      <td>Michigan State</td>
      <td>9638555</td>
    </tr>
    <tr>
      <th>237</th>
      <td>Zaza Pachulia</td>
      <td>Dallas Mavericks</td>
      <td>27.0</td>
      <td>C</td>
      <td>32</td>
      <td>6-11</td>
      <td>275.0</td>
      <td>NaN</td>
      <td>5200000</td>
    </tr>
  </tbody>
</table>
<p>457 rows × 9 columns</p>
</div>




```python
nba.sort_values(by=["Team", "Name"])
nba.sort_values(by=["Team", "Name"], ascending=[True, False])
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>322</th>
      <td>Walter Tavares</td>
      <td>Atlanta Hawks</td>
      <td>22.0</td>
      <td>C</td>
      <td>24</td>
      <td>7-3</td>
      <td>260.0</td>
      <td>NaN</td>
      <td>1000000</td>
    </tr>
    <tr>
      <th>310</th>
      <td>Tim Hardaway Jr.</td>
      <td>Atlanta Hawks</td>
      <td>10.0</td>
      <td>SG</td>
      <td>24</td>
      <td>6-6</td>
      <td>205.0</td>
      <td>Michigan</td>
      <td>1304520</td>
    </tr>
    <tr>
      <th>321</th>
      <td>Tiago Splitter</td>
      <td>Atlanta Hawks</td>
      <td>11.0</td>
      <td>C</td>
      <td>31</td>
      <td>6-11</td>
      <td>245.0</td>
      <td>NaN</td>
      <td>9756250</td>
    </tr>
    <tr>
      <th>320</th>
      <td>Thabo Sefolosha</td>
      <td>Atlanta Hawks</td>
      <td>25.0</td>
      <td>SF</td>
      <td>32</td>
      <td>6-7</td>
      <td>220.0</td>
      <td>NaN</td>
      <td>4000000</td>
    </tr>
    <tr>
      <th>315</th>
      <td>Paul Millsap</td>
      <td>Atlanta Hawks</td>
      <td>4.0</td>
      <td>PF</td>
      <td>31</td>
      <td>6-8</td>
      <td>246.0</td>
      <td>Louisiana Tech</td>
      <td>18671659</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>374</th>
      <td>JJ Hickson</td>
      <td>Washington Wizards</td>
      <td>21.0</td>
      <td>C</td>
      <td>27</td>
      <td>6-9</td>
      <td>242.0</td>
      <td>North Carolina State</td>
      <td>273038</td>
    </tr>
    <tr>
      <th>380</th>
      <td>Garrett Temple</td>
      <td>Washington Wizards</td>
      <td>17.0</td>
      <td>SG</td>
      <td>30</td>
      <td>6-6</td>
      <td>195.0</td>
      <td>LSU</td>
      <td>1100602</td>
    </tr>
    <tr>
      <th>372</th>
      <td>Drew Gooden</td>
      <td>Washington Wizards</td>
      <td>90.0</td>
      <td>PF</td>
      <td>34</td>
      <td>6-10</td>
      <td>250.0</td>
      <td>Kansas</td>
      <td>3300000</td>
    </tr>
    <tr>
      <th>369</th>
      <td>Bradley Beal</td>
      <td>Washington Wizards</td>
      <td>3.0</td>
      <td>SG</td>
      <td>22</td>
      <td>6-5</td>
      <td>207.0</td>
      <td>Florida</td>
      <td>5694674</td>
    </tr>
    <tr>
      <th>368</th>
      <td>Alan Anderson</td>
      <td>Washington Wizards</td>
      <td>6.0</td>
      <td>SG</td>
      <td>33</td>
      <td>6-6</td>
      <td>220.0</td>
      <td>Michigan State</td>
      <td>4000000</td>
    </tr>
  </tbody>
</table>
<p>457 rows × 9 columns</p>
</div>




```python
# Sorting by index
```


```python
nba.sort_index().head()
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000</td>
    </tr>
  </tbody>
</table>
</div>



### Rank method
rank() method returns a rank of every respective index of a series passed.


```python
nba = pd.read_csv("datasets/nba.csv").dropna(how="all")
nba["Salary"] = nba["Salary"].fillna(0)
nba
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Avery Bradley</td>
      <td>Boston Celtics</td>
      <td>0.0</td>
      <td>PG</td>
      <td>25.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>Texas</td>
      <td>7730337.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Jae Crowder</td>
      <td>Boston Celtics</td>
      <td>99.0</td>
      <td>SF</td>
      <td>25.0</td>
      <td>6-6</td>
      <td>235.0</td>
      <td>Marquette</td>
      <td>6796117.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>John Holland</td>
      <td>Boston Celtics</td>
      <td>30.0</td>
      <td>SG</td>
      <td>27.0</td>
      <td>6-5</td>
      <td>205.0</td>
      <td>Boston University</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>R.J. Hunter</td>
      <td>Boston Celtics</td>
      <td>28.0</td>
      <td>SG</td>
      <td>22.0</td>
      <td>6-5</td>
      <td>185.0</td>
      <td>Georgia State</td>
      <td>1148640.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Jonas Jerebko</td>
      <td>Boston Celtics</td>
      <td>8.0</td>
      <td>PF</td>
      <td>29.0</td>
      <td>6-10</td>
      <td>231.0</td>
      <td>NaN</td>
      <td>5000000.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>452</th>
      <td>Trey Lyles</td>
      <td>Utah Jazz</td>
      <td>41.0</td>
      <td>PF</td>
      <td>20.0</td>
      <td>6-10</td>
      <td>234.0</td>
      <td>Kentucky</td>
      <td>2239800.0</td>
    </tr>
    <tr>
      <th>453</th>
      <td>Shelvin Mack</td>
      <td>Utah Jazz</td>
      <td>8.0</td>
      <td>PG</td>
      <td>26.0</td>
      <td>6-3</td>
      <td>203.0</td>
      <td>Butler</td>
      <td>2433333.0</td>
    </tr>
    <tr>
      <th>454</th>
      <td>Raul Neto</td>
      <td>Utah Jazz</td>
      <td>25.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-1</td>
      <td>179.0</td>
      <td>NaN</td>
      <td>900000.0</td>
    </tr>
    <tr>
      <th>455</th>
      <td>Tibor Pleiss</td>
      <td>Utah Jazz</td>
      <td>21.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-3</td>
      <td>256.0</td>
      <td>NaN</td>
      <td>2900000.0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>Jeff Withey</td>
      <td>Utah Jazz</td>
      <td>24.0</td>
      <td>C</td>
      <td>26.0</td>
      <td>7-0</td>
      <td>231.0</td>
      <td>Kansas</td>
      <td>947276.0</td>
    </tr>
  </tbody>
</table>
<p>457 rows × 9 columns</p>
</div>




```python
nba["Salary Rank"] = nba["Salary"].rank(ascending=False).astype(int)
```


```python
nba.sort_values("Salary", ascending=False)
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
      <th>Name</th>
      <th>Team</th>
      <th>Number</th>
      <th>Position</th>
      <th>Age</th>
      <th>Height</th>
      <th>Weight</th>
      <th>College</th>
      <th>Salary</th>
      <th>Salary Rank</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>109</th>
      <td>Kobe Bryant</td>
      <td>Los Angeles Lakers</td>
      <td>24.0</td>
      <td>SF</td>
      <td>37.0</td>
      <td>6-6</td>
      <td>212.0</td>
      <td>NaN</td>
      <td>25000000.0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>169</th>
      <td>LeBron James</td>
      <td>Cleveland Cavaliers</td>
      <td>23.0</td>
      <td>SF</td>
      <td>31.0</td>
      <td>6-8</td>
      <td>250.0</td>
      <td>NaN</td>
      <td>22970500.0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Carmelo Anthony</td>
      <td>New York Knicks</td>
      <td>7.0</td>
      <td>SF</td>
      <td>32.0</td>
      <td>6-8</td>
      <td>240.0</td>
      <td>Syracuse</td>
      <td>22875000.0</td>
      <td>3</td>
    </tr>
    <tr>
      <th>251</th>
      <td>Dwight Howard</td>
      <td>Houston Rockets</td>
      <td>12.0</td>
      <td>C</td>
      <td>30.0</td>
      <td>6-11</td>
      <td>265.0</td>
      <td>NaN</td>
      <td>22359364.0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>339</th>
      <td>Chris Bosh</td>
      <td>Miami Heat</td>
      <td>1.0</td>
      <td>PF</td>
      <td>32.0</td>
      <td>6-11</td>
      <td>235.0</td>
      <td>Georgia Tech</td>
      <td>22192730.0</td>
      <td>5</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>353</th>
      <td>Dorell Wright</td>
      <td>Miami Heat</td>
      <td>11.0</td>
      <td>SF</td>
      <td>30.0</td>
      <td>6-9</td>
      <td>205.0</td>
      <td>NaN</td>
      <td>0.0</td>
      <td>452</td>
    </tr>
    <tr>
      <th>264</th>
      <td>Jordan Farmar</td>
      <td>Memphis Grizzlies</td>
      <td>4.0</td>
      <td>PG</td>
      <td>29.0</td>
      <td>6-2</td>
      <td>180.0</td>
      <td>UCLA</td>
      <td>0.0</td>
      <td>452</td>
    </tr>
    <tr>
      <th>409</th>
      <td>Greg Smith</td>
      <td>Minnesota Timberwolves</td>
      <td>4.0</td>
      <td>PF</td>
      <td>25.0</td>
      <td>6-10</td>
      <td>250.0</td>
      <td>Fresno State</td>
      <td>0.0</td>
      <td>452</td>
    </tr>
    <tr>
      <th>273</th>
      <td>Alex Stepheson</td>
      <td>Memphis Grizzlies</td>
      <td>35.0</td>
      <td>PF</td>
      <td>28.0</td>
      <td>6-10</td>
      <td>270.0</td>
      <td>USC</td>
      <td>0.0</td>
      <td>452</td>
    </tr>
    <tr>
      <th>270</th>
      <td>Xavier Munford</td>
      <td>Memphis Grizzlies</td>
      <td>14.0</td>
      <td>PG</td>
      <td>24.0</td>
      <td>6-3</td>
      <td>180.0</td>
      <td>Rhode Island</td>
      <td>0.0</td>
      <td>452</td>
    </tr>
  </tbody>
</table>
<p>457 rows × 10 columns</p>
</div>




```python

```
