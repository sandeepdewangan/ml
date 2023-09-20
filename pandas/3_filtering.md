# Data Frames - Filtering


```python
import pandas as pd
```


```python
df = pd.read_csv("datasets/employees.csv")
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Douglas</td>
      <td>Male</td>
      <td>8/6/1993</td>
      <td>12:42 PM</td>
      <td>97308</td>
      <td>6.945</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Thomas</td>
      <td>Male</td>
      <td>3/31/1996</td>
      <td>6:53 AM</td>
      <td>61933</td>
      <td>4.170</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Maria</td>
      <td>Female</td>
      <td>4/23/1993</td>
      <td>11:17 AM</td>
      <td>130590</td>
      <td>11.858</td>
      <td>False</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>Male</td>
      <td>3/4/2005</td>
      <td>1:00 PM</td>
      <td>138705</td>
      <td>9.340</td>
      <td>True</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Larry</td>
      <td>Male</td>
      <td>1/24/1998</td>
      <td>4:47 PM</td>
      <td>101004</td>
      <td>1.389</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1000 entries, 0 to 999
    Data columns (total 8 columns):
     #   Column             Non-Null Count  Dtype  
    ---  ------             --------------  -----  
     0   First Name         933 non-null    object 
     1   Gender             855 non-null    object 
     2   Start Date         1000 non-null   object 
     3   Last Login Time    1000 non-null   object 
     4   Salary             1000 non-null   int64  
     5   Bonus %            1000 non-null   float64
     6   Senior Management  933 non-null    object 
     7   Team               957 non-null    object 
    dtypes: float64(1), int64(1), object(6)
    memory usage: 62.6+ KB
    


```python
# Convert Start Date col of object dtype to date time dtype
df["Start Date"] = pd.to_datetime(df["Start Date"])
df["Last Login Time"] = pd.to_datetime(df["Last Login Time"]) # date not specified so default it to today.
# convert Senior Management col to bool
df["Senior Management"] = df["Senior Management"].astype(bool)
# convert gender col to category
df["Gender"] = df["Gender"].astype("category")
```

    C:\Users\sande\AppData\Local\Temp\ipykernel_7800\3245198919.py:3: UserWarning: Could not infer format, so each element will be parsed individually, falling back to `dateutil`. To ensure parsing is consistent and as-expected, please specify a format.
      df["Last Login Time"] = pd.to_datetime(df["Last Login Time"]) # date not specified so default it to today.
    


```python
df.info() # see the difference in memory usage above and below.
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1000 entries, 0 to 999
    Data columns (total 8 columns):
     #   Column             Non-Null Count  Dtype         
    ---  ------             --------------  -----         
     0   First Name         933 non-null    object        
     1   Gender             855 non-null    category      
     2   Start Date         1000 non-null   datetime64[ns]
     3   Last Login Time    1000 non-null   datetime64[ns]
     4   Salary             1000 non-null   int64         
     5   Bonus %            1000 non-null   float64       
     6   Senior Management  1000 non-null   bool          
     7   Team               957 non-null    object        
    dtypes: bool(1), category(1), datetime64[ns](2), float64(1), int64(1), object(2)
    memory usage: 49.1+ KB
    


```python
# df["Start Date"] = pd.to_datetime(df["Start Date"])
# df["Last Login Time"] = pd.to_datetime(df["Last Login Time"])

# Alternating to below two rows we can use

# df = pd.read_csv("datasets/employees.csv", parse_dates=["Start Date", "Last Login Time"])
```

### Filter data based on condition


```python
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Douglas</td>
      <td>Male</td>
      <td>1993-08-06</td>
      <td>2023-08-15 12:42:00</td>
      <td>97308</td>
      <td>6.945</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Thomas</td>
      <td>Male</td>
      <td>1996-03-31</td>
      <td>2023-08-15 06:53:00</td>
      <td>61933</td>
      <td>4.170</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Maria</td>
      <td>Female</td>
      <td>1993-04-23</td>
      <td>2023-08-15 11:17:00</td>
      <td>130590</td>
      <td>11.858</td>
      <td>False</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>Male</td>
      <td>2005-03-04</td>
      <td>2023-08-15 13:00:00</td>
      <td>138705</td>
      <td>9.340</td>
      <td>True</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Larry</td>
      <td>Male</td>
      <td>1998-01-24</td>
      <td>2023-08-15 16:47:00</td>
      <td>101004</td>
      <td>1.389</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Filter by gender
df["Gender"] == "Male"
# this will extract all true and false values.
# to extract only true values, wrap it with square brakets.

df[df["Gender"] == "Male"].head()
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Douglas</td>
      <td>Male</td>
      <td>1993-08-06</td>
      <td>2023-08-15 12:42:00</td>
      <td>97308</td>
      <td>6.945</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Thomas</td>
      <td>Male</td>
      <td>1996-03-31</td>
      <td>2023-08-15 06:53:00</td>
      <td>61933</td>
      <td>4.170</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>Male</td>
      <td>2005-03-04</td>
      <td>2023-08-15 13:00:00</td>
      <td>138705</td>
      <td>9.340</td>
      <td>True</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Larry</td>
      <td>Male</td>
      <td>1998-01-24</td>
      <td>2023-08-15 16:47:00</td>
      <td>101004</td>
      <td>1.389</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Dennis</td>
      <td>Male</td>
      <td>1987-04-18</td>
      <td>2023-08-15 01:35:00</td>
      <td>115163</td>
      <td>10.125</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Better way
filter = df["Gender"] == "Male"
df[filter].head()
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Douglas</td>
      <td>Male</td>
      <td>1993-08-06</td>
      <td>2023-08-15 12:42:00</td>
      <td>97308</td>
      <td>6.945</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Thomas</td>
      <td>Male</td>
      <td>1996-03-31</td>
      <td>2023-08-15 06:53:00</td>
      <td>61933</td>
      <td>4.170</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>Male</td>
      <td>2005-03-04</td>
      <td>2023-08-15 13:00:00</td>
      <td>138705</td>
      <td>9.340</td>
      <td>True</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Larry</td>
      <td>Male</td>
      <td>1998-01-24</td>
      <td>2023-08-15 16:47:00</td>
      <td>101004</td>
      <td>1.389</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Dennis</td>
      <td>Male</td>
      <td>1987-04-18</td>
      <td>2023-08-15 01:35:00</td>
      <td>115163</td>
      <td>10.125</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
  </tbody>
</table>
</div>



### Filter with more than one conditions


```python
male = df["Gender"] == "Male"
team = df["Team"] == "Marketing"
df[male & team] # AND
df[male | team] # OR
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Douglas</td>
      <td>Male</td>
      <td>1993-08-06</td>
      <td>2023-08-15 12:42:00</td>
      <td>97308</td>
      <td>6.945</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Thomas</td>
      <td>Male</td>
      <td>1996-03-31</td>
      <td>2023-08-15 06:53:00</td>
      <td>61933</td>
      <td>4.170</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>Male</td>
      <td>2005-03-04</td>
      <td>2023-08-15 13:00:00</td>
      <td>138705</td>
      <td>9.340</td>
      <td>True</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Larry</td>
      <td>Male</td>
      <td>1998-01-24</td>
      <td>2023-08-15 16:47:00</td>
      <td>101004</td>
      <td>1.389</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Dennis</td>
      <td>Male</td>
      <td>1987-04-18</td>
      <td>2023-08-15 01:35:00</td>
      <td>115163</td>
      <td>10.125</td>
      <td>False</td>
      <td>Legal</td>
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
    </tr>
    <tr>
      <th>994</th>
      <td>George</td>
      <td>Male</td>
      <td>2013-06-21</td>
      <td>2023-08-15 17:47:00</td>
      <td>98874</td>
      <td>4.479</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>996</th>
      <td>Phillip</td>
      <td>Male</td>
      <td>1984-01-31</td>
      <td>2023-08-15 06:30:00</td>
      <td>42392</td>
      <td>19.675</td>
      <td>False</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>997</th>
      <td>Russell</td>
      <td>Male</td>
      <td>2013-05-20</td>
      <td>2023-08-15 12:39:00</td>
      <td>96914</td>
      <td>1.421</td>
      <td>False</td>
      <td>Product</td>
    </tr>
    <tr>
      <th>998</th>
      <td>Larry</td>
      <td>Male</td>
      <td>2013-04-20</td>
      <td>2023-08-15 16:45:00</td>
      <td>60500</td>
      <td>11.985</td>
      <td>False</td>
      <td>Business Development</td>
    </tr>
    <tr>
      <th>999</th>
      <td>Albert</td>
      <td>Male</td>
      <td>2012-05-15</td>
      <td>2023-08-15 18:24:00</td>
      <td>129949</td>
      <td>10.169</td>
      <td>True</td>
      <td>Sales</td>
    </tr>
  </tbody>
</table>
<p>481 rows × 8 columns</p>
</div>



### isin()


```python
# filter1 = df["Team"] == "Legal"
# filter2 = df["Team"] = "Another"
# filter3 = df["Team"] = "Produc"
# df[filter1 | filter2 | filter3]
# Instead of applying these filter use isin()
filter = df["Team"].isin(["Legal", "Product"])
df[filter]
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>Dennis</td>
      <td>Male</td>
      <td>1987-04-18</td>
      <td>2023-08-15 01:35:00</td>
      <td>115163</td>
      <td>10.125</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Ruby</td>
      <td>Female</td>
      <td>1987-08-17</td>
      <td>2023-08-15 16:20:00</td>
      <td>65476</td>
      <td>10.012</td>
      <td>True</td>
      <td>Product</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Julie</td>
      <td>Female</td>
      <td>1997-10-26</td>
      <td>2023-08-15 15:19:00</td>
      <td>102508</td>
      <td>12.637</td>
      <td>True</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Lillian</td>
      <td>Female</td>
      <td>2016-06-05</td>
      <td>2023-08-15 06:09:00</td>
      <td>59414</td>
      <td>1.256</td>
      <td>False</td>
      <td>Product</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Shawn</td>
      <td>Male</td>
      <td>1986-12-07</td>
      <td>2023-08-15 19:45:00</td>
      <td>111737</td>
      <td>6.414</td>
      <td>False</td>
      <td>Product</td>
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
    </tr>
    <tr>
      <th>979</th>
      <td>Ernest</td>
      <td>Male</td>
      <td>2013-07-20</td>
      <td>2023-08-15 06:41:00</td>
      <td>142935</td>
      <td>13.198</td>
      <td>True</td>
      <td>Product</td>
    </tr>
    <tr>
      <th>981</th>
      <td>James</td>
      <td>Male</td>
      <td>1993-01-15</td>
      <td>2023-08-15 17:19:00</td>
      <td>148985</td>
      <td>19.280</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>985</th>
      <td>Stephen</td>
      <td>NaN</td>
      <td>1983-07-10</td>
      <td>2023-08-15 20:10:00</td>
      <td>85668</td>
      <td>1.909</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>989</th>
      <td>Justin</td>
      <td>NaN</td>
      <td>1991-02-10</td>
      <td>2023-08-15 16:58:00</td>
      <td>38344</td>
      <td>3.794</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>997</th>
      <td>Russell</td>
      <td>Male</td>
      <td>2013-05-20</td>
      <td>2023-08-15 12:39:00</td>
      <td>96914</td>
      <td>1.421</td>
      <td>False</td>
      <td>Product</td>
    </tr>
  </tbody>
</table>
<p>183 rows × 8 columns</p>
</div>



### isnull(), notnull()


```python
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Douglas</td>
      <td>Male</td>
      <td>1993-08-06</td>
      <td>2023-08-15 12:42:00</td>
      <td>97308</td>
      <td>6.945</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Thomas</td>
      <td>Male</td>
      <td>1996-03-31</td>
      <td>2023-08-15 06:53:00</td>
      <td>61933</td>
      <td>4.170</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Maria</td>
      <td>Female</td>
      <td>1993-04-23</td>
      <td>2023-08-15 11:17:00</td>
      <td>130590</td>
      <td>11.858</td>
      <td>False</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>Male</td>
      <td>2005-03-04</td>
      <td>2023-08-15 13:00:00</td>
      <td>138705</td>
      <td>9.340</td>
      <td>True</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Larry</td>
      <td>Male</td>
      <td>1998-01-24</td>
      <td>2023-08-15 16:47:00</td>
      <td>101004</td>
      <td>1.389</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["Team"].isnull()
```




    0      False
    1       True
    2      False
    3      False
    4      False
           ...  
    995    False
    996    False
    997    False
    998    False
    999    False
    Name: Team, Length: 1000, dtype: bool




```python
df["Team"].notnull()
```




    0       True
    1      False
    2       True
    3       True
    4       True
           ...  
    995     True
    996     True
    997     True
    998     True
    999     True
    Name: Team, Length: 1000, dtype: bool



### Between


```python
df["Salary"].between(60000,70000) # both values are inclusive
```




    0      False
    1       True
    2      False
    3      False
    4      False
           ...  
    995    False
    996    False
    997    False
    998     True
    999    False
    Name: Salary, Length: 1000, dtype: bool



### Duplicate


```python
df.sort_values("First Name").head()
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>101</th>
      <td>Aaron</td>
      <td>Male</td>
      <td>2012-02-17</td>
      <td>2023-08-15 10:20:00</td>
      <td>61602</td>
      <td>11.849</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>327</th>
      <td>Aaron</td>
      <td>Male</td>
      <td>1994-01-29</td>
      <td>2023-08-15 18:48:00</td>
      <td>58755</td>
      <td>5.097</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>440</th>
      <td>Aaron</td>
      <td>Male</td>
      <td>1990-07-22</td>
      <td>2023-08-15 14:53:00</td>
      <td>52119</td>
      <td>11.343</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
    <tr>
      <th>937</th>
      <td>Aaron</td>
      <td>NaN</td>
      <td>1986-01-22</td>
      <td>2023-08-15 19:39:00</td>
      <td>63126</td>
      <td>18.424</td>
      <td>False</td>
      <td>Client Services</td>
    </tr>
    <tr>
      <th>137</th>
      <td>Adam</td>
      <td>Male</td>
      <td>2011-05-21</td>
      <td>2023-08-15 01:45:00</td>
      <td>95327</td>
      <td>15.120</td>
      <td>False</td>
      <td>Distribution</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["First Name"].sort_values().duplicated() # first encounter of Aaron is not duplicate, rest are.
```




    101    False
    327     True
    440     True
    937     True
    137    False
           ...  
    902     True
    925     True
    946     True
    947     True
    951     True
    Name: First Name, Length: 1000, dtype: bool




```python
dup = ~df["First Name"].duplicated(keep=False)
df[dup].head(10)
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>Dennis</td>
      <td>Male</td>
      <td>1987-04-18</td>
      <td>2023-08-15 01:35:00</td>
      <td>115163</td>
      <td>10.125</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Angela</td>
      <td>Female</td>
      <td>2005-11-22</td>
      <td>2023-08-15 06:29:00</td>
      <td>95570</td>
      <td>18.523</td>
      <td>True</td>
      <td>Engineering</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Jean</td>
      <td>Female</td>
      <td>1993-12-18</td>
      <td>2023-08-15 09:07:00</td>
      <td>119082</td>
      <td>16.180</td>
      <td>False</td>
      <td>Business Development</td>
    </tr>
    <tr>
      <th>190</th>
      <td>Carol</td>
      <td>Female</td>
      <td>1996-03-19</td>
      <td>2023-08-15 03:39:00</td>
      <td>57783</td>
      <td>9.129</td>
      <td>False</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>291</th>
      <td>Tammy</td>
      <td>Female</td>
      <td>1984-11-11</td>
      <td>2023-08-15 10:30:00</td>
      <td>132839</td>
      <td>17.463</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
    <tr>
      <th>495</th>
      <td>Eugene</td>
      <td>Male</td>
      <td>1984-05-24</td>
      <td>2023-08-15 10:54:00</td>
      <td>81077</td>
      <td>2.117</td>
      <td>False</td>
      <td>Sales</td>
    </tr>
    <tr>
      <th>688</th>
      <td>Brian</td>
      <td>Male</td>
      <td>2007-04-07</td>
      <td>2023-08-15 22:47:00</td>
      <td>93901</td>
      <td>17.821</td>
      <td>True</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>832</th>
      <td>Keith</td>
      <td>Male</td>
      <td>2003-02-12</td>
      <td>2023-08-15 15:02:00</td>
      <td>120672</td>
      <td>19.467</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>887</th>
      <td>David</td>
      <td>Male</td>
      <td>2009-12-05</td>
      <td>2023-08-15 08:48:00</td>
      <td>92242</td>
      <td>15.407</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
  </tbody>
</table>
</div>



### drop_duplicates()


```python
df = pd.read_csv("datasets/employees.csv")
df["Start Date"] = pd.to_datetime(df["Start Date"])
df["Last Login Time"] = pd.to_datetime(df["Last Login Time"])
df["Senior Management"] = df["Senior Management"].astype(bool)
df["Gender"] = df["Gender"].astype("category")
```

    C:\Users\sande\AppData\Local\Temp\ipykernel_7800\2176492938.py:3: UserWarning: Could not infer format, so each element will be parsed individually, falling back to `dateutil`. To ensure parsing is consistent and as-expected, please specify a format.
      df["Last Login Time"] = pd.to_datetime(df["Last Login Time"])
    


```python
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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Douglas</td>
      <td>Male</td>
      <td>1993-08-06</td>
      <td>2023-08-15 12:42:00</td>
      <td>97308</td>
      <td>6.945</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Thomas</td>
      <td>Male</td>
      <td>1996-03-31</td>
      <td>2023-08-15 06:53:00</td>
      <td>61933</td>
      <td>4.170</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Maria</td>
      <td>Female</td>
      <td>1993-04-23</td>
      <td>2023-08-15 11:17:00</td>
      <td>130590</td>
      <td>11.858</td>
      <td>False</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>Male</td>
      <td>2005-03-04</td>
      <td>2023-08-15 13:00:00</td>
      <td>138705</td>
      <td>9.340</td>
      <td>True</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Larry</td>
      <td>Male</td>
      <td>1998-01-24</td>
      <td>2023-08-15 16:47:00</td>
      <td>101004</td>
      <td>1.389</td>
      <td>True</td>
      <td>Client Services</td>
    </tr>
  </tbody>
</table>
</div>




```python
len(df)
```




    1000




```python
len(df.drop_duplicates())
```




    1000




```python
# both outputs are same, bez combinedly all are unique rows.
```


```python
df.drop_duplicates(subset=["First Name"], keep="first") 
# keep the first occurance
# if keep=False, it will remove all the occurances

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
      <th>First Name</th>
      <th>Gender</th>
      <th>Start Date</th>
      <th>Last Login Time</th>
      <th>Salary</th>
      <th>Bonus %</th>
      <th>Senior Management</th>
      <th>Team</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Douglas</td>
      <td>Male</td>
      <td>1993-08-06</td>
      <td>2023-08-15 12:42:00</td>
      <td>97308</td>
      <td>6.945</td>
      <td>True</td>
      <td>Marketing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Thomas</td>
      <td>Male</td>
      <td>1996-03-31</td>
      <td>2023-08-15 06:53:00</td>
      <td>61933</td>
      <td>4.170</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Maria</td>
      <td>Female</td>
      <td>1993-04-23</td>
      <td>2023-08-15 11:17:00</td>
      <td>130590</td>
      <td>11.858</td>
      <td>False</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>Male</td>
      <td>2005-03-04</td>
      <td>2023-08-15 13:00:00</td>
      <td>138705</td>
      <td>9.340</td>
      <td>True</td>
      <td>Finance</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Larry</td>
      <td>Male</td>
      <td>1998-01-24</td>
      <td>2023-08-15 16:47:00</td>
      <td>101004</td>
      <td>1.389</td>
      <td>True</td>
      <td>Client Services</td>
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
    </tr>
    <tr>
      <th>712</th>
      <td>Martin</td>
      <td>NaN</td>
      <td>2001-02-06</td>
      <td>2023-08-15 04:17:00</td>
      <td>123963</td>
      <td>15.745</td>
      <td>True</td>
      <td>Engineering</td>
    </tr>
    <tr>
      <th>749</th>
      <td>Janet</td>
      <td>NaN</td>
      <td>1986-01-25</td>
      <td>2023-08-15 05:48:00</td>
      <td>85789</td>
      <td>9.712</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>832</th>
      <td>Keith</td>
      <td>Male</td>
      <td>2003-02-12</td>
      <td>2023-08-15 15:02:00</td>
      <td>120672</td>
      <td>19.467</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
    <tr>
      <th>855</th>
      <td>Phillip</td>
      <td>NaN</td>
      <td>2003-10-20</td>
      <td>2023-08-15 11:09:00</td>
      <td>89700</td>
      <td>2.277</td>
      <td>True</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>887</th>
      <td>David</td>
      <td>Male</td>
      <td>2009-12-05</td>
      <td>2023-08-15 08:48:00</td>
      <td>92242</td>
      <td>15.407</td>
      <td>False</td>
      <td>Legal</td>
    </tr>
  </tbody>
</table>
<p>201 rows × 8 columns</p>
</div>



### unique(), nunique()


```python
df["Gender"].unique()
```




    ['Male', 'Female', NaN]
    Categories (2, object): ['Female', 'Male']




```python
df["Gender"].nunique() # doesnot count NaN
```




    2




```python
df["Gender"].nunique(dropna=False)
```




    3




```python

```
