---
layout: post
title: "python 学习(一)"
featured-img: 1_ueWmI48uuShON-hX7LwI0w1 
summary: 条件，循环和其他语句 
categories: [技术 ,python]
---

# 基础知识

## print函数

> 表示打印

- **print **可以传入多个参数，那么相对应的首尾输出。(可以理解chrome 浏览中`console `函数)例如:

  ```python
  print(1, 3, 4, 5, 6, 7)
  >>>1 3 4 5 6 7
  ```

- 当我们输出`print("apple", ",", "orange")`返回的结果有空格；`apple , orange`。解决方法:

  ```python
  print("apple"+","+"orange")
  >>>apple,orange
  
  
  # 采用print特有的方法，就是priny函数最后参数添加sep=","
  print("apple", "orange", "banana", sep=",")
  >>>apple,orange,banana
  ```

- **print**函数输出结果，结果后面会默认添加一个`\n`换行符，可以通过`end=""`参数，**引号中可以添加参数**可以添加参数例如：

  ```python
  x = 12345
  y = 0xF98A
  z = 0b1100010110
  print('2', bin(x), end="|")
  print('8', oct(x), end="|")
  print('16', hex(x), end="|")
  >>>2 0b11000000111001|8 0o30071|16 0x3039|
  ```

## 赋值操作

> =

- python可以多个赋值操作

  ```python
  x, y, z = 12345, 0xF98A, 0b1100010110
  
  print('2', bin(x), end="|")
  print('8', oct(x), end="|")
  print('16', hex(x), end="|")
  >>>2 0b11000000111001|8 0o30071|16 0x3039|
  ```

  > python 这种赋值方式，称之为序列解包，确保左右赋值相同，不然会报错。

- 链式赋值

  ```python
  a = b = 9
  print(a, b)
  >>>9 9
  ```

- 增量赋值

  ```python
  a = b = 9
  a *= 2   # ===> a=a*2
  print(a)
  >>>19
  
  a /= 2 # ===> a=a/2
  print(a)
  >>>4.5
  
  a %= 2  # ===> a=a%2
  print(a)
  >>>1
  ```

## 用缩进创建代码块

> 虽然**tab**也是可以进行缩进代码块，python将一个**tab**字符解释到下一个**tab**字符位置移动，而一个**tab**字符是8个字符，python推荐使用4个空格来进行缩进。

因此整个代码格式如下：

```python
this is a code
this is a second code:
    this is block
    this is second block    
this is escaped the inner block
```

## 条件语句（逻辑控制）

### boolean 和boolean 变量

- boolean变量：**True**和**False**,注意大小写。

- 下面的值会被解释为**False**：`None 0 "" () [] {}`。

- 在python底层，是将**Flase**看成**0**，**True**看成**1**，例如：

  ```python
  print(True == 1)
  >>>True
  print(False == 0)
  >>>True
  ```

- 可以bool将一些变量，转换为boolean值。

  ```python
  print(bool(""))
  >>>False
  print(bool("1"))
  >>>True
  ```

### 条件语句（if,else 和elif）

> 和其他语言对比：
>
> if和else 和其他语言用法相似，
>
> elif相当与其余语言的else if用法。

注意一点：python中没有switch逻辑判断语句。

基本用法和**java**和**JavaScript**用法相似。支持嵌套

### 比较运算符

| 逻辑表达式 |                             描述                             |
| :--------: | :----------------------------------------------------------: |
|    x==y    |                            x等于y                            |
|    x<y     |                            x小于y                            |
|    x>y     |                            x大于y                            |
|    x<=y    |                          x小于等于y                          |
|    x>=y    |                          x大于等于y                          |
|    x!=y    |                           x不等于y                           |
|   x is y   |                      x 和 y是同一个对象                      |
| x is not y |                     x 和 y是不同一个对象                     |
|   x in y   |   x是y的容器的成员，如：y =[1,3,54,6] x=1 ; x in y >>>True   |
| x not in y | x是y的容器的成员，如：y =[1,3,54,6] x=12 ; x not in y >>>True |
|   x or y   |                            x 或y                             |
|  x and y   |                            x 且y                             |

- python 比较字符串时，会比较字符串的**ASCII**,如：

  ```python
  print("hello" > "Hello")
  >>>True
  ```

  > 会首先比较**h**和**H**的 **ASCII**值，前面为*真*后面就不会比较

- 如果一个字符串是另一个字符串的前缀，那么python会认为字符串较长的更大一些

  ```python
  print("hello" > "hello world")
  >>>False
  ```

- 判断相等

  ```python
  x = y = [1, 2, 3]
  z = [1, 2, 3]
  print(x == y)
  >>> True
  print(x == z)
  >>> True
  print(x is y)
  >>> True
  print(x is z)
  >>> False
  print(x is not z)
  >>> True
  ```
  > 可以参照类似堆和栈方式，来理解。

- `in`和`not in`运算符

  ```python
  x = [1, 2, 3]
  y = 3
  print(y in x)
  >>>True
  
  #除了可以用来判断容器，也可以判断字符串是否包含其中一个字符串
  s = "hello world"
  print("h" in s)
  >>>True
  ```

- `or`和`and`用来表示多个逻辑的组合在一个。

### 断言

contine......

