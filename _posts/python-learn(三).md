---
layout: post
title: "python 学习(三)"
featured-img: 1_ueWmI48uuShON-hX7LwI0w1 
summary: python 序列中列表和元组
categories: [技术 ,PYTHON]
---

> 在python中最基本的数据结构是序列。系列的每一个元素都被分配一个编号，可以称这个编号是索引。
> 自己可以理解为其他语言的数组
# 序列

## 1.创建序列

创建一个序列：

```python
a = [1, 3, "3", True]
```

> 序列的内部值是任意类型的值

创建二维序列：

```python
v = [1, 3, 45, [1, "4324"]]
```
## 2.序列的基本操作

- 和其他语言一样，序列都是下标的。

  ```python
  a = [1, 3, "3", True]
  print(a[1])
  
  >>>3
  ```

- 可以通过索引获取字符串s中，相对应的位置的字符，类似js操作

  ```python
  s = 'hello world'
  print(s[2])
  
  >>>l
  ```

- 如果索引为负数，则获取序列的倒数第一和第二，例如：

  ```python
  s = ["bill", 'mary', 'jack']
  print(s[0])
  print(s[-1])
  print(s[-2])
  
  >>>bill
  jack
  mary
  ```
  >如果下标超出范围，则会抛出异常

## 3.分片

分片操作是从序列A中获取一个子序列B。

- 基本操作如下：

  ```python
  s = "https://vineo.cn"
  
  print(s[1:3])
  >>>tt
  ```

- 通过索引和省略索引的方式得到子序列，观察下面一个例子：

  ```python
  a = [1, 2, 3, 4, 5, 6, 7, 8]
  print(a[3:5])
  print(a[0:1])
  print(a[5:8])
  print(a[-3:-1])
  print(a[-3:0]) #python语言规定，如果结束索引比开始索引晚出现，那么就会返回一个空序列。
  print(a[-3:])  #省略了结束索引 --->print(a[-3:-1])
  print(a[-3:8])  #结束索引用了正数作为索引
  print(a[:3]) #表示序列的前三位子序列
  print(a[:]) #如果不指定任何序列，则复制整个序列
  >>>
  [4, 5]
  [1]
  [6, 7, 8]
  [6, 7]
  []
  [6, 7, 8]
  [6, 7, 8]
  [1, 2, 3]
  [1, 2, 3, 4, 5, 6, 7, 8, 9]
  ```
- 设置步长，可以用来获取不相邻的元素
  ```python
  a = [1, 2, 3, 4, 5, 6, 7, 8]
  print(a[1:6:2]) #指定每次跨几步，格式是：   a[开始索引:结束索引:步长]
  print(a[::2]) #可以省略开始和结束索引
  print(a[3::2])
  print(a[::-2]) #从后往前推
  >>>
  [2, 4, 6]
  [1, 3, 5, 7, 9]
  [4, 6, 8]
  [9, 7, 5, 3, 1]
  ```
  >注意：步长不能为0，负责会抛出异常。如果步长为负数，此时开始索引要比结束索引要大。
- 小结：
  ```python
  urls = input("请输入一个网址")
  print("输入的scheme：", urls[0:5])
  print("输入的host：", urls[8:])

  >>>
  请输入一个网址https://www.vineo.com
  输入的scheme： https
  输入的host： www.vineo.com
  ```
