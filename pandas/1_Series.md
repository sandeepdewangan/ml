# Series


```python
import pandas as pd
```

### Creating Series using Lists


```python
ice_cream = ["Chocholate", "Valina", "Strawberry", "Rum"]
pd.Series(ice_cream)
```




    0    Chocholate
    1        Valina
    2    Strawberry
    3           Rum
    dtype: object




```python
lottery = [4,8,15,16,23,42]
pd.Series(lottery)
```




    0     4
    1     8
    2    15
    3    16
    4    23
    5    42
    dtype: int64



### Creating Series using Dictionary


```python
food = {
    "Tomato": "Tamatar",
    "Potato": "Aalu",
    "Brinjal": "Bhata"
}
pd.Series(food)
```




    Tomato     Tamatar
    Potato        Aalu
    Brinjal      Bhata
    dtype: object



### Methods


```python
"hello".upper() # donot mutates
```




    'HELLO'




```python
data = [1,2,3]
data.append(4) # mutates
data
```




    [1, 2, 3, 4]




```python
prices = pd.Series([2.5, 3.5, 3.3])
prices
```




    0    2.5
    1    3.5
    2    3.3
    dtype: float64




```python
prices.sum()
```




    9.3




```python
prices.product()
```




    28.875




```python
prices.mean()
```




    3.1



### Atrributes


```python
adjectives = pd.Series(["Smart", "Intelligent", "Humble", "Brilliant"])
adjectives
```




    0          Smart
    1    Intelligent
    2         Humble
    3      Brilliant
    dtype: object




```python
adjectives.size
```




    4




```python
adjectives.is_unique
```




    True




```python
# returns as numpy array
adjectives.values
```




    array(['Smart', 'Intelligent', 'Humble', 'Brilliant'], dtype=object)




```python
type(adjectives.values)
```




    numpy.ndarray




```python
adjectives.index
```




    RangeIndex(start=0, stop=4, step=1)




```python
adjectives.dtype
```




    dtype('O')



### Parameters and Arguments


```python
fruits = ["Apple", "Pineapple", "Banana", "Vanila", "Pears"]
weekdays = ["Monday", "Tuesday", "Wednesday", "Thusday", "Friday"]
pd.Series(data=fruits, index=weekdays)
```




    Monday           Apple
    Tuesday      Pineapple
    Wednesday       Banana
    Thusday         Vanila
    Friday           Pears
    dtype: object



### Import Series with the pd.read_csv Function


```python
pd.read_csv("datasets\pokemon.csv")
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
      <th>Pokemon</th>
      <th>Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bulbasaur</td>
      <td>Grass</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ivysaur</td>
      <td>Grass</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Venusaur</td>
      <td>Grass</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Charmander</td>
      <td>Fire</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Charmeleon</td>
      <td>Fire</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>716</th>
      <td>Yveltal</td>
      <td>Dark</td>
    </tr>
    <tr>
      <th>717</th>
      <td>Zygarde</td>
      <td>Dragon</td>
    </tr>
    <tr>
      <th>718</th>
      <td>Diancie</td>
      <td>Rock</td>
    </tr>
    <tr>
      <th>719</th>
      <td>Hoopa</td>
      <td>Psychic</td>
    </tr>
    <tr>
      <th>720</th>
      <td>Volcanion</td>
      <td>Fire</td>
    </tr>
  </tbody>
</table>
<p>721 rows × 2 columns</p>
</div>




```python
# squeeze will convert csv into Series
pokemon = pd.read_csv("datasets\pokemon.csv", usecols=["Pokemon"]).squeeze() 
pokemon
```




    0       Bulbasaur
    1         Ivysaur
    2        Venusaur
    3      Charmander
    4      Charmeleon
              ...    
    716       Yveltal
    717       Zygarde
    718       Diancie
    719         Hoopa
    720     Volcanion
    Name: Pokemon, Length: 721, dtype: object



### Head and Tail


```python
pokemon.head()
```




    0     Bulbasaur
    1       Ivysaur
    2      Venusaur
    3    Charmander
    4    Charmeleon
    Name: Pokemon, dtype: object




```python
pokemon.head(10)
```




    0     Bulbasaur
    1       Ivysaur
    2      Venusaur
    3    Charmander
    4    Charmeleon
    5     Charizard
    6      Squirtle
    7     Wartortle
    8     Blastoise
    9      Caterpie
    Name: Pokemon, dtype: object




```python
pokemon.tail()
```




    716      Yveltal
    717      Zygarde
    718      Diancie
    719        Hoopa
    720    Volcanion
    Name: Pokemon, dtype: object



### Passing Series to Python Functions


```python
pokemon = pd.read_csv("datasets\pokemon.csv", usecols=["Pokemon"]).squeeze() 
```


```python
type(pokemon)
```




    pandas.core.series.Series




```python
# List of all operations that can be performed
# dir(pokemon)
```


```python
# Sorting
# sorted(pokemon)
```


```python
pokemon
```




    0       Bulbasaur
    1         Ivysaur
    2        Venusaur
    3      Charmander
    4      Charmeleon
              ...    
    716       Yveltal
    717       Zygarde
    718       Diancie
    719         Hoopa
    720     Volcanion
    Name: Pokemon, Length: 721, dtype: object




```python
# Sorting Series without changing type of output
pokemon.sort_values()
```




    459    Abomasnow
    62          Abra
    358        Absol
    616     Accelgor
    680    Aegislash
             ...    
    570      Zoroark
    569        Zorua
    40         Zubat
    633     Zweilous
    717      Zygarde
    Name: Pokemon, Length: 721, dtype: object




```python
# Creating series with index_col
pokemon = pd.read_csv("datasets\pokemon.csv", index_col="Pokemon").squeeze()
pokemon
```




    Pokemon
    Bulbasaur       Grass
    Ivysaur         Grass
    Venusaur        Grass
    Charmander       Fire
    Charmeleon       Fire
                   ...   
    Yveltal          Dark
    Zygarde        Dragon
    Diancie          Rock
    Hoopa         Psychic
    Volcanion        Fire
    Name: Type, Length: 721, dtype: object




```python
# sort by index
pokemon.sort_index()
```




    Pokemon
    Abomasnow      Grass
    Abra         Psychic
    Absol           Dark
    Accelgor         Bug
    Aegislash      Steel
                  ...   
    Zoroark         Dark
    Zorua           Dark
    Zubat         Poison
    Zweilous        Dark
    Zygarde       Dragon
    Name: Type, Length: 721, dtype: object



### Inclusion - check for a value exists or not


```python
pokemon = pd.read_csv("datasets\pokemon.csv", usecols=["Pokemon"]).squeeze()
pokemon
```




    0       Bulbasaur
    1         Ivysaur
    2        Venusaur
    3      Charmander
    4      Charmeleon
              ...    
    716       Yveltal
    717       Zygarde
    718       Diancie
    719         Hoopa
    720     Volcanion
    Name: Pokemon, Length: 721, dtype: object




```python
# check, # False bez, by default pandas check in index.
"Bulbasaur" in pokemon
```




    False




```python
100 in pokemon
```




    True




```python
# .values will display all the list
# pokemon.values
```


```python
"Bulbasaur" in pokemon.values
```




    True



### Extract Series Values by Index Position


```python
pokemon = pd.read_csv("datasets\pokemon.csv", usecols=["Pokemon"]).squeeze()
pokemon
```




    0       Bulbasaur
    1         Ivysaur
    2        Venusaur
    3      Charmander
    4      Charmeleon
              ...    
    716       Yveltal
    717       Zygarde
    718       Diancie
    719         Hoopa
    720     Volcanion
    Name: Pokemon, Length: 721, dtype: object




```python
pokemon[0]
```




    'Bulbasaur'




```python
# Multiple value pull out
pokemon[[100, 200, 300]]
```




    100    Electrode
    200        Unown
    300     Delcatty
    Name: Pokemon, dtype: object



### Extract Series Values by Index Label


```python
pokemon = pd.read_csv("datasets\pokemon.csv", index_col="Pokemon").squeeze()
pokemon
```




    Pokemon
    Bulbasaur       Grass
    Ivysaur         Grass
    Venusaur        Grass
    Charmander       Fire
    Charmeleon       Fire
                   ...   
    Yveltal          Dark
    Zygarde        Dragon
    Diancie          Rock
    Hoopa         Psychic
    Volcanion        Fire
    Name: Type, Length: 721, dtype: object




```python
pokemon[0] # will work
```




    'Grass'




```python
pokemon["Bulbasaur"]
```




    'Grass'



### Get Method


```python
# get method is more efficient than [] method
```


```python
pokemon = pd.read_csv("datasets\pokemon.csv", index_col="Pokemon").squeeze()
pokemon
```




    Pokemon
    Bulbasaur       Grass
    Ivysaur         Grass
    Venusaur        Grass
    Charmander       Fire
    Charmeleon       Fire
                   ...   
    Yveltal          Dark
    Zygarde        Dragon
    Diancie          Rock
    Hoopa         Psychic
    Volcanion        Fire
    Name: Type, Length: 721, dtype: object




```python
pokemon.get(0)
```




    'Grass'




```python
# pokemon["Sandeep"]
# displays error
```


```python
print(pokemon.get("Sandeep")) # donot display error
```

    None
    


```python
# we can specify what to display if error occurs
pokemon.get("Sandeep", "Item Not Found")
```




    'Item Not Found'



### Override Series Values


```python
pokemon = pd.read_csv("datasets\pokemon.csv", usecols=["Pokemon"]).squeeze()
pokemon
```




    0       Bulbasaur
    1         Ivysaur
    2        Venusaur
    3      Charmander
    4      Charmeleon
              ...    
    716       Yveltal
    717       Zygarde
    718       Diancie
    719         Hoopa
    720     Volcanion
    Name: Pokemon, Length: 721, dtype: object




```python
# changing value
pokemon[0] = 'Sandeep'
```


```python
pokemon.head()
```




    0       Sandeep
    1       Ivysaur
    2      Venusaur
    3    Charmander
    4    Charmeleon
    Name: Pokemon, dtype: object




```python
# if we try to override the index values which do not exits then it will add
pokemon[1500] = 'Sandy'
```


```python
pokemon.tail()
```




    717       Zygarde
    718       Diancie
    719         Hoopa
    720     Volcanion
    1500        Sandy
    Name: Pokemon, dtype: object




```python
pokemon[[1,2,3]] = ["Cherry", "Zozo", "Unnati"]
```


```python
pokemon.head()
```




    0       Sandeep
    1        Cherry
    2          Zozo
    3        Unnati
    4    Charmeleon
    Name: Pokemon, dtype: object



### Copy method


```python
pokemon_df = pd.read_csv("datasets\pokemon.csv", usecols=["Pokemon"])
pokemon_series = pokemon_df.squeeze().copy()
```

### Inplace parameter


```python
google = (
    pd.read_csv("datasets\google_stock_price.csv", usecols=["Stock Price"])
    .squeeze()
    .copy()
)
```


```python
google
```




    0        50.12
    1        54.10
    2        54.65
    3        52.38
    4        52.95
             ...  
    3007    772.88
    3008    771.07
    3009    773.18
    3010    771.61
    3011    782.22
    Name: Stock Price, Length: 3012, dtype: float64




```python
google = google.sort_values()
google
```




    11       49.95
    9        50.07
    0        50.12
    10       50.70
    12       50.74
             ...  
    3010    771.61
    3007    772.88
    3009    773.18
    2859    776.60
    3011    782.22
    Name: Stock Price, Length: 3012, dtype: float64




```python
google.sort_values(inplace=True) # sort the series in place without assignment
```

### Math methods on Series


```python
google.count()
```




    3012




```python
google.sum()
```




    1006942.0




```python
google.mean()
```




    334.3100929614874




```python
google.describe()
```




    count    3012.000000
    mean      334.310093
    std       173.187205
    min        49.950000
    25%       218.045000
    50%       283.315000
    75%       443.000000
    max       782.220000
    Name: Stock Price, dtype: float64



### Broadcasting


```python
# Applying math operation to every values is broadcasting
```


```python
google.head()
```




    11    49.95
    9     50.07
    0     50.12
    10    50.70
    12    50.74
    Name: Stock Price, dtype: float64




```python
google + 10
```




    11       59.95
    9        60.07
    0        60.12
    10       60.70
    12       60.74
             ...  
    3010    781.61
    3007    782.88
    3009    783.18
    2859    786.60
    3011    792.22
    Name: Stock Price, Length: 3012, dtype: float64



### Value_count method


```python
pokemon = pd.read_csv("datasets\pokemon.csv", index_col=["Pokemon"]).squeeze()
pokemon
```




    Pokemon
    Bulbasaur       Grass
    Ivysaur         Grass
    Venusaur        Grass
    Charmander       Fire
    Charmeleon       Fire
                   ...   
    Yveltal          Dark
    Zygarde        Dragon
    Diancie          Rock
    Hoopa         Psychic
    Volcanion        Fire
    Name: Type, Length: 721, dtype: object




```python
pokemon.value_counts()
```




    Type
    Water       105
    Normal       93
    Grass        66
    Bug          63
    Fire         47
    Psychic      47
    Rock         41
    Electric     36
    Ground       30
    Poison       28
    Dark         28
    Fighting     25
    Dragon       24
    Ghost        23
    Ice          23
    Steel        22
    Fairy        17
    Flying        3
    Name: count, dtype: int64



### apply method


```python
# apply certain method to all the values of series
```


```python
pokemon.apply(len) # return the count of values "Grass" -> 5
```




    Pokemon
    Bulbasaur     5
    Ivysaur       5
    Venusaur      5
    Charmander    4
    Charmeleon    4
                 ..
    Yveltal       4
    Zygarde       6
    Diancie       4
    Hoopa         7
    Volcanion     4
    Name: Type, Length: 721, dtype: int64




```python
# Custom apply
def my_custom_pokemon(pokemon_type):
    if pokemon_type in ["Grass"]:
        return "Hahaha"
    else:
        return pokemon_type
```


```python
pokemon.head()
```




    Pokemon
    Bulbasaur     Grass
    Ivysaur       Grass
    Venusaur      Grass
    Charmander     Fire
    Charmeleon     Fire
    Name: Type, dtype: object




```python
pokemon.apply(my_custom_pokemon)
```




    Pokemon
    Bulbasaur      Hahaha
    Ivysaur        Hahaha
    Venusaur       Hahaha
    Charmander       Fire
    Charmeleon       Fire
                   ...   
    Yveltal          Dark
    Zygarde        Dragon
    Diancie          Rock
    Hoopa         Psychic
    Volcanion        Fire
    Name: Type, Length: 721, dtype: object



### Map method


```python
pokemon = pd.read_csv("datasets\pokemon.csv", index_col=["Pokemon"]).squeeze()
pokemon
```




    Pokemon
    Bulbasaur       Grass
    Ivysaur         Grass
    Venusaur        Grass
    Charmander       Fire
    Charmeleon       Fire
                   ...   
    Yveltal          Dark
    Zygarde        Dragon
    Diancie          Rock
    Hoopa         Psychic
    Volcanion        Fire
    Name: Type, Length: 721, dtype: object




```python
mappings = {
    "Grass": "New Grass",
    "Fire": "Hot Fire",
}
mapping_series = pd.Series(mappings)
mapping_series
```




    Grass    New Grass
    Fire      Hot Fire
    dtype: object




```python
pokemon.map(mapping_series)
```




    Pokemon
    Bulbasaur     New Grass
    Ivysaur       New Grass
    Venusaur      New Grass
    Charmander     Hot Fire
    Charmeleon     Hot Fire
                    ...    
    Yveltal             NaN
    Zygarde             NaN
    Diancie             NaN
    Hoopa               NaN
    Volcanion      Hot Fire
    Name: Type, Length: 721, dtype: object




```python

```
