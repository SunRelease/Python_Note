# day4
---
```
import gettext
```
### 可迭代元素的拆包
#### 元组的拆包可以应用到任何可以迭代的对象上,对元组来说,_ * 都是很好的占位符
* #### 例如:
```
lax = (33.789, -118.56)
latitude, longitude = lax
print(latitude, longitude)
```
* #### 还可以直接交换变量,不用中间值,比c语言便捷多了
```
latitude,longitude=longitude,latitude
print(latitude, longitude)
```
#### 1. 其实就我理解来说,用c语言理解就是大概将该数值的指针的位置指向特定位置,从而实现数据在序列中分离
#### 2.占位符在大多数情况下是选择好用的```_```,但是它也是```gettext.gettext```函数的别名,这里大家要注意一下:
```
_ = gettext.gettext()
```

#### 3.当然最经典的还是莫属于```*args```,```**kwargs```了,大家都懂的,在定义值时非常好用,接下来在会仔细了解了解