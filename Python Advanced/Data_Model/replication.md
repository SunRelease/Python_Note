# day 8

### 关于一个比较神奇的问题,在学者讨论会上有人提出来的

---
```
def question():
    result = (1, 2, [20, 30])
    result[2] += [40, 50]
    return result
def print_result(result):
    print(result)
if __name__ == '__main__':
    result=question()
    print_result(result)
```
- [x] 以上的结果是会报错
```
Traceback (most recent call last):
   File "D:/replication.py", line 4, in <module>
     result[2]+=[40,50]
TypeError: 'tuple' object does not support item assignment
```
### 虽然元组的属性是不可改变的,但是result的结果还是改变了,变为

``` 
result=(1,2,[20,30,40,50])
```
* #### 所以对于这种问题,最好的方法不要把可变的序列放在不可变的序列中,避免这种问题的出现
