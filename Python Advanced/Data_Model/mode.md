# day1

---

### 关于对python中的内置函数有个比较系统的认识

```
import collections
card = collections.namedtuple('Card', ['rank', 'suit'])
```
* #### 通过`__getitems__`可以实现迭代

* #### 其实`len()`等方法实际是调用`__len__`的方法

* #### 特殊方法的调用是隐式的.如下面i的循环

---
```
for i in x:
    print(x)
```
---
* #### 实际上是调用```x._iter_```的方法

* #### 唯一的例外是在自己的子类中调用超类的构造器.如关键字

```
def __init__ (self):
```
* #### ```__add__``` 和```__model__```是算术的加乘```+``` ```*```


