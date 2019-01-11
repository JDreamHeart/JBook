# Python编程技巧
  * 程序必须先让人读懂，然后才能让计算机执行。

### 1. 交换赋值
```
# 先生成一个元素（tuple）对象，然后unpack
a, b = b, a;
```

### 2. Unpacking
```
# 使用变量接收列表中的数据
l = ["a", "b", "c"];
a, b, c = l;
# 在Python3中，支持以下方式
a, *midList, c = l;
```