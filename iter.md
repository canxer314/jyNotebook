### 语法

```
iter(object[, sentinel])
```

### 作用

生成迭代器

### 参数

* object:支持迭代的集合对象。

* sentinel:如果传递了第二个参数，则参数 object 必须是一个可调用的对象（如，函数），此时，iter 创建了一个迭代器对象，每次调用这个迭代器对象的\_\_next\_\_\(\)方法时，都会调用 object。

### 实例

```
>>>lst = [1, 2, 3]
>>> for i in iter(lst):
...     print(i)
... 
1
2
3
```



