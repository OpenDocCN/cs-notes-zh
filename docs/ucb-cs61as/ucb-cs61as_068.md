# 引用

本节是对 `quote` 函数（更常见的是 `'`）及其功能的简短回顾和概述，以帮助你准备下一节 `calc.rkt`。

## 复习

自从这门课程开始，我们一直使用引号 `'` 作为创建单词和句子的快捷方式。下面的例子应该非常简单易懂：

```
> (define a 3)
3

> a
3

> 'a
a 
```

使用单引号实际上是一个快捷方式 - `'a` 等同于 `(quote a)`。类似地，`'(a 1 b 2)` 等同于 `(quote (a 1 b 2))`

**测试你的理解**

函数 quote（'）是一个特殊形式。

## 谓词和引用

要检查相等性，我们可以使用原始函数 `eq?`

```
> (eq? 'a 'a)
#t
> (eq? 'a 'b)
#f
> (eq? 'a (first 'afro))
#t 
```

处理符号/引用的另一个有用的原始函数是 `memq`。`memq` 接受两个参数，一个符号和一个列表。如果符号不包含在列表中（即它与列表中的任何项都不是 `eq?`），那么 `memq` 返回 `false`。否则，它返回列表的子列表，从符号的第一次出现开始：

```
>(memq 'apple '(banana raspberry windows android))
#f
>(memq 'apple '(banana raspberry windows apple android))
(apple android)
>(memq 'apple '(banana raspberry windows (apple android))
#f 
```

注意最后一个例子返回 `#f`，因为 `(eq? 'apple '(apple android))` 返回 #f。因此，`memq` 在深层列表上不起作用。

你可以用以下定义来实现 `memq`：

```
(define (memq item x)
  (cond ((null? x) false)
        ((eq? item (car x)) x)
        (else (memq item (cdr x))))) 
```

**测试你的理解**

以下表达式返回什么？

```
(memq 'everything '(sugar spice (everything nice)))
```

```
(memq 'chicken '(cow chicken cow and chicken))
```

## Racket 会打印什么？

对于以下每个表达式，预测 Racket 会打印什么，而不使用解释器。然后，使用解释器检查你的答案。

```
* `(list 'a 'b 'c)`
* `(list (list 'george))`
* `(cdr '((x1 x2) (y1 y2)))`
* `(cadr '((x1 x2) (y1 y2))`
* `(pair? (car '(a short list)))`
* `(memq 'red '((red shoes) (blue socks)))`
* `(memq 'red '(red shoes blue socks))` 
```

## 要点

在本小节中，你学到了：

+   `'hi` 是 `(quote hi)` 的简写。

+   `memq` 是一个判断符号是否在列表中的谓词。
