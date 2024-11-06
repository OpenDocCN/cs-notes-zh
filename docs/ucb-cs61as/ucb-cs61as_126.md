# 求值

课程的其余部分可能包含一些概念，第一次学习时可能会感到困惑，所以请仔细重新阅读那些难以理解的句子！同时，要记住，元循环求值器的核心是抽象，所以如果你暂时不理解某个实现方式，很可能会在后面的部分中解释。

## 求值

```
(define (eval-1 exp)
  (cond ((constant? exp) exp)
        ((symbol? exp) (eval exp))      ; use underlying Scheme's EVAL                        
        ((quote-exp? exp) (cadr exp))
        ((if-exp? exp)
         (if (eval-1 (cadr exp))
             (eval-1 (caddr exp))
             (eval-1 (cadddr exp))))
        ((lambda-exp? exp) exp)
        ((pair? exp) (apply-1 (eval-1 (car exp))      ; eval the operator                     
                              (map eval-1 (cdr exp))))
        (else (error "bad expr: " exp)))) 
```

这段代码看起来熟悉吗？应该是的；它是你在第 6 课学到的 Racket-1/Scheme-1 解释器的一部分！如果你看第 3 行，你会看到`eval-1`正在使用 Scheme 的`eval`过程。在第 6 课中，你不需要太担心细节，因为 Scheme 的`eval`过程处理了所有细节。但是 Scheme 的`eval`背后的细节是什么？

现在是时候看看`mc-eval`是如何编写的了。看一看，并将其与`eval-1`进行比较：

```
(define (mc-eval exp env)
  (cond ((self-evaluating? exp) exp)
  ((variable? exp) (lookup-variable-value exp env))
  ((quoted? exp) (text-of-quotation exp))
  ((assignment? exp) (eval-assignment exp env))
  ((definition? exp) (eval-definition exp env))
  ((if? exp) (eval-if exp env))
  ((lambda? exp)
    (make-procedure (lambda-parameters exp)
      (lambda-body exp)
      env))
  ((begin? exp) 
  (eval-sequence (begin-actions exp) env))
  ((cond? exp) (mc-eval (cond->if exp) env))
  ((application? exp)
    (mc-apply (mc-eval (operator exp) env)
      (list-of-values (operands exp) env)))
  (else
    (error "Unknown expression type -- EVAL" exp)))) 
```

`mc-eval`被定义为执行底层 Scheme 的`eval`工作，解释 Scheme 的语法规则，并将每个调用分解为适当的操作。如果你不理解，不要担心。我们将逐步解释这段代码。

## `mc-eval`做什么？

过程`mc-eval`接受一个表达式和一个环境作为参数。它对表达式进行分类并指导其求值。为了保持过程的通用性，我们以抽象的方式表达对表达式类型的确定，不对各种表达式类型的具体表示做任何承诺。每种表达式类型都有一个用于测试的谓词，并选择其部分的抽象方法。

当`mc-eval`处理一个过程应用时，它使用`list-of-values`生成要应用过程的参数列表。过程`list-of-values`以组合的操作数作为参数。它评估每个操作数并返回相应值的列表：

```
(define (list-of-values exps env)
  (if (no-operands? exps)
      '()
      (cons (mc-eval (first-operand exps) env)
        (list-of-values (rest-operands exps) env)))) 
```

**从左到右？从右到左？** 给定一些操作数列表，`list-of-values`将递归构造一个嵌套的`mc-eval`调用的 cons 结构。注意，我们无法确定元循环求值器从左到右还是从右到左评估操作数的顺序。它的评估顺序继承自底层 Scheme：如果`list-of-values`中`cons`的参数从左到右评估，则`list-of-values`将从左到右评估操作数；如果`cons`中的参数从右到左评估，则`list-of-values`将从右到左评估操作数。

编写一个`list-of-values`的版本，无论 Scheme 底层的求值顺序如何，都从左到右评估操作数。同时编写一个从右到左评估操作数的`list-of-values`版本。

让我们逐行查看条件中的每个表达式的作用。

## 自求值表达式

![](http://www.bbc.co.uk/music/tinthepark/2010/img/home/radio1_small_promo.jpg )

对于自评估表达式，例如数字，`mc-eval`返回表达式本身。`mc-eval`必须在环境中查找变量以找到它们的值。

+   唯一的自评估项是数字和字符串：

    (define (self-evaluating? exp) (cond ((number? exp) true) ((string? exp) true) (else false)))

请记住，单词**不是**字符串。字符串使用双引号（例如`"Hello, world!"`）。

+   变量由符号表示：

    (define (variable? exp) (symbol? exp))

## 特殊形式

![](https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcQzrLHmk190OIaf1 -xqLtrpW-BYa-yWwYHL58ZZBqQw6AVbqSZ2qw)

### 特殊形式：句子和单词

对于引用的表达式，`mc-eval`返回被引用的表达式。

请记住，Scheme 解析器会自动将表达式`'(some text here)`转换为表达式对`(quote (some text here))`。

换句话说，引用的形式为`(quote <text-of-quotation>)`：

```
(define (quoted? exp)
  (tagged-list? exp 'quote))

(define (text-of-quotation exp) (cadr exp))  ;returns just the text as a list that will print to output 
```

`Quoted?`是根据过程`tagged-list?`定义的，该过程识别以指定符号开头的列表：

```
(define (tagged-list? exp tag)
  (if (pair? exp)
      (eq? (car exp) tag)
      false)) 
```

### 特殊形式：Lambda

`lambda`表达式必须通过将 lambda 表达式指定的参数和主体与评估环境打包在一起，转换为可应用的过程。

Lambda 表达式是以符号 lambda 开头的列表：

```
(define (lambda? exp) (tagged-list? exp 'lambda))
(define (lambda-parameters exp) (cadr exp))
(define (lambda-body exp) (cddr exp)) 
```

有一个用于 lambda 表达式的构造器，它被`definition-value`使用：

```
(define (make-lambda parameters body)
  (cons 'lambda (cons parameters body))) 
```

### 特殊形式：序列

![](http://x-equals.com/blog/wp-content/editing_sequences_5_seq_1280.jpg)

+   `Eval-sequence`被`apply`用于评估过程体中的表达式序列。它还被`eval`用于评估`begin`表达式中的表达式序列。它接受一个表达式序列和一个环境作为参数，并按照它们出现的顺序评估表达式。返回的值是最终表达式的值。

    (define (eval-sequence exps env) (cond ((last-exp? exps) (mc-eval (first-exp exps) env)) (else (mc-eval (first-exp exps) env) (eval-sequence (rest-exps exps) env))))

+   `Begin`将一系列表达式打包成单个表达式。`begin`表达式需要按照它们出现的顺序评估其表达式序列。我们包括对`begin`表达式的语法操作，以从`begin`表达式中提取实际序列，以及返回序列中第一个表达式和其余表达式的选择器。

    (define (begin? exp) (tagged-list? exp 'begin)) (define (begin-actions exp) (cdr exp)) (define (last-exp? seq) (null? (cdr seq))) (define (first-exp seq) (car seq)) (define (rest-exps seq) (cdr seq))

有一个构造器`sequence->exp`（供`cond->if`使用），它将一个序列转换为单个表达式，必要时使用`begin`：

```
(define (sequence->exp seq)
  (cond ((null? seq) seq)
        ((last-exp? seq) (first-exp seq))
        (else (make-begin seq))))
(define (make-begin seq) (cons 'begin seq)) 
```

### 特殊形式：条件

![](http://callofcarly.files.wordpress.com/2011/10/if.png)

+   `Eval-if`在给定环境中评估`if`表达式的谓词部分。如果结果为真，则 eval-if 评估结果，否则评估替代项：

    (define (eval-if exp env) (if (true? (mc-eval (if-predicate exp) env)) (mc-eval (if-consequent exp) env) (mc-eval (if-alternative exp) env)))

在`eval-if`中使用`true?`突出了实现语言和实现语言之间的连接问题。`if-predicate`在正在实现的语言中进行评估，因此产生该语言中的一个值。解释器谓词`true?`将该值转换为可以由实现语言中的 if 测试的值：真实性的元循环表示可能与基础 Scheme 的表示不同。

`true?`和`false?`定义如下：

```
(define (true? x)
  (not (eq? x false)))
(define (false? x)
  (eq? x false)) 
```

+   `if`表达式需要对其部分进行特殊处理，以便在谓词为真时评估结果，否则评估替代项。

    (define (if? exp) (tagged-list? exp 'if)) (define (if-predicate exp) (cadr exp)) (define (if-consequent exp) (caddr exp)) (define (if-alternative exp) (if (not (null? (cdddr exp))) (cadddr exp) 'false))

有一个用于`if`表达式的构造函数，供`cond->if`使用将`cond`表达式转换为`if`表达式：

```
(define (make-if predicate consequent alternative)
  (list 'if predicate consequent alternative)) 
```

+   案例分析（`cond`）被转换为一系列`if`表达式，然后进行评估。

例如，

```
(cond ((> x 0) x)
      ((= x 0) (display 'zero) 0)
      (else (- x))) 
```

可以表示为：

```
(if (> x 0)
    x
    (if (= x 0)
        (begin (display 'zero)
               0)
        (- x))) 
```

有提取 cond 表达式部分的语法过程，以及一个将`cond`表达式转换为`if`表达式的过程`cond->if`。案例分析以`cond`开始，并具有一系列谓词-动作子句。如果其谓词是符号`else`，则子句是`else`子句。

```
(define (cond? exp) (tagged-list? exp 'cond))
(define (cond-clauses exp) (cdr exp))
(define (cond-else-clause? clause)
  (eq? (cond-predicate clause) 'else))
(define (cond-predicate clause) (car clause))
(define (cond-actions clause) (cdr clause))
(define (cond->if exp)
  (expand-clauses (cond-clauses exp)))

(define (expand-clauses clauses)
  (if (null? clauses)
      'false                          ; no else clause
      (let ((first (car clauses))
            (rest (cdr clauses)))
        (if (cond-else-clause? first)
            (if (null? rest)
                (sequence->exp (cond-actions first))
                (error "ELSE clause isn't last -- COND->IF"
                       clauses))
            (make-if (cond-predicate first)
                     (sequence->exp (cond-actions first))
                     (expand-clauses rest)))))) 
```

我们选择实现为语法转换的表达式（如`cond`）称为**派生表达式**。`Let`表达式也是派生表达式。

### 特殊形式：赋值和定义

![](http://2.bp.blogspot.com/-BJ9VKWsOh74/UjWTv9D1TZI/AAAAAAAAfFA/c0x9oTVm2S4/ s1600/DEFINE_TwitterAvatar_R1_eo.png)

对变量的赋值（或定义）必须递归调用`eval`来计算与变量关联的新值。必须修改环境以更改（或创建）变量的绑定。

以下过程处理对变量的赋值。它调用`eval`来找到要赋值的值，并将变量和结果值传递给`set-variable-value!`在指定环境中定义。

```
(define (eval-assignment exp env)
  (set-variable-value! (assignment-variable exp)
                       (mc-eval (assignment-value exp) env)
                       env)
  'ok) 
```

变量的定义以类似的方式处理：

```
(define (eval-definition exp env)
  (define-variable! (definition-variable exp)
                    (mc-eval (definition-value exp) env)
                    env)
  'ok) 
```

按照惯例，符号`ok`被返回为赋值或定义的值。

现在让我们看看赋值表达式是如何表示的。

赋值的形式为`(set! <var> <value>)`：

```
(define (assignment? exp)
  (tagged-list? exp 'set!))
(define (assignment-variable exp) (cadr exp))
(define (assignment-value exp) (caddr exp)) 
```

定义的形式为`(define <var> <value>)`或形式

```
(define (var parameter1 ... parametern)
  body) 
```

后一种形式（标准过程定义）可以重写为：

```
(define var
  (lambda (parameter1 ... parametern)
          body)) 
```

相应的语法过程如下：

```
(define (definition? exp)
  (tagged-list? exp 'define))
(define (definition-variable exp)
  (if (symbol? (cadr exp))
      (cadr exp)
      (caadr exp)))
(define (definition-value exp)
  (if (symbol? (cadr exp))
      (caddr exp)
      (make-lambda (cdadr exp)   ; formal parameters
                   (cddr exp)))) ; body 
```

**And 和 Or**

回顾第 1 单元中特殊形式`and`和`or`的定义：

+   and：表达式从左到右进行评估。如果任何表达式评估为假，则返回`false`；任何剩余的表达式都不会被评估。如果所有表达式评估为真值，则返回最后一个表达式的值。如果没有表达式，则返回 true。

+   or：表达式从左到右进行评估。如果任何表达式评估为真值，则返回该值；任何剩余的表达式都不会被评估。如果所有表达式评估为假，或者没有表达式，则返回`false`。

通过定义适当的语法过程和评估过程`eval-and`和`eval-or`，将`and`和`or`安装为评估器的新特殊形式。或者，展示如何将`and`和`or`实现为派生表达式。

## mc-eval 定义再次审视

让我们再次看看`mc-eval`的定义。现在你明白了吗？

```
(define (mc-eval exp env)
  (cond ((self-evaluating? exp) exp)
  ((variable? exp) (lookup-variable-value exp env))
  ((quoted? exp) (text-of-quotation exp))
  ((assignment? exp) (eval-assignment exp env))
  ((definition? exp) (eval-definition exp env))
  ((if? exp) (eval-if exp env))
  ((lambda? exp)
    (make-procedure (lambda-parameters exp)
      (lambda-body exp)
      env))
  ((begin? exp) 
    (eval-sequence (begin-actions exp) env))
  ((cond? exp) (mc-eval (cond->if exp) env))
  ((application? exp)
    (mc-apply (mc-eval (operator exp) env)
      (list-of-values (operands exp) env)))
  (else
    (error "Unknown expression type -- EVAL" exp)))) 
```

*等等，等等，apply 是什么？我不知道那是什么！*

我们将在下一小节中探讨这个问题。

以下哪些在其定义中使用了 mc-eval？可能有多个正确答案，因此请逐个检查每个答案。

## 要点

在本小节中，您了解了 Scheme 如何使用`mc-eval`和其他过程评估表达式。

## 接下来呢？

前往下一小节，了解 Scheme 如何应用评估的表达式！
