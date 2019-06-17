# 编程笔记

----

## 1. 数据结构
### 1.1 结构拆分
#### 1.1.1 数据层级原则上不宜过深
  * 为了方便阅读代码，且保证在查找相关数据结构时，能较快跳转到所定义的文件中，从而进行扩展或修改等操作。
  * 同一个文件进行查找或跳转，在一定程度上，会比在多个文件中进行查找跳转更优。

#### 1.1.2 多层基本数据组合而成的数据需要进行合理拆分
  * 当存在多层基本数据组合而成的数据时，为了方便理解，需要进行合理拆分及添加相应注释。
```go
struct Data {
  groupListMap map[int][][]int
}

// 进行简单拆分
type group []int // 单个组合
type groupList []group // 组合列表
struct Data {
  groupListMap map[int]groupList
}
```

### 1.2 数据状态
#### 1.2.1 标记or状态值
  * 当存在多种标记时，则要考虑是否可以通过状态值来达到多种标记的作用，以减少多种标记字段的维护和提高使用的方便性。


## 2. 协议相关
### 2.1 协议设计
#### 2.1.1 功能的统一
  * 设计协议时，不代表功能拆分得越细，越容易理解和使用。而是应该**将请求和反馈协议，进行配套**，避免出现单个请求，而又多种反馈协议的出现，否则会导致理解和使用变得麻烦。

#### 2.1.2 尽量使用向后添加字段来扩展协议
  * 在协议的使用上，为了**方便理解和使用**，而应该尽量使用向后添加字段的方式来扩展协议，不宜通过json字符串将数据保存到一个string类型的字段。

### 2.2 协议命名
#### 2.2.1 适当使用缩写
  * 由于可使用注释，故而在设计协议及其字段时，要保证既能保证命名简单，又能反映出大概用途，则可适当地利用缩写来实现。