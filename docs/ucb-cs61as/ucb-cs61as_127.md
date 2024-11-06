# 应用

## `apply`

`Apply`接受两个参数，一个过程和应该应用该过程的参数列表。`Apply`将过程分类为两种：它调用`apply-primitive-procedure`来应用原始过程；它通过顺序评估组成过程体的表达式来应用复合过程。用于评估复合过程体的环境是通过扩展过程携带的基本环境构造的，以包括一个框架，该框架将过程的参数绑定到应该应用过程的参数上。这是`apply`的定义：

```
(define (apply procedure arguments)
  (cond ((primitive-procedure? procedure)
         (apply-primitive-procedure procedure arguments))
        ((compound-procedure? procedure)
         (eval-sequence
           (procedure-body procedure)
           (extend-environment
             (procedure-parameters procedure)
             arguments
             (procedure-environment procedure))))
        (else
         (error
          "Unknown procedure type -- APPLY" procedure)))) 
```

我们将逐一介绍定义中使用的步骤。

## 表示过程

要处理原始过程，我们假设我们可以使用以下过程：

+   `(apply-primitive-procedure proc args)`

    将给定的原始过程应用于列表'args'中的参数值，并返回应用的结果。

+   `(primitive-procedure? proc)`

    测试`proc`是否是原始过程。

复合过程是使用构造函数`make-procedure`从参数、过程体和环境构造的：

```
(define (make-procedure parameters body env)
  (list 'procedure parameters body env))
(define (compound-procedure? p)
  (tagged-list? p 'procedure))
(define (procedure-parameters p) (cadr p))
(define (procedure-body p) (caddr p))
(define (procedure-environment p) (cadddr p)) 
```

## 原始过程

此时，或许很长时间以来，您可能想知道如何在 Scheme 中表示原始过程。实际上，表示原始过程没有正确的方式，只要`apply`可以使用`primitive-procedure?`和`apply-primitive- procedure`识别和应用它们即可。

创建 Scheme 的人决定将原始过程表示为以符号`primitive`开头并包含实现该原始过程的基础 Lisp 中的过程的列表。

```
(define (primitive-procedure? proc)
  (tagged-list? proc 'primitive))

(define (primitive-implementation proc) (cadr proc))

(define primitive-procedures
  (list (list 'car car)
        (list 'cdr cdr)
        (list 'cons cons)
        (list 'null? null?)
        <more primitives>
        ))

(define (primitive-procedure-names)
  (map car
       primitive-procedures))

(define (primitive-procedure-objects)
  (map (lambda (proc) (list 'primitive (cadr proc)))
       primitive-procedures)) 
```

要应用原始过程，我们只需将实现过程应用于参数，使用底层的 Lisp 系统：

```
(define (apply-primitive-procedure proc args)
  (apply-in-underlying-scheme
   (primitive-implementation proc) args)) 
```

## 环境操作

当然，评估器需要操作以操作环境。环境是什么？它是一系列框架，其中每个框架都是一个将变量与其对应值关联的绑定表。我们使用以下操作来操作环境：

+   `(lookup-variable-value <var> <env>)`

    返回绑定到符号`in the environment <env>的值，如果变量未绑定，则发出错误信号。</env>`

+   `(extend-environment <variables> <values> <base-env>)`

    返回一个新的环境，由一个新的框架组成，在该框架中，列表<variables>中的符号绑定到列表<values>中的相应元素，其中封闭环境是环境<base-env>。</base-env></values></variables>

+   `(define-variable! <var> <value> <env>)`

    向环境<env>中的第一个框架添加一个新绑定，将变量`与值<value>关联。</value>`</env>

+   `(set-variable-value! <var> <value> <env>)`

    更改变量`在环境<env>中的绑定，使变量现在绑定到值<value>，或者如果变量未绑定，则发出错误信号。</value></env>`

为了实现这些操作，我们将环境表示为框架列表。环境的封闭环境是列表的`cdr`。空环境就是空列表。

```
(define (enclosing-environment env) (cdr env))
(define (first-frame env) (car env))
(define the-empty-environment '()) 
```

环境的每个框架都表示为两个列表的对：绑定在该框架中的变量列表和关联值列表。

```
(define (make-frame variables values)
  (cons variables values))
(define (frame-variables frame) (car frame))
(define (frame-values frame) (cdr frame))
(define (add-binding-to-frame! var val frame)
  (set-car! frame (cons var (car frame)))
  (set-cdr! frame (cons val (cdr frame)))) 
```

为了通过一个新的框架扩展环境，将变量与值关联起来，我们创建一个由变量列表和值列表组成的框架，并将其附加到环境中。如果变量的数量与值的数量不匹配，我们会发出错误信号。

```
(define (extend-environment vars vals base-env)
  (if (= (length vars) (length vals))
      (cons (make-frame vars vals) base-env)
      (if (< (length vars) (length vals))
          (error "Too many arguments supplied" vars vals)
          (error "Too few arguments supplied" vars vals)))) 
```

要在环境中查找变量，我们扫描第一个框架中的变量列表。如果找到所需的变量，我们返回值列表中对应的元素。如果在当前框架中找不到变量，我们就搜索封闭环境，依此类推。如果到达空环境，我们会发出“未绑定变量”错误信号。

```
(define (lookup-variable-value var env)
  (define (env-loop env)
    (define (scan vars vals)
      (cond ((null? vars)
             (env-loop (enclosing-environment env)))
            ((eq? var (car vars))
             (car vals))
            (else (scan (cdr vars) (cdr vals)))))
    (if (eq? env the-empty-environment)
        (error "Unbound variable" var)
        (let ((frame (first-frame env)))
          (scan (frame-variables frame)
                (frame-values frame)))))
  (env-loop env)) 
```

要在指定的环境中将变量设置为新值，我们会像在`lookup-variable-value`中一样扫描变量，并在找到时更改相应的值。

```
(define (set-variable-value! var val env)
  (define (env-loop env)
    (define (scan vars vals)
      (cond ((null? vars)
             (env-loop (enclosing-environment env)))
            ((eq? var (car vars))
             (set-car! vals val))
            (else (scan (cdr vars) (cdr vals)))))
    (if (eq? env the-empty-environment)
        (error "Unbound variable -- SET!" var)
        (let ((frame (first-frame env)))
          (scan (frame-variables frame)
                (frame-values frame)))))
  (env-loop env)) 
```

要定义一个变量，我们在第一个框架中搜索变量的绑定，并在存在时更改绑定（就像在`set-variable-value!`中一样）。如果不存在这样的绑定，我们就在第一个框架中添加一个。

```
(define (define-variable! var val env)
  (let ((frame (first-frame env)))
    (define (scan vars vals)
      (cond ((null? vars)
             (add-binding-to-frame! var val frame))
            ((eq? var (car vars))
             (set-car! vals val))
            (else (scan (cdr vars) (cdr vals)))))
    (scan (frame-variables frame)
          (frame-values frame)))) 
```

## 重新审视`apply`

让我们再次看一下`apply`的定义。这次有没有更清晰的理解？

```
(define (apply procedure arguments)
  (cond ((primitive-procedure? procedure)
         (apply-primitive-procedure procedure arguments))
        ((compound-procedure? procedure)
         (eval-sequence
           (procedure-body procedure)
           (extend-environment
             (procedure-parameters procedure)
             arguments
             (procedure-environment procedure))))
        (else
         (error
          "Unknown procedure type -- APPLY" procedure)))) 
```

## 总结

在本小节中，您学到了以下内容：

1.  `apply`的定义方式

1.  如何定义和应用原始过程

1.  如何定义环境操作

## 接下来呢？

我们将学习评估器如何作为一个程序运行。
