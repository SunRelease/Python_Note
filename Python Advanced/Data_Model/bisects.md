# day10

### 来管理已经排序的序列

---
```
import bisect
import random
import sys

HAYSTACK = [1, 23, 3, 45, 35, 69, 57, 83, 12]
NEEDLES = [0, 1, 2, 3, 45, 35, 56, 42, 14]

ROW_FMT = '{0:2d} @ {1:2d}    {2}{0:<2d}'


def demo(bisect_fn):
    # 观察插入序列的位置
    for needles in reversed(NEEDLES):
        position = bisect_fn(HAYSTACK, needles)
        offset = position * ' |'
        print(ROW_FMT.format(needles, position, offset))


def grade(sorce, breakpoints=[60, 70, 80, 90], grade='FDCBA'):
    # 以分数作为索引和成绩对应起来
    i = bisect.bisect(breakpoints, sorce)
    return grade[i]


if __name__ == '__main__':

    if sys.argv[-1] == 'left':
        bisect_fn = bisect.bisect_left
    else:
        bisect_fn = bisect.bisect

    print('DEMO:', bisect_fn.__name__)
    print('hastrack->', ''.join('%2d ' % n for n in HAYSTACK))
    demo(bisect_fn)
    grades = [grade(sorce) for sorce in [33, 45, 97, 16, 54, 65, 87, 69, 77]]
    print(grades)
```
* #### ```bisect.bisect_right```是```bisect```的别名,```right```是插在元素相等的后面,而```left```是元素相等的前面
```
DEMO: bisect
hastrack->  1 23  3 45 35 69 57 83 12
14 @  3     | | |14
42 @  5     | | | | |42
56 @  5     | | | | |56
35 @  5     | | | | |35
45 @  5     | | | | |45
3 @  3     | | |3
2 @  1     |2
1 @  1     |1
0 @  0    0
['F', 'F', 'A', 'F', 'F', 'D', 'B', 'D', 'C']
```
* #### 运用```bisect.insort```插入已经排序好的序列,保持顺序,当然,列表的功能很强大,如果只是处理数字的话,数组是一个不错的选择
```
SIZE = 7
random.seed(1729)

my_list = []
for i in range(SIZE):
    new_item = random.randrange(SIZE * 2)
    bisect.insort(my_list, new_item)
    print('%2d -> ' % new_item, my_list)
```
---
```
10 ->  [10]
0 ->  [0, 10]
6 ->  [0, 6, 10]
8 ->  [0, 6, 8, 10]
7 ->  [0, 6, 7, 8, 10]
2 ->  [0, 2, 6, 7, 8, 10]
10 ->  [0, 2, 6, 7, 8, 10, 10]
```