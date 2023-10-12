# 实验二 Python变量、简单数据类型

班级： 21计科4班

学号： B20210404205

姓名： 康佳程

Github地址：<https://github.com/ktxiaok/python_experiments_2023.git>

CodeWars地址：<https://www.codewars.com/users/ktxiaok>

---

## 实验目的

1. 使用VSCode编写和运行Python程序
2. 学习Python变量和简单数据类型

## 实验环境

1. Git
2. Python 3.10
3. VSCode
4. VSCode插件

## 实验内容和步骤

### 第一部分

实验环境的安装

1. 安装Python，从Python官网下载Python 3.10安装包，下载后直接点击可以安装：[Python官网地址](https://www.python.org/downloads/)
2. 为了在VSCode集成环境下编写和运行Python程序，安装下列VScode插件
   - Python
   - Python Environment Manager
   - Python Indent
   - Python Extended
   - Python Docstring Generator
   - Jupyter
   - indent-rainbow
   - Jinja

---

### 第二部分

Python变量、简单数据类型和列表简介

完成教材《Python编程从入门到实践》下列章节的练习：

- 第2章 变量和简单数据类型

---

### 第三部分

在[Codewars网站](https://www.codewars.com)注册账号，完成下列Kata挑战：

---

#### 第1题：求离整数n最近的平方数（Find Nearest square number）

难度：8kyu

你的任务是找到一个正整数n的最近的平方数
例如，如果n=111，那么nearest_sq(n)（nearestSq(n)）等于121，因为111比100（10的平方）更接近121（11的平方）。
如果n已经是完全平方（例如n=144，n=81，等等），你需要直接返回n。
代码提交地址
<https://www.codewars.com/kata/5a805d8cafa10f8b930005ba>

---

#### 第2题：弹跳的球（Bouncing Balls）

难度：6kyu

一个孩子在一栋高楼的第N层玩球。这层楼离地面的高度h是已知的。他把球从窗口扔出去。球弹了起来,  例如:弹到其高度的三分之二（弹力为0.66）。他的母亲从离地面w米的窗户向外看,母亲会看到球在她的窗前经过多少次（包括球下落和反弹的时候）？

一个有效的实验必须满足三个条件：

- 参数 "h"（米）必须大于0
- 参数 "bounce "必须大于0且小于1
- 参数 “window "必须小于h。

如果以上三个条件都满足，返回一个正整数，否则返回-1。
**注意:只有当反弹球的高度严格大于窗口参数时，才能看到球。**
代码提交地址
<https://www.codewars.com/kata/5544c7a5cb454edb3c000047/train/python>

---

#### 第3题： 元音统计(Vowel Count)

难度： 7kyu

返回给定字符串中元音的数量（计数）。对于这个Kata，我们将考虑a、e、i、o、u作为元音（但不包括y）。输入的字符串将只由小写字母和/或空格组成。

代码提交地址：
<https://www.codewars.com/kata/54ff3102c1bad923760001f3>

---

#### 第4题：偶数或者奇数（Even or Odd）

难度：8kyu

创建一个函数接收一个整数作为参数，当整数为偶数时返回”Even”当整数位奇数时返回”Odd”。
代码提交地址：
<https://www.codewars.com/kata/53da3dbb4a5168369a0000fe>

### 第四部分

使用Mermaid绘制程序流程图

安装Mermaid的VSCode插件：

- Markdown Preview Mermaid Support
- Mermaid Markdown Syntax Highlighting

使用Markdown语法绘制你的程序绘制程序流程图（至少一个），Markdown代码如下：

显示效果如下：

```mermaid
flowchart LR
    A[Start] --> B{Is it?}
    B -->|Yes| C[OK]
    C --> D[Rethink]
    D --> B
    B ---->|No| E[End]
```

查看Mermaid流程图语法-->[点击这里](https://mermaid.js.org/syntax/flowchart.html)

使用Markdown编辑器（例如VScode）编写本次实验的实验报告，包括[实验过程与结果](#实验过程与结果)、[实验考查](#实验考查)和[实验总结](#实验总结)，并将其导出为 **PDF格式** 来提交。

## 实验过程与结果

请将实验过程与结果放在这里，包括：

- [第二部分 Python变量、简单数据类型和列表简介](#第二部分)
- [第三部分 Codewars Kata挑战](#第三部分)
- [第四部分 使用Mermaid绘制程序流程图](#第四部分)

### Codewars Kata挑战


Find Nearest Square Number
```python
def nearest_sq(n):
    i = 1
    diff = None
    while True:
        sq = i * i
        if sq == n:
            return n
        elif sq < n:
            diff = n - sq
        else:
            if diff == None:
                return sq
            else:
                cur_diff = sq - n
                if diff <= cur_diff:
                    return (i - 1) * (i - 1)
                else:
                    return sq
        i += 1
```
![完成情况截图](images/1.jpg)


Bouncing Ball
```python
def bouncing_ball(h, bounce, window):
    if h <= 0 or (bounce <= 0 or bounce >= 1) or window >= h:
        return -1
    count = 1
    x = h
    while True:
        x *= bounce
        if x > window:
            count += 2
        else:
            return count
```
![完成情况截图](images/2.jpg)


Vowel Count
```python
def get_count(sentence):
    vowels = {"a", "e", "i", "o", "u"}
    count = 0
    for c in sentence:
        if c in vowels: count += 1
    return count
```
![完成情况截图](images/3.jpg)


Even or Odd
```python
def even_or_odd(number):
    if number % 2 == 0: return "Even"
    else: return "Odd"
```
![完成情况截图](images/4.jpg)

### 使用Mermaid完成流程图
Bouncing Ball程序流程图:
```mermaid
flowchart LR
s(Start)
e(End)
s --> validate{"h > 0 and\n0 < bounce < 1 and\nwindow < h?"}
validate -->|No| exception[/"return -1"/] --> e
validate -->|Yes| init["count = 1, x = h"]
bounce["x *= bounce"]
judge{"x > window?"}
count["count += 2"]
init --> bounce --> judge
judge -->|Yes| count --> bounce
judge -->|No| return[/"return count"/] --> e
```

## 实验考查

请使用自己的语言并使用尽量简短代码示例回答下面的问题，这些问题将在实验检查时用于提问和答辩以及实际的操作。

1. Python中的简单数据类型有那些？我们可以对这些数据类型做哪些操作？

简单数据类型：字符串、整数、浮点数、布尔

字符串的操作：

使用索引来访问字符串中的单个字符
```python
s = "hello"
print(s[0]) # "h"
print(s[1]) # "e"
```

字符串通过加号拼接
```python
a = "hello"
b = "world"
print(a + " " + b) # "hello world"
```

字符串切片
```python
s = "hello"
# s[a:b]代表s的索引从a到b（不包括b）的部分字符串
print(s[0:2]) # "he"
print(s[1:]) # "ello"
print(s[:-1]) # "hell"
```

格式化字符串
```python
a = 1
b = 2
print("a = {}, b = {}".format(a, b)) # "a = 1, b = 2"
```

2. 为什么说Python中的变量都是标签？

Python的变量的类型可以动态更改，因此没有固定的存储大小，给变量赋值就像把变量的名字贴在某个数据上。

3. 有哪些方法可以提高Python代码的可读性？

对代码元素进行规范清晰的命名

逻辑和架构设计合理

合理组织代码，降低程序复杂性

在关键的地方适当添加注释

## 实验总结

总结一下这次实验你学习和使用到的知识，例如：编程工具的使用、数据结构、程序语言的语法、算法、编程技巧、编程思想。

本次实验学习了Python的变量的本质、常见数据类型的定义和操作，学习了Mermaid语言的使用。
其中，字符串的操作非常丰富，比如单个字符的访问、字符串切片、字符串格式化、字符串内置函数等等。