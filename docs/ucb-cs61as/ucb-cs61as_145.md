# 字典和记忆化

## 字典

字典与列表非常相似，但不使用索引来引用值，而是使用键。

![](img/0c0d53cc040c2f16d234cd2589f427cd.jpg)

作为提醒，这是如何声明和访问列表值的方式：

```
>>> list_var = [0, 1, 2, 3]
>>> list_var[0]
0
>>> list_var[1]
1 
```

现在，将其与字典的结构进行对比。

创建字典：（键必须是不可变的，即字符串、数字、[元组](https://docs.python.org/2/tutorial/datastructures.html#tuples-and-sequences)，但不能是列表！）

```
>>> empty_dict = {}
>>> full_dict = {"January": 31, "February":28, "March": 31} 
```

访问字典：

```
>>> empty_dict["April"] #should error because there is no "April" key in this dictionary 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'April'
>>> full_dict["January"] #should return the value associated with "January" key
31 
```

添加和更改字典键值对：

```
>>> empty_dict["April"] = 30 #adding a new key,value pair
>>> empty_dict
{'April': 30}
>>> full_dict["February"] = 29 #changing an existing key's value
>>> full_dict #note that there is no order to the entries of the dictionary
{'March': 31, 'February': 29, 'January': 31} 
```

有用的字典操作：

```
>>> len(full_dict)
3 
```

```
>>> print ("dictionary as string: " + str(full_dict)) #str returns a printable string representation
dictionary as string: {'January': 31, 'March': 31, 'February': 29} 
```

```
>>> full_dict.get("April", default=False) #returns default if key is not in dictionary
False
>>> full_dict.has_key("January")
True
>>> "January" in full_dict #same as has_key operation
True 
```

```
>>> full_dict.update(empty_dict) #adds all of empty_dict's key,values into full_dict
>>> full_dict
{'January': 31, 'March': 31, 'February': 29, 'April': 30} 
```

遍历字典的键

```
>>> all_months = ""
>>> total_days = 0
>>> for key in full_dict:
...    all_months += key
...    all_months += " "
...    total_days += full_dict[key]
...
>>> total_days
121
>>> all_months
'January March February April ' 
```

遍历字典的值

```
>>> total_days = 0
>>> for val in full_dict.values():
...    total_days += val
...
>>> total_days
121 
```

删除

```
>>> del empty_dict['April']; # remove entry with key 'Name'
>>> empty_dict.clear();     # remove all entries in dict
>>> del empty_dict ;        # delete entire dictionary 
```

> **作业问题 7：字符频率**
> 
> 编写一个函数`char_freq()`，它接受一个字符串并构建其中包含的字符的频率列表。将频率列表表示为一个 Python 字典，其中每个字母作为一个键，存储该字母出现的次数。
> 
> 尝试使用类似`char_freq("abbabcbdbabdbdbabababcbcbab")`的东西。
> 
> **作业问题 8.1：凯撒密码**
> 
> 编写一个函数`rotate_letters()`，它接受一个数字并创建一个由该数字偏移的小写字母的新映射。将新映射作为字典返回，原始字母映射到移位后的字母。例如，`rotate_letters(2)`将映射`'a'`->`'c'`，`'b'`->`'d'`，`'c'`->`'e'`等。
> 
> **作业问题 8.2：凯撒密码**
> 
> 编写一个函数`decode_cipher()`，它接受一个字母映射的字典和一个密码字符串（仅包含小写字母）。返回当每个字符被字典中的映射替换时创建的解码字符串。例如，`decode_cipher(rotate_letters(2), "abc")`应返回`"cde"`。
> 
> 使用此函数解码“jbj fpurzr vf terng”，假设字母已经移位了 13 个位置。

## 记忆化

现在你已经掌握了学习一个名为记忆化的新主题的所有工具！记忆化是在计算事物时存储答案（特别是计算昂贵的答案）的行为，以便如果需要重复该计算，你已经有了一个记忆化的答案。记忆化通常用于改进慢递归过程的效率，该过程进行重复计算。

考虑生成第 n 个斐波那契数的斐波那契函数。递归地，该过程的蛮力定义如下：

```
def fib(n):
    return n if n < 2 else fib(n-2) + fib(n-1) 
```

如果 n 足够大，你将等待很长时间才能得到 fib 的返回值。考虑 n 为 5 的情况。我们将不得不计算 fib(5-2)和单独计算 fib(5-1)。但在计算 fib(5-1)时，我们将不得不重新计算 fib(5-2)。按照这种逻辑，你可以看到我们将得到许多不必要的重复计算。

查看调用 fib(6)生成的递归树。你能发现所有重叠的计算吗？

![](img/9d7ca612333db0e774e186ffc09e1859.jpg)

为了减少我们的低效性，我们应该在完成计算后缓存或存储计算。然后，在进行任何计算之前，我们只需检查我们的缓存是否已经完成了该计算。我们的缓存可以用字典创建！键将对应于参数值，值将对应于计算的结果。

```
fib_cache = {}
def fib(n):
    if n in fib_cache:
        return fib_cache[n]
    else:
        fib_cache[n] = n if n < 2 else fib(n-2) + fib(n-1)
        return fib_cache[n] 
```

这有点混乱，因为缓存存在于函数之外。或者，您可以封装缓存和函数，使其在每次调用包装函数时都进行记忆化。缓存将在每次调用`memo_fib()`时重置，但至少在一个调用内会发生记忆化。在项目 4 中，您将编写一个更好的记忆化例程，它不那么混乱，但在调用之间仍然进行了记忆化。

```
def memo_fib(n):
    fib_cache = {}
    def fib(n):
        if n in fib_cache:
            return fib_cache[n]
        else:
            fib_cache[n] = n if n < 2 else fib(n-2) + fib(n-1)
            return fib_cache[n]
    return fib(n) 
```

> **作业问题 9: 记忆化的阶乘乘积**
> 
> 以类似于`memo_fib`的方式编写一个记忆化的累积阶乘乘积过程。您必须使用递归。
> 
> 累积阶乘 5 的结果 = 5! * 4! * 3! * 2! * 1!
