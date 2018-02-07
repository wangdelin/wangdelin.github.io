---
layout: post
title: "PEP 8: Style Guide for Python Code"
author: wdl
date: 2018-1-10 10:00:00
tags:
    - python
---

> 代码如诗

# 代码布局

### 1 缩进

每个缩进级使用4个空格.

Yes:
```python
# 与打开的分隔符对齐
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

# 使用更多的缩进与其他区分开
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)

foo = long_function_name(
    var_one, var_two,
    var_three, var_four)
```

No:
```python
# 在不使用垂直对齐时,禁止在第一行写参数
foo = long_function_name(var_one, var_two,
    var_three, var_four)

def long_function_name(
    var_one, var_two, var_three,
    var_four):
    print(var_one)
```

Optional:
```python
foo = long_function_name(
  var_one, var_two,
  var_three, var_four)
```

```python
if (this_is_one_thing and
    that_is_another_thing):
    do_something()

if (this_is_one_thing and
    that_is_another_thing):
    # Since both conditions are true, we can frobnicate.
    do_something()

if (this_is_one_thing
        and that_is_another_thing):
    do_something()
```

```
my_list = [
    1, 2, 3,
    4, 5, 6,
    ]
result = some_function_that_takes_arguments(
    'a', 'b', 'c',
    'd', 'e', 'f',
    )

# 或者

my_list = [
    1, 2, 3,
    4, 5, 6,
]
result = some_function_that_takes_arguments(
    'a', 'b', 'c',
    'd', 'e', 'f',
)
```

###  2 Tabs or Spaces?

+ 空格是首选缩进方法
+ tab仅用于与已用tab缩进的代码保持一致
+ python 3 不允许混合使用tab和空格进行缩进
+ 使用tab和空格混合方式缩进的 python 2 代码, 应转换为使用空格
+ 当使用-t选项调用 python 2 命令行解释器时, 它会发出关于非法混合使用tab和空格的警告.当使用-tt选项时, 这些警告会变成错误.强烈建议使用这些选项

### 3 最大行长度

将所有行限制为最多79个字符。

对于结构限制少的长文本块（文档字符串或注释）, 行的长度应该限制为72个字符。

### 4 是否应该在二元操作符前或后换行?

### 5 空白行

### 6 源文件编码

### 7 导入

> 导入应该放在独立的行

Yes:
```python

import os
import sys
```

No:
```python
import sys, os
```

> 导入应该放在文件的顶端，放在模块注释和文档字符串之后，模块全集变量和常量之前。

应该按照以下顺序分组导入:

1. 标准库导入
2. 相关的第三方库导入
3. 本地应用程序/库特定的导入

每组之间应该放置一个空行。

> 建议绝对导入，因为它们通常更容易阅读。如果导入系统配置不正确（例如， 当包中的一个目录在**sys.path**的结尾），它们往往表现更好（或者至少给出更好的错误信息）。

```python
import mypkg.sibling
from mypkg import sibling
from mypkg.sibling import example
```

然而，显式的相对导入是绝对导入可接受的替代品，尤其是在处理复杂的包布局（使用绝对导入将会不必要地冗长）的时候。

```python
from . import sibling
from .silbing import example
```

标准库代码应避免复杂的包布局, 并始终使用绝对导入。

不应使用隐式相对导入, 并且已在 Python 3 中删除。

> 当从包含类的模块导入类时，通常可以这样拼写:

```python
from myclass import MyClass
from foo.bar.yourclass import YourClass
```

如果此拼写导致本地名称冲突, 则这样拼写:

```python
import myclass
import foo.bar.yourclass
```

然后使用`myclass.MyClass` 和 `foo.bar.yourclass.YourClass`。

> 应避免通配符导入(`from <module> import *`), 因为它们使得命名空间中存在哪些名称(names)不清楚， 这会使得读者或者许多自动化工具混淆。通配符导入有一个可辨的使用案例是，重新发布一个内部接口作为公共API的一部分。

当以这种方式重新发布名称(names)时，下面有关公共和内部接口的准则仍然适用。

### 8 模块级dunder名称

模块级 "dunders" （即名称有两个前导和两个尾随下划线）例如 `__all__`, `__author__`, `__version__` 等等。应该放在除了`from __future__`导入之外的任何导入语句之前且模块文档字符串(docstrings)之后。python 要求 futrue导出必须出现在模块除了文档字符串(docstrings)之外的任意代码之前。

例如:
```python
"""This is the example module.

This module does stuff.
"""

from __future__ import barry_as_FLUFL

__all__ = ['a', 'b', 'c']
__version__ = '0.1'
__author__ = 'Cardinal Biggles'

import os
import sys
```

# 字符串引用

在Python中, 单引号字符串与双引号字符串是一样的。PEP并没有对此提出建议。选择一个规则并坚持下去。但是，当字符串中包含单引号或者双引号时，使用另外一种来避免使用反斜杆。它可提高可读性。

对于三引号字符串，总是使用双引号来保持与PEP 257中的docstring约定一致。

# 表达式和语句中的空白

### 1 个人小怪癖

在下列情况下避免多余的空白:

+ 括号，方括号，大括号内部紧接的地方。

Yes
```
spam(ham[1], {eggs: 2})
```
No
```
spam( ham[ 1 ], { eggs: 2 } )
```

+ 介于尾随逗号和右括号之间。'

Yes
```
foo = (0,)
```

No
```
bar = (0, )
```

+ 紧接在逗号、分号或冒号之前。

Yes
```
if x == 4: print x, y; x, y = y, x
```

No
```
if x == 4 : print x , y ; x , y = y , x
```

+ 然而, 在分片中冒号的作用类似于二元操作符，并且逗号两边应该有相等的数量（将其作为具有最低优先级的操作符）.在扩展分片中，两个冒号都必须提供相同数量的空白。例外: 当一个分片参数省略，空白也应省略。

Yes
```
# Yes
ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
ham[lower:upper], ham[lower:upper:], ham[lower::step]
ham[lower+offset : upper+offset]
ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
ham[lower + offset : upper + offset]
```

No
```
ham[lower + offset:upper + offset]
ham[1: 9], ham[1 :9], ham[1:9 :3]
ham[lower : : upper]
ham[ : upper]
```

+ 紧接在开始函数调用的参数列表的左括号之前。

Yes
```
spam(1)
```

No
```
spam (1)
```

+ 紧接在开始索引或切片的左括号之前。

Yes
```
dct['key'] = lst[index]
```

No
```
dct ['key'] = lst [index]
```

+ 在赋值(或其他)运算符周围有多个空白, 以使其与另一个运算符对齐。

Yes
```
x = 1
y = 2
long_variable = 3
```

No
```
x             = 1
y             = 2
long_variable = 3
```

### 2 其他建议

# 何时使用结尾逗号

# 注释

### 1 块注释

### 2 行内注释

### 3 文档字符串

# 命名约定

### 1 压倒一切的原则

### 2 描述: 命名样式

### 3 规范性: 命名约定

### 4 公共和内部接口

# 编程建议

### 1 函数注释