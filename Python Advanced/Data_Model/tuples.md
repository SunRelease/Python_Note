# day11
```
from array import array
from random import random
```
* #### 创建一千万的浮点数
```
float1=array('d',(random() for i in range(10**7)))
```
* #### 打印数组数值
```
print(float1[-1])
print(float1[0])
```
* #### 使用二进制保存文件比直接保存节省字节
```
with open('file.txt','wb')as f:
    f.write(float1)
 ```
* #### 建立新数组
```
float2=array('d')
with open('file.txt','rb')as f:
    float2.fromfile(f,10**7)
    print(float2[-1],float2[0])

0.8122407782124278
0.22865307802567636
```



