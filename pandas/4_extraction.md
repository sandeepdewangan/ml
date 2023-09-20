# Data Extraction


```python
import pandas as pd
```


```python
bond = pd.read_csv("datasets\jamesbond.csv")
```


```python
bond.head()
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
      <th>Film</th>
      <th>Year</th>
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Dr. No</td>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>From Russia with Love</td>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Goldfinger</td>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Thunderball</td>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Casino Royale</td>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### set_index and reset_index methods


```python
bond = pd.read_csv("datasets\jamesbond.csv", index_col="Film")
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>From Russia with Love</th>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>Goldfinger</th>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>Thunderball</th>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# OR using method
# benificial when multiple index needed
```


```python
bond = bond.set_index(keys="Film")
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>From Russia with Love</th>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>Goldfinger</th>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>Thunderball</th>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# reset index back to numeric
bond = bond.reset_index()
```


```python
bond.head()
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
      <th>Film</th>
      <th>Year</th>
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Dr. No</td>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>From Russia with Love</td>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Goldfinger</td>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Thunderball</td>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Casino Royale</td>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### Retrive rows by loc


```python
bond = pd.read_csv("datasets\jamesbond.csv", index_col="Film")
# make sure the dataset is sorted to improve perfromance before making query for row retrieval
bond = bond.sort_index()
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.loc['Casino Royale']
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.loc["Casini Royale":"Dr. No"] # for index labels Ending point is inclusive
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
  </tbody>
</table>
</div>




```python
# skipping 
bond.loc["Casini Royale":"Dr. No":2]
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
  </tbody>
</table>
</div>




```python
# retrive multiple label rows
bond.loc[["Casino Royale", "Diamonds Are Forever"]]
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
  </tbody>
</table>
</div>



### in operator


```python
"Casino Royale" in bond.index
```




    True



### Retrieve rows by its index pos with iloc


```python
bond = pd.read_csv("datasets\jamesbond.csv")
bond.head()
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
      <th>Film</th>
      <th>Year</th>
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Dr. No</td>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>From Russia with Love</td>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Goldfinger</td>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Thunderball</td>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Casino Royale</td>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.iloc[0]
```




    Film                        Dr. No
    Year                          1962
    Actor                 Sean Connery
    Director             Terence Young
    Box Office                   448.8
    Budget                         7.0
    Bond Actor Salary              0.6
    Name: 0, dtype: object




```python
bond.iloc[0:6]
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
      <th>Film</th>
      <th>Year</th>
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Dr. No</td>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>From Russia with Love</td>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Goldfinger</td>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Thunderball</td>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Casino Royale</td>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>You Only Live Twice</td>
      <td>1967</td>
      <td>Sean Connery</td>
      <td>Lewis Gilbert</td>
      <td>514.2</td>
      <td>59.9</td>
      <td>4.4</td>
    </tr>
  </tbody>
</table>
</div>




```python
# selecting rows and columns
bond.iloc[0:6, 2:4]
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
      <th>Actor</th>
      <th>Director</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Sean Connery</td>
      <td>Terence Young</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Sean Connery</td>
      <td>Terence Young</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Sean Connery</td>
      <td>Terence Young</td>
    </tr>
    <tr>
      <th>4</th>
      <td>David Niven</td>
      <td>Ken Hughes</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Sean Connery</td>
      <td>Lewis Gilbert</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.iloc[[1,2,3]]
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
      <th>Film</th>
      <th>Year</th>
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>From Russia with Love</td>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Goldfinger</td>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Thunderball</td>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.iloc[14,2]
```




    'Roger Moore'



### Arguments to loc and iloc


```python
bond = pd.read_csv("datasets\jamesbond.csv", index_col="Film")
bond = bond.sort_index()
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.loc["Casino Royale", "Actor"]
```




    Film
    Casino Royale    Daniel Craig
    Casino Royale     David Niven
    Name: Actor, dtype: object




```python
bond.loc["Die Another Day", "Actor"]
```




    'Pierce Brosnan'




```python
bond.loc["Die Another Day", ["Actor", "Budget"]]
```




    Actor     Pierce Brosnan
    Budget             154.2
    Name: Die Another Day, dtype: object




```python
bond.loc["Casino Royale", ["Actor", "Budget"]]
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
      <th>Actor</th>
      <th>Budget</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>Daniel Craig</td>
      <td>145.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>David Niven</td>
      <td>85.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Range, slicing
bond.loc["Casino Royale", "Actor":"Budget"]
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
### Set new value for a specific cells
```


```python
bond = pd.read_csv("datasets\jamesbond.csv", index_col="Film")
bond = bond.sort_index()
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.loc["Casino Royale", "Actor"] = "Hritik Roshan"
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Hritik Roshan</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>Hritik Roshan</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.loc["A View to a Kill", ["Actor", "Director"]] = ["Shahid Kapoor", "Priyadarshan"]
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Shahid Kapoor</td>
      <td>Priyadarshan</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Hritik Roshan</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>Hritik Roshan</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>



### Set multiple values in Dataframes


```python
bond = pd.read_csv("datasets\jamesbond.csv", index_col="Film")
bond = bond.sort_index()
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
actor_is_sean_connery = bond["Actor"] == "Sean Connery"
actor_is_sean_connery.head()
```




    Film
    A View to a Kill        False
    Casino Royale           False
    Casino Royale           False
    Diamonds Are Forever     True
    Die Another Day         False
    Name: Actor, dtype: bool




```python
bond.loc[actor_is_sean_connery, "Actor"] = "Sir Sean Connery"
bond
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sir Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sir Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>For Your Eyes Only</th>
      <td>1981</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>449.4</td>
      <td>60.2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>From Russia with Love</th>
      <td>1963</td>
      <td>Sir Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>GoldenEye</th>
      <td>1995</td>
      <td>Pierce Brosnan</td>
      <td>Martin Campbell</td>
      <td>518.5</td>
      <td>76.9</td>
      <td>5.1</td>
    </tr>
    <tr>
      <th>Goldfinger</th>
      <td>1964</td>
      <td>Sir Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>Licence to Kill</th>
      <td>1989</td>
      <td>Timothy Dalton</td>
      <td>John Glen</td>
      <td>250.9</td>
      <td>56.7</td>
      <td>7.9</td>
    </tr>
    <tr>
      <th>Live and Let Die</th>
      <td>1973</td>
      <td>Roger Moore</td>
      <td>Guy Hamilton</td>
      <td>460.3</td>
      <td>30.8</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Moonraker</th>
      <td>1979</td>
      <td>Roger Moore</td>
      <td>Lewis Gilbert</td>
      <td>535.0</td>
      <td>91.5</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Never Say Never Again</th>
      <td>1983</td>
      <td>Sir Sean Connery</td>
      <td>Irvin Kershner</td>
      <td>380.0</td>
      <td>86.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Octopussy</th>
      <td>1983</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>373.8</td>
      <td>53.9</td>
      <td>7.8</td>
    </tr>
    <tr>
      <th>On Her Majesty's Secret Service</th>
      <td>1969</td>
      <td>George Lazenby</td>
      <td>Peter R. Hunt</td>
      <td>291.5</td>
      <td>37.3</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>Quantum of Solace</th>
      <td>2008</td>
      <td>Daniel Craig</td>
      <td>Marc Forster</td>
      <td>514.2</td>
      <td>181.4</td>
      <td>8.1</td>
    </tr>
    <tr>
      <th>Skyfall</th>
      <td>2012</td>
      <td>Daniel Craig</td>
      <td>Sam Mendes</td>
      <td>943.5</td>
      <td>170.2</td>
      <td>14.5</td>
    </tr>
    <tr>
      <th>Spectre</th>
      <td>2015</td>
      <td>Daniel Craig</td>
      <td>Sam Mendes</td>
      <td>726.7</td>
      <td>206.3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>The Living Daylights</th>
      <td>1987</td>
      <td>Timothy Dalton</td>
      <td>John Glen</td>
      <td>313.5</td>
      <td>68.8</td>
      <td>5.2</td>
    </tr>
    <tr>
      <th>The Man with the Golden Gun</th>
      <td>1974</td>
      <td>Roger Moore</td>
      <td>Guy Hamilton</td>
      <td>334.0</td>
      <td>27.7</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>The Spy Who Loved Me</th>
      <td>1977</td>
      <td>Roger Moore</td>
      <td>Lewis Gilbert</td>
      <td>533.0</td>
      <td>45.1</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>The World Is Not Enough</th>
      <td>1999</td>
      <td>Pierce Brosnan</td>
      <td>Michael Apted</td>
      <td>439.5</td>
      <td>158.3</td>
      <td>13.5</td>
    </tr>
    <tr>
      <th>Thunderball</th>
      <td>1965</td>
      <td>Sir Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>Tomorrow Never Dies</th>
      <td>1997</td>
      <td>Pierce Brosnan</td>
      <td>Roger Spottiswoode</td>
      <td>463.2</td>
      <td>133.9</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>You Only Live Twice</th>
      <td>1967</td>
      <td>Sir Sean Connery</td>
      <td>Lewis Gilbert</td>
      <td>514.2</td>
      <td>59.9</td>
      <td>4.4</td>
    </tr>
  </tbody>
</table>
</div>



### Rename index or cols labels


```python
bond = pd.read_csv("datasets\jamesbond.csv", index_col="Film")
bond = bond.sort_index()
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond = bond.rename(mapper={"GoldenEye":"BlackEye", 
                    "A View to a Kill": "A Plot to a Kill"})
# OR
bond = bond.rename(index={"GoldenEye":"BlackEye", 
                    "A View to a Kill": "A Plot to a Kill"})
```


```python
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A Plot to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.rename(mapper={'Year':'Which Year?'}).head()
# this will not work bez by default pandas will check in rows
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A Plot to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.rename(columns={'Year':'Which Year?'}).head()
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
      <th>Which Year?</th>
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A Plot to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.columns
```




    Index(['Year', 'Actor', 'Director', 'Box Office', 'Budget',
           'Bond Actor Salary'],
          dtype='object')




```python
# change all the columns in one shot
bond.columns = ["Which Year?", "Actor", "Director", "Box Office India", "Budget", "Bond Actor Salary?"]
bond.head()
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
      <th>Which Year?</th>
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office India</th>
      <th>Budget</th>
      <th>Bond Actor Salary?</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A Plot to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>



### Delete rows and cols


```python
bond = pd.read_csv("datasets\jamesbond.csv", index_col="Film")
bond = bond.sort_index()
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond = bond.drop("A View to a Kill")
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
  </tbody>
</table>
</div>




```python
# droping using cols
bond = bond.drop("Year", axis="columns") #1 vertical axis, cols
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
    <tr>
      <th>Dr. No</th>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
  </tbody>
</table>
</div>




```python
# del
del bond["Actor"]
```


```python
bond.head()
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
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
    <tr>
      <th>Dr. No</th>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
  </tbody>
</table>
</div>



### Retrieve random samples


```python
bond = pd.read_csv("datasets\jamesbond.csv", index_col="Film")
bond = bond.sort_index()
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.sample(n=5)
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>From Russia with Love</th>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>Octopussy</th>
      <td>1983</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>373.8</td>
      <td>53.9</td>
      <td>7.8</td>
    </tr>
    <tr>
      <th>Spectre</th>
      <td>2015</td>
      <td>Daniel Craig</td>
      <td>Sam Mendes</td>
      <td>726.7</td>
      <td>206.3</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.sample(frac=.25) # 25%
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Tomorrow Never Dies</th>
      <td>1997</td>
      <td>Pierce Brosnan</td>
      <td>Roger Spottiswoode</td>
      <td>463.2</td>
      <td>133.9</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>The Spy Who Loved Me</th>
      <td>1977</td>
      <td>Roger Moore</td>
      <td>Lewis Gilbert</td>
      <td>533.0</td>
      <td>45.1</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>GoldenEye</th>
      <td>1995</td>
      <td>Pierce Brosnan</td>
      <td>Martin Campbell</td>
      <td>518.5</td>
      <td>76.9</td>
      <td>5.1</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
    <tr>
      <th>For Your Eyes Only</th>
      <td>1981</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>449.4</td>
      <td>60.2</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### nsmallest, nlargest methods


```python
bond.nlargest(3, columns="Year")
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Spectre</th>
      <td>2015</td>
      <td>Daniel Craig</td>
      <td>Sam Mendes</td>
      <td>726.7</td>
      <td>206.3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Skyfall</th>
      <td>2012</td>
      <td>Daniel Craig</td>
      <td>Sam Mendes</td>
      <td>943.5</td>
      <td>170.2</td>
      <td>14.5</td>
    </tr>
    <tr>
      <th>Quantum of Solace</th>
      <td>2008</td>
      <td>Daniel Craig</td>
      <td>Marc Forster</td>
      <td>514.2</td>
      <td>181.4</td>
      <td>8.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.nsmallest(3, columns="Year")
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>From Russia with Love</th>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>Goldfinger</th>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
  </tbody>
</table>
</div>



### Filtering with where


```python
filter = bond["Actor"] == 'Sean Connery'
bond[filter]
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>From Russia with Love</th>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>Goldfinger</th>
      <td>1964</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>Never Say Never Again</th>
      <td>1983</td>
      <td>Sean Connery</td>
      <td>Irvin Kershner</td>
      <td>380.0</td>
      <td>86.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Thunderball</th>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>You Only Live Twice</th>
      <td>1967</td>
      <td>Sean Connery</td>
      <td>Lewis Gilbert</td>
      <td>514.2</td>
      <td>59.9</td>
      <td>4.4</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.where(filter)
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box Office</th>
      <th>Budget</th>
      <th>Bond Actor Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971.0</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Dr. No</th>
      <td>1962.0</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>For Your Eyes Only</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>From Russia with Love</th>
      <td>1963.0</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>GoldenEye</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Goldfinger</th>
      <td>1964.0</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>820.4</td>
      <td>18.6</td>
      <td>3.2</td>
    </tr>
    <tr>
      <th>Licence to Kill</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Live and Let Die</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Moonraker</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Never Say Never Again</th>
      <td>1983.0</td>
      <td>Sean Connery</td>
      <td>Irvin Kershner</td>
      <td>380.0</td>
      <td>86.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Octopussy</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>On Her Majesty's Secret Service</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Quantum of Solace</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Skyfall</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Spectre</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>The Living Daylights</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>The Man with the Golden Gun</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>The Spy Who Loved Me</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>The World Is Not Enough</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Thunderball</th>
      <td>1965.0</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
    <tr>
      <th>Tomorrow Never Dies</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>You Only Live Twice</th>
      <td>1967.0</td>
      <td>Sean Connery</td>
      <td>Lewis Gilbert</td>
      <td>514.2</td>
      <td>59.9</td>
      <td>4.4</td>
    </tr>
  </tbody>
</table>
</div>



### filter using query method


```python
bond.columns = [column_name.replace(" ", "_") for column_name in bond.columns]
```


```python
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box_Office</th>
      <th>Budget</th>
      <th>Bond_Actor_Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>54.5</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>145.3</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>85.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>34.7</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>154.2</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
bond.query("Actor == 'Sean Connery'")
bond.query("Actor == 'Sean Connery' and Director=='Terence Young'")
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box_Office</th>
      <th>Budget</th>
      <th>Bond_Actor_Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Dr. No</th>
      <td>1962</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>448.8</td>
      <td>7.0</td>
      <td>0.6</td>
    </tr>
    <tr>
      <th>From Russia with Love</th>
      <td>1963</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>543.8</td>
      <td>12.6</td>
      <td>1.6</td>
    </tr>
    <tr>
      <th>Thunderball</th>
      <td>1965</td>
      <td>Sean Connery</td>
      <td>Terence Young</td>
      <td>848.1</td>
      <td>41.9</td>
      <td>4.7</td>
    </tr>
  </tbody>
</table>
</div>



### apply method


```python
# apply method applies some kind of transformation to dataset values
```


```python
# 1- Passing Column
```


```python
def convert_budget_to_inr(number):
    return str(number * 74) + " INR"
```


```python
bond["Budget"] = bond["Budget"].apply(convert_budget_to_inr)
bond.head()
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
      <th>Actor</th>
      <th>Director</th>
      <th>Box_Office</th>
      <th>Budget</th>
      <th>Bond_Actor_Salary</th>
    </tr>
    <tr>
      <th>Film</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A View to a Kill</th>
      <td>1985</td>
      <td>Roger Moore</td>
      <td>John Glen</td>
      <td>275.2</td>
      <td>4033.0 INR</td>
      <td>9.1</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>2006</td>
      <td>Daniel Craig</td>
      <td>Martin Campbell</td>
      <td>581.5</td>
      <td>10752.2 INR</td>
      <td>3.3</td>
    </tr>
    <tr>
      <th>Casino Royale</th>
      <td>1967</td>
      <td>David Niven</td>
      <td>Ken Hughes</td>
      <td>315.0</td>
      <td>6290.0 INR</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Diamonds Are Forever</th>
      <td>1971</td>
      <td>Sean Connery</td>
      <td>Guy Hamilton</td>
      <td>442.5</td>
      <td>2567.8 INR</td>
      <td>5.8</td>
    </tr>
    <tr>
      <th>Die Another Day</th>
      <td>2002</td>
      <td>Pierce Brosnan</td>
      <td>Lee Tamahori</td>
      <td>465.4</td>
      <td>11410.8 INR</td>
      <td>17.9</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 2- Passing Row
```


```python
def good_movie(row):
    actor = row[1]
    budget = row[4]

    if actor == "Pierce Brosnan":
        return "The BEST"
```


```python
bond.apply(good_movie, axis="columns")
```




    Film
    A View to a Kill                       None
    Casino Royale                          None
    Casino Royale                          None
    Diamonds Are Forever                   None
    Die Another Day                    The BEST
    Dr. No                                 None
    For Your Eyes Only                     None
    From Russia with Love                  None
    GoldenEye                          The BEST
    Goldfinger                             None
    Licence to Kill                        None
    Live and Let Die                       None
    Moonraker                              None
    Never Say Never Again                  None
    Octopussy                              None
    On Her Majesty's Secret Service        None
    Quantum of Solace                      None
    Skyfall                                None
    Spectre                                None
    The Living Daylights                   None
    The Man with the Golden Gun            None
    The Spy Who Loved Me                   None
    The World Is Not Enough            The BEST
    Thunderball                            None
    Tomorrow Never Dies                The BEST
    You Only Live Twice                    None
    dtype: object



### copy method


```python
director = bond["Director"].copy()
```


```python
director.head()
```




    Film
    A View to a Kill              John Glen
    Casino Royale           Martin Campbell
    Casino Royale                Ken Hughes
    Diamonds Are Forever       Guy Hamilton
    Die Another Day            Lee Tamahori
    Name: Director, dtype: object




```python

```
