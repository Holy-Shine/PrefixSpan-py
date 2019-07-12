<a href="https://996.icu"><img src="https://img.shields.io/badge/link-996.icu-red.svg?style=flat-square"></a> <a href='https://pytorch.org/'><img src='https://img.shields.io/badge/python-3.5-green.svg?style=flat-square'></a> [![HitCount](http://hits.dwyl.io/Holy-Shine/PrefixSpan-py.svg)](http://hits.dwyl.io/Holy-Shine/PrefixSpan-py)

# PrefixSpan-py

An implementation of data mining algorithm **PrefixSpan** based on Python.

[Readme中文版](README_CN.md)

Base on paper:

> [PrefixSpan: Mining Sequential Patterns Efficiently by Prefix-Projected Pattern Growth](http://hanj.cs.illinois.edu/pdf/span01.pdf)



## Quick Start

This simple python script **does not rely on any other third-party libraries**. Just confirm that your environment is **Python 3**.  

1. Type code below to import script.

   ```python
   import PrefixSpan
   ```

2. Pack data. Confirm that this data is a 2-D python list whose elements are single char(or int)

   ```python
   data = [
       [1, 4, 2, 3],
       [0, 1, 2, 3],
       [1, 2, 1, 3, 4],
       [2, 1, 2, 4, 4],
       [1, 1, 1, 2, 3],
   ]
   ```

3. Call function PrefixSpan.

   ```python
   L = PrefixSpan.PrefixSpan(data,minSup=0.8,minConf=0)
   ```

   This function return a list that contains bunch of result subsequences(**format: python tuple**).   

   Parameters:

   - minSup: min_support declared in paper, default 0.5
   - minConf: min_confidence, default 0
   
4. Print result.

   ```python
   print(L)
   ```

   **[out]：**

   > [[(1,), (2,), (3,)], [(1, 2), (1, 3), (2, 3)], [(1, 2, 3)], []]

   The length of pattern sequence in result list increases by 1 