---
layout: post
title: "PEP 8: Style Guide for Python Code"
author: wdl
date: 2018-1-10 10:00:00
tags:
    - python
---

> 
>
>

# 代码布局

1. 缩进

每个缩进级使用4个空格.

Yes:

{% highlight python %}
# Aligned with opening delimiter.
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

# More indentation included to distinguish this from the rest.
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)

# Hanging indents should add a level.
foo = long_function_name(
    var_one, var_two,
    var_three, var_four)
{% endhighlight %}

No:

{% highlight python %}
# Arguments on first line forbidden when not using vertical alignment.
foo = long_function_name(var_one, var_two,
    var_three, var_four)

# Further indentation required as indentation is not distinguishable.
def long_function_name(
    var_one, var_two, var_three,
    var_four):
    print(var_one)
{% endhighlight %}

Optional:

{% highlight python %}
# Hanging indents *may* be indented to other than 4 spaces.
foo = long_function_name(
  var_one, var_two,
  var_three, var_four)
{% endhighlight %}

2. Tabs or Spaces?

3. 最大行长度

4. 是否应该在二元操作符前或后换行?

5. 空白行

6. 源文件编码

7. 导入

8. 模块级dunder名称

# 字符串引用

1. Pet Peeves

2. 其他建议

# 表达式和语句中的空白

# 何时使用结尾逗号

# 注释

1. 块注释

2. 行内注释

3. 文档字符串

# 命名约定

1. 压倒一切的原则

2. 描述: 命名样式

3. 规范性: 命名约定

4. 公共和内部接口

# 编程建议

1. 函数注释