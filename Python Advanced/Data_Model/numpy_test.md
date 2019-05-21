# day12
```
import numpy
a = numpy.arange(15)
print(a)
[ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14]
```
* ###  建立三行五列的矩阵
```
a.shape = 3, 5
print(a, a[1, 2], a[1, :], a[:, 3])
```
* ### 行列式的转置
```
b = a.transpose()
print(b)
```