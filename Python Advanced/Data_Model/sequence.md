# day2

### 内置函数的类型概览

---
```
import collections
import array
```
* ## 容器序列
>#### 可以贮存不同类型的数据
```
list(),tuple(),collections.deque()
```
* ## 扁平序列
>#### 只能贮存相同类型的数据
```
str(),bytearray(),bytes(),memoryview(),array.array()
```
## 序列又可以分成```可变```和```不可变```序列
### 可变序列
```
list(), bytearray(), array.array(), collections.deque(), memoryview()
```
### 不可变序列
```
tuple(),str(),bytes()
```