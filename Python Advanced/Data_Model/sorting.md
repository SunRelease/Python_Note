# day9

#### ```list.sort```和```sorted```内置函数


```
fruits = ['apple', 'pear', 'banana', 'grape']
```

* #### 运用```list.sort```方法的话不会生成新列表,但是不利于观察结果调试,直接在原列表修改```sort()```
* #### 而且不能对```dict```字典进行排序
```
fruits.sort()
print(fruits)
fruits = ['apple', 'banana', 'grape', 'pear']
```
### 运用```sorted```则会生成新列表,不会影响原列表
### 个人建议使用内置函数,好调试且支持字典排序
```
new_fruits = sorted(fruits)
print(new_fruits, fruits)
['apple', 'banana', 'grape', 'pear']
['apple', 'pear', 'banana', 'grape']
```
* ### 关于排序函数都是默认升序排序的,这两类都有两个参数,```reverse```和```key```,```value```;
* ### 这```key```可以是大小,长度等,```str.lower```
```
test = sorted(fruits, reverse=True, key=len)
print(test)

['banana', 'apple', 'grape', 'pear']
```