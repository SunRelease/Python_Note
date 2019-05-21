# day5
### 具名元组,即用collections构建一个带字段的元组和类
- [x] 尝试一下定义类
```
import collections
Citys=collections.namedtuple('City','name localip port')
China=Citys('Beijing','154.98.9.83',('3389','3306'))
print('{}\n{} {}:{}'.format(China,China.name,China.localip,China.port))
```
-[x] 结果如下,其实就是生成一个类,然后调用,但是它只能接受单一的可迭代对象
```
City(name='Beijing', local='154.98.9.83', port='3389')
Beijing 154.98.9.83:3389
```
### 除了从普通元组继承的属性外,它还有自己的属性
```
print(Citys._fields)
```
### 结果
```
('name', 'localip', 'port')
```
### ```asdict```顾名思义即可作为```dict```类型传出
```
print(Citys._asdict(China))
```
### 只不过是```ordereddict```类型
```
OrderedDict([('name', 'Beijing'), ('localip', '154.98.9.83'), ('port', ('3389', '3306'))])
```
### 还可以嵌套遍历字典
```
for keys,vaules in Citys._asdict(China).items():
    print('{} {}'.format(keys,vaules))
```
