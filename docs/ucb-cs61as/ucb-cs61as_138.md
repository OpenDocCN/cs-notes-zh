# 惰性列表中的流

## 流再访

在第 11 课中，我们展示了如何将流实现为延迟列表。我们引入了特殊形式`delay`和`cons-stream`，这使我们能够构造一个“承诺”来计算流的`cdr`，而不实际履行该承诺直到以后。每当我们需要更多控制评估过程时，我们可以使用这种一般技术引入特殊形式，但这很笨拙。首先，特殊形式不像过程那样是一流对象，因此我们无法与高阶过程一起使用它。此外，我们被迫将流创建为一种类似但不完全相同于列表的新数据对象，这要求我们重新实现许多用于流的普通列表操作（`map`，`append`等）。

## 惰性求值器中的流

使用惰性求值，流（streams）和列表（lists）可以是相同的，因此不需要特殊形式或单独的列表和流操作。我们所需要做的就是安排`cons`是非严格的。实现这一点的一种方法是扩展惰性求值器以允许非严格的原语，并将`cons`实现为其中之一。更简单的方法是回顾第 4 课，根本没有必要将`cons`实现为原语。相反，我们可以将对偶表示为过程

```
(define (cons x y)
  (lambda (m) (m x y)))
(define (car z)
  (z (lambda (p q) p)))
(define (cdr z)
  (z (lambda (p q) q))) 
```

根据这些基本操作，列表操作的标准定义将适用于无限列表（流）以及有限列表，并且流操作可以实现为列表操作。以下是一些示例：

```
(define (list-ref items n)
  (if (= n 0)
      (car items)
      (list-ref (cdr items) (- n 1))))

(define (map proc items)
  (if (null? items)
      '()
      (cons (proc (car items))
            (map proc (cdr items)))))
(define (scale-list items factor)
  (map (lambda (x) (* x factor))
       items))
(define (add-lists list1 list2)
  (cond ((null? list1) list2)
        ((null? list2) list1)
        (else (cons (+ (car list1) (car list2))
                    (add-lists (cdr list1) (cdr list2))))))
(define ones (cons 1 ones))
(define integers (cons 1 (add-lists ones integers)))
;;; L-Eval input:
(list-ref integers 17)
;;; L-Eval value:
18 
```

请注意，这些惰性列表比第 11 课的流*更懒惰*：列表的`car`和`cdr`都是延迟的。实际上，即使访问惰性对的`car`或`cdr`也不需要强制列表元素的值。只有在真正需要时才会强制该值--例如，用作原语的参数，或作为答案打印。
