# Numpy
# Numpy Array


```python
import numpy as np
```


```python
my_list = [1, 2, 3]
```


```python
# Convert list into an array
np.array(my_list)
```




    array([1, 2, 3])




```python
# Check type
type(np.array(my_list))
```




    numpy.ndarray




```python
# Range Function - Start, Stop, Step
np.arange(0, 10, 2)
```




    array([0, 2, 4, 6, 8])




```python
# Nested list
nested_list = [[1,2], [3,4], [5,6]]
nested_list
```




    [[1, 2], [3, 4], [5, 6]]




```python
# Conversion of nested list into matrix
np.array(nested_list)
```




    array([[1, 2],
           [3, 4],
           [5, 6]])




```python
# Generate zeros of 1 X 3 matrix (1 D vector)
np.zeros(3)
```




    array([0., 0., 0.])




```python
# Define shape (row X col)
np.zeros((4,3))
```




    array([[0., 0., 0.],
           [0., 0., 0.],
           [0., 0., 0.],
           [0., 0., 0.]])




```python
# Generate One's
np.ones((2,3))
```




    array([[1., 1., 1.],
           [1., 1., 1.]])




```python
# Linearly space number generator
np.linspace(0, 10, 3) # generate 3 points evenly spaced between 0 to 10
```




    array([ 0.,  5., 10.])




```python
# Identity matrix
np.eye(5)
```




    array([[1., 0., 0., 0., 0.],
           [0., 1., 0., 0., 0.],
           [0., 0., 1., 0., 0.],
           [0., 0., 0., 1., 0.],
           [0., 0., 0., 0., 1.]])




```python
# Random Number - Uniform Distribution
np.random.rand(2)
```




    array([0.98398256, 0.59237866])




```python
np.random.rand(3, 4) # 3 rows and 4 coloums - Uniform Distribution
```




    array([[0.6029448 , 0.55165709, 0.78211516, 0.87161884],
           [0.76945026, 0.78552375, 0.12243544, 0.17339705],
           [0.89084808, 0.28248178, 0.74656686, 0.19735005]])




```python
# Random Number - Standard Normal Distribution
np.random.randn(3,3)
```




    array([[-0.86067118, -0.20387412, -0.50200183],
           [-1.21751046, -0.76743098,  0.78144595],
           [-0.69014229, -0.36097176,  0.63586237]])




```python
np.random.randint(1,50)
```




    42




```python
np.random.randint(1,50, 5)
```




    array([33, 34, 23, 27,  8])




```python
np.random.randint(1,50, (2,3))
```




    array([[49, 19, 37],
           [35, 25, 26]])




```python
# Generating same random number every time
np.random.seed(77)
np.random.rand(4)
```




    array([0.91910903, 0.6421956 , 0.75371223, 0.13931457])




```python
# Reshaping of array
myarray = np.arange(0,25)
myarray
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,
           17, 18, 19, 20, 21, 22, 23, 24])




```python
# Get array shape
myarray.shape
```




    (25,)




```python
# Reshape it
myarray.reshape(5,5)
```




    array([[ 0,  1,  2,  3,  4],
           [ 5,  6,  7,  8,  9],
           [10, 11, 12, 13, 14],
           [15, 16, 17, 18, 19],
           [20, 21, 22, 23, 24]])




```python
# Min, Max, Index
ar = np.arange(0,58,3)
ar
```




    array([ 0,  3,  6,  9, 12, 15, 18, 21, 24, 27, 30, 33, 36, 39, 42, 45, 48,
           51, 54, 57])




```python
ar.max()
```




    57




```python
ar.min()
```




    0




```python
# Index of max
ar.argmax()
```




    19




```python
# Index of min
ar.argmin()
```




    0




```python
# Get data type
ar.dtype
```




    dtype('int32')



# Index Selection


```python
arr = np.arange(0, 10)
```


```python
# 0th Element
arr[0]
```




    0




```python
# Starting from element index 1 to 4
arr[1:5]
```




    array([1, 2, 3, 4])




```python
# String from begning go upto index 4
arr[:5]
```




    array([0, 1, 2, 3, 4])




```python
# All the way to the end
arr[0:]
```




    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
# Broadcasting
arr[0:5] = 7
```


```python
arr # broadcasted 7
```




    array([7, 7, 7, 7, 7, 5, 6, 7, 8, 9])




```python
# Arrays are of Object of Reference Type

arr = np.arange(1,10)
arr
```




    array([1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
slice_of_arr = arr[0:4]
slice_of_arr
```




    array([1, 2, 3, 4])




```python
slice_of_arr[:] = 7
```


```python
arr  # Broadcasted the object of reference type
```




    array([7, 7, 7, 7, 5, 6, 7, 8, 9])




```python
# To get a copy of array use copy() method.

copy_of_arr = arr.copy()
copy_of_arr
```




    array([7, 7, 7, 7, 5, 6, 7, 8, 9])




```python
# 2d Arrays

arr_2d = np.array([[1,2,3], [4,5,6], [7,8,9]])
arr_2d
```




    array([[1, 2, 3],
           [4, 5, 6],
           [7, 8, 9]])




```python
arr_2d.shape
```




    (3, 3)




```python
# Get first row
arr_2d[0]
```




    array([1, 2, 3])




```python
arr_2d[1,1] # arr_2d[1][1]
```




    5




```python
# get rows starting from 0 to 1 index (2 is excluded)
arr_2d[:2]
```




    array([[1, 2, 3],
           [4, 5, 6]])




```python
# Get first two rows and last 2 cols
arr_2d[:2, 1:]
```




    array([[2, 3],
           [5, 6]])




```python
# Features of broadcasting
# START -----------------------
arr = np.arange(1,10)
arr
```




    array([1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
bool_arr = arr > 4
bool_arr
```




    array([False, False, False, False,  True,  True,  True,  True,  True])




```python
# pass this bool_arr to our arr
arr[bool_arr]
```




    array([5, 6, 7, 8, 9])




```python
# END -----------------------
```


```python
# We can accomplish above situation using one statement.
arr[arr>4]
```




    array([5, 6, 7, 8, 9])



# Numpy Operations


```python
arr
```




    array([1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
arr + 5
```




    array([ 6,  7,  8,  9, 10, 11, 12, 13, 14])




```python
# Division by error

# 0 / 1 --> nan
# 1 / 0 --> inf
```


```python
# 2d reshaping
arr2d = np.arange(0,25).reshape(5,5)
```


```python
arr2d
```




    array([[ 0,  1,  2,  3,  4],
           [ 5,  6,  7,  8,  9],
           [10, 11, 12, 13, 14],
           [15, 16, 17, 18, 19],
           [20, 21, 22, 23, 24]])




```python
# Sum of all
arr2d.sum()
```




    300




```python
# Row wise sum
arr2d.sum(axis=0)
```




    array([50, 55, 60, 65, 70])




```python
# Col wise sum
arr2d.sum(axis=1)
```




    array([ 10,  35,  60,  85, 110])


