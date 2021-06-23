---
title: Numpy
tags: Numpy

---

## What is Numpy?

- 행렬 곱셈

- 수치 계산

## What different List and Numpy

### List

``` bash
배열과 배열을 더하면 하나의 배열로 합쳐진다.
```

### Numpy

``` bash
배열과 배열을 더하면 각 배열 값들의 합으로 구성된다.
```

## What is Reshape

``` bash
곱의 값이 같아야함.
-1  : 자동으로 배열값을 찾아준다.
```

## Numpy example
``` bash
import numpy as np

## An example
print("######################################")
print("An example")
a = np.arange(15).reshape(3,5)
print("a:",a)
print("a.shape :",a.shape)
print("a.ndim :",a.ndim)
print("a.dtype.name :",a.dtype.name)
print("a.itemsize :",a.itemsize)
print("a.size : ",a.size)
type(a)
b = np.array([6, 7, 8])
print(b)
type(b)
print("######################################")
## Array Creation
print("Array Creation")
ar = np.array([2, 3, 4])
print("ar : ",ar)
print("ar.dtype : ",ar.dtype)

br = np.array([1.2, 3.5, 5.1])
print("br : ",br)
print("br.dtype : ",br.dtype)
print("######################################")
## Printing Arrays
print("Printing Arrays")
### 1d array
a1 = np.arange(6)
print(a1)
print()
### 2d array
b1 = np.arange(12).reshape(4,3)
print(b1)
print()
### 3d array
c1 = np.arange(24).reshape(2, 3, 4)
print(c1)
print("######################################")

##Basic Operations
print("Basic Operations")
a = np.array([20, 30, 40, 50])
b = np.arange(4)
print(b)

c = a - b
print(c)
print(b**2)
print(10*np.sin(a))
print(a<35)
```


