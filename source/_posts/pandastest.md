---
title: Pandas
tags: Pandas

---

## What is Pandas?

- 데이터 전처리 모듈

## Why we should use Pandas?
- garbage data -> garbage result

## Pandas example
``` bash
import numpy as np
print("numpy version : ",np.__version__)

import pandas as pd
print("pandas version : ",pd.__version__)
```
![version](/images/version.png)

```bash
## 개체 생성
s = pd.Series([1, 3, 5, np.nan, 6, 8])
print(s)
```
![result1](/images/result1.png)
```bash
## 날짜 시간 numpy 배열 -> DataFrame 만들기
dates = pd.date_range("20210623", periods=6)
print(dates)
print()
```
![result2](/images/result2.png)

```bash
df = pd.DataFrame(np.random.randn(6,4), index=dates, columns=list("ABCD"))
print(df)
print()
```
![result3](/images/result3.png)
```bash
## Series ->  DataFrame
df2 = pd.DataFrame(
    {
        "A": 1.0,
        "B": pd.Timestamp("20210623"),
        "C":pd.Series(1, index=list(range(4)), dtype="float32"),
        "D": np.array([3] * 4, dtype="int32"),
        "E":pd.Categorical(["test", "train", "test", "train"]),
        "F": "foo",
    }  
)

print(df2,"\n")
print(df2.dtypes)
```
![result4](/images/result4.png)

```bash
## 데이터 보기
print(df.head())
print(df.tail(3))
print()
```
![result5](/images/result5.png)

```bash
## index, columns
print(df.index)
print(df.columns)
print()
```
![result6](/images/result6.png)

```bash
## 데이터 통계 요약
print(df.describe())
print()
![result7](/images/result7.png)
```


