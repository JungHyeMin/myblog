---
title: Numpy_2
tags: Numpy

---
# Numpy example

## Basic Operations 2 
```bash
A = np.array([[1, 1],
              [0, 1]])
B = np.array([[2, 0],
              [3, 4]])
print(" A*B\n",A * B)
```
### result
 A*B
 [[2 0]
 [0 4]]

A@B
 [[5 4]
 [3 4]]

 A.dat(B)
 [[5 4]
 [3 4]]

 ```bash
rg = np.random.default_rng(1)
a = np.ones((2, 3), dtype=int)
b = rg.random((2, 3))
a *= 3
print("a\n",a)
b += a
print("b\n",b)
```
### result
a
 [[3 3 3]
 [3 3 3]]
b
 [[3.51182162 3.9504637  3.14415961]
 [3.94864945 3.31183145 3.42332645]]

