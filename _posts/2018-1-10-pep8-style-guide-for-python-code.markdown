---
layout: post
title: "PEP 8: Style Guide for Python Code"
author: wdl
date: 2018-1-10 10:00:00
tags:
    - python
---

> 优雅的python

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

+ 空格是首选缩进方法.
+ tab仅用于与已用tab缩进的代码保持一致.
+ python 3不允许混合使用tab和空格进行缩进.
+ 使用tab和空格混合方式缩进的python 2代码, 应转换为使用空格.
+ 当使用-t选项调用python 2命令行解释器时, 它会发出关于非法混合使用tab和空格的警告.当使用tt选项时, 这些警告会变成错误.强烈建议使用这些选项.

### 3 最大行长度

### 4 是否应该在二元操作符前或后换行?

### 5 空白行

### 6 源文件编码

### 7 导入

### 8 模块级dunder名称

# 字符串引用

### 1 Pet Peeves


### 2 其他建议


# 表达式和语句中的空白

# 何时使用结尾逗号

# 注释

### 1 块注释

###2 行内注释

###3 文档字符串

# 命名约定

### 1 压倒一切的原则

### 2 描述: 命名样式

### 3 规范性: 命名约定

### 4 公共和内部接口

# 编程建议

### 1 函数注释