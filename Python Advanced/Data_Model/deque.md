# day13

# 队列

```
各种不同的标准库deque队列
from collections import deque
from queue import Queue
from multiprocessing import queues
from asyncio import Queue
```

-  #### `dq=deque(range(10),maxlen=10)` 

> `maxlen`是可选参数,即确定`队列容纳`的数量,确定后不可以改变

```
print(dq)
deque([0, 1, 2, 3, 4, 5, 6, 7, 8, 9], maxlen=10)
```

- ### 对列反转
>队列的旋转操作

>`n>0`时,`最左边`的元素移到`最右边`

>`n<0`时,`最右边`的元素移到`最左边`

- #### `dq.rotate(3)`    

```
print(dq)
deque([7, 8, 9, 0, 1, 2, 3, 4, 5, 6], maxlen=10)
```

- #### dq.rotate(-5)
```
print(dq)
deque([2, 3, 4, 5, 6, 7, 8, 9, 0, 1], maxlen=10)
```
* ### 单个元素操作

`dq.appendleft(-1)`做`头部`添加操作,`尾部元素弹出`,即保持栈数

```
print(dq)
deque([-1, 2, 3, 4, 5, 6, 7, 8, 9, 0], maxlen=10)
```

`dq.append(-2)` 作`尾部`添加操作,`头部元素弹出`,保持栈数

```
print(dq)
deque([2, 3, 4, 5, 6, 7, 8, 9, 0, -2], maxlen=10)
```

* ### 多个元素操作 `itemable`


* `dq.extendleft([-2,2,8])`  向`头部`操作

```
print(dq)
deque([8, 2, -2, 2, 3, 4, 5, 6, 7, 8], maxlen=10)
```

* `dq.extend([3,5,-2])`    向尾部操作

```
print(dq)
deque([2, 3, 4, 5, 6, 7, 8, 3, 5, -2], maxlen=10)
```

* `dq.pop()`   弹出`最后`一个元素,`不接受参数`

```
print(dq)
deque([2, 3, 4, 5, 6, 7, 8, 3, 5], maxlen=10)
```

* `dq.popleft()` #弹出`第一个数`

```
print(dq)
deque([2, 3, 4, 5, 6, 7, 8, 3, 5], maxlen=10)
```

* `dq.__delitem__(3)`   删除`指定索引`的元素

```
print(dq)
deque([3, 4, 5, 7, 8, 3, 5], maxlen=10)
```








