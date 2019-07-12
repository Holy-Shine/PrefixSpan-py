<a href="https://996.icu"><img src="https://img.shields.io/badge/link-996.icu-red.svg?style=flat-square"></a> <a href='https://pytorch.org/'><img src='https://img.shields.io/badge/python-3.5-green.svg?style=flat-square'></a> [![HitCount](http://hits.dwyl.io/Holy-Shine/PrefixSpan-py.svg)](http://hits.dwyl.io/Holy-Shine/PrefixSpan-py)

# PrefixSpan-py

一个基于Python的数据挖掘算法 **PrefixSpan** 的简单实现。

[Readme English Version](README.md)

基于 paper:

> [PrefixSpan: Mining Sequential Patterns Efficiently by Prefix-Projected Pattern Growth](http://hanj.cs.illinois.edu/pdf/span01.pdf)

代码详细解释：

https://www.cnblogs.com/HolyShine/p/11176843.html

## 快速开始

这个简单的python脚本**不依赖于任何第三方库**。只要确认你的环境是**Python3**即可

1. 导入脚本.

   ```python
   import PrefixSpan
   ```

2. 包装数据. 该数据是一个Python的二维list，其中每个元素是单个字符或者数字.

   ```python
   data = [
       [1, 4, 2, 3],
       [0, 1, 2, 3],
       [1, 2, 1, 3, 4],
       [2, 1, 2, 4, 4],
       [1, 1, 1, 2, 3],
   ]
   ```

3. 调用PrefixSpan函数

   ```python
   L = PrefixSpan.PrefixSpan(data,minSup=0.8,minCon=0)
   ```

   这个函数返回一个list，其中每个元素是一个PrefixSpan提取到的模式串（format: python tuple）
   
   参数：
   
   - minSup: 论文中提到的关键参数 min_support，默认为0.5
   - minConf: 置信度，可选，默认为0
   
4. 打印结果.

   ```python
   print(L)
   ```

   **[out]：**

   > [[(1,), (2,), (3,)], [(1, 2), (1, 3), (2, 3)], [(1, 2, 3)], []]

   列表中模式串的长度增长幅度为1