# 将分析与执行分开

## 分析评估器

要使用本节中的思想，请获取分析元循环评估器：

```
cp ~cs61as/lib/analyze.scm . 
```

第 12 课中的元循环评估器实现很简单，但非常低效，因为表达式的语法分析与执行交织在一起。因此，如果一个程序被多次执行，其语法将被多次分析。让我们考虑一个例子。

假设我们已经定义了`factorial`函数如下：

```
(define (fact num) 
  (if (= num 0)
      1
      (* num (fact (- num 1))))) 
```

当我们计算`(fact 3)`时会发生什么？

```
eval (fact 3) 
  self-evaluating? ==> #f 
  variable? ==> #f
  quoted? ==> #f 
  assignment? definition?
  if? ==> #f
  lambda? ==> #f
  begin? ==> #f
  cond? ==> #f 
  application? ==> #t 
  eval fact
    self-evaluating? ==> #f
    variable? ==> #t
    lookup-variable-value ==> <procedure fact> 
    list-of-values (3)
      eval3 ==> 3
    apply <procedure fact> (3)
      eval (if (= num 0) ...) 
      self-evaluating? ==> #f 
      variable? ==> #f 
      quoted? ==> #f 
      assignment? ==> #f 
      definition? ==> #f
      if? ==> #t 
        eval-if (if (= num 0) ...) 
          if-predicate ==> (= num 0)
            eval (= num 0)
            self-evaluating? ==> #f
            ...
          if-alternative ==> (* num (fact (- num 1)))  
            eval (* num (fact (- num 1)))
              self-evaluating? ==> #f
              ...
              list-of-values (num (fact (- num 1)))
                ...
                eval (fact (- num 1))
                  ...
                  apply <procedure fact> (2)
                    eval (if (= num 0) ...) 
```

评估器必须四次检查过程体，确定它是一个 if 表达式，提取其组成部分，并评估这些部分（这反过来又涉及决定每个部分是什么类型的表达式）。

这就是解释性语言比[编译语言](https://en.wikipedia.org/wiki/Compiled_language)慢得多的原因之一：解释器一遍又一遍地进行程序的语法分析。编译器只进行一次分析，而编译后的程序只需执行依赖于变量实际值的计算部分。在本节中，我们将研究分析评估器，以了解如何防止程序语法的重复分析。

## 分离

`eval`接受两个参数，一个表达式和一个环境。其中，表达式参数在我们重新访问相同表达式时是相同的，而环境每次都会不同。例如，当我们计算`(fact 3)`时，我们在`num`的值为`3`的环境中评估`fact`的主体。该主体包括一个递归调用来计算`(fact 2)`，在其中我们在`num`绑定为`2`的环境中评估相同的主体。

我们的计划是查看评估过程，找到那些仅依赖于`exp`而不依赖于`env`的部分，并仅执行一次。执行此工作的过程称为`analyze`。

`analyze`的结果是什么？它必须是某种可以与环境结合以返回值的东西。解决方案是`analyze`返回一个只接受`env`作为参数的过程，并完成其余的评估。

而不是

```
(eval exp env) ==> value 
```

现在我们有

```
1\. (analyze exp) ==> exp-procedure 
2\. (exp-procedure env) ==> value 
```

**检验你的理解**

分析返回的过程接受什么类型的参数？

当我们再次评估相同的表达式时，我们只需重复第 2 步。我们所做的类似于记忆化，我们记住计算的结果以避免重复计算。不同之处在于，现在我们记住的是整体问题的部分解，而不是完整解的一部分。

我们可以通过以下方式复制原始`eval`的效果：

```
(define (eval exp env)
  ((analyze exp) env)) 
```

## `analyze`

`analyze`的结构与原始`eval`类似：

```
(define (analyze exp)
  (cond
    ((self-evaluating? exp)
      (analyze-self-eval exp)) 
    ((variable? exp)
      (analyze-var exp)) 
    ...
    ((foo? exp) (analyze-foo exp)) 
    ...)) 
```

区别在于接受表达式和环境作为参数的诸如`eval-if`之类的过程已被接受仅接受表达式作为参数的诸如`analyze-if`之类的过程所取代。这些分析过程如何工作？作为我们理解的中间步骤，这里有一个完全遵循`eval-if`结构并且不节省时间的`analyze-if`版本：

**`eval-if`:**

```
(define (eval-if exp env)
  (if (true? (eval (if-predicate exp) env))
      (eval (if-consequent exp) env) 
      (eval (if-alternative exp) env))) 
```

**`analyze-if`:**

```
(define (analyze-if exp) 
  (lambda (env)
    (if (true? (eval (if-predicate exp) env)) 
        (eval (if-consequent exp) env)
        (eval (if-alternative exp) env)))) 
```

这个版本的`analyze-if`返回一个以`env`为参数的过程，其主体与原始`eval-if`的主体完全相同。因此，如果我们这样做

```
((analyze-if some-if-expression) some-environment) 
```

结果将与我们说

```
(eval-if some-if-expression some-environment) 
```

在原始元循环评估器中。

但是我们希望改进这个`analyze-if`的第一个版本，因为它实际上并没有避免任何工作。每次调用`analyze-if`返回的过程时，它将执行原始`eval-if`执行的所有工作。

第一个版本的`analyze-if`包含三个对`eval`的调用。每个调用都对表达式进行分析，然后在给定环境中计算值。我们希望将这些`eval`调用分成两个独立的部分，并且仅在第一次执行时执行第一部分：

```
(define (analyze-if exp)
  (let ((pproc (analyze (if-predicate exp)))
        (cproc (analyze (if-consequent exp)))
        (aproc (analyze (if-alternative exp)))) 
    (lambda (env)
      (if (true? (pproc env)) 
          (cproc env)
          (aproc env))))) 
```

在这个最终版本中，`analyze-if`返回的过程不包含任何分析步骤。在调用该过程之前，所有组件都已经被分析过，因此不需要进一步分析。

效率上的最大收益来自对`lambda`表达式的处理方式。在原始元循环评估器中，为了清晰起见，我们省略了一些数据抽象，我们有

```
(define (eval-lambda exp env) (list ’procedure exp env)) 
```

评估器对`lambda`表达式实际上什么也不做，除了记住过程的文本和创建它的环境。但是在分析评估器中，我们分析过程的主体（使用`analyze-sequence`过程）；存储为过程的表示不包括其文本！相反，评估器在元循环 Scheme 中表示一个过程为底层 Scheme 中的一个过程，以及形式参数和定义环境。

（务必阅读[SICP 的第 4.1.7 节](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_sec_4.1.7)以了解所有的语法分析过程是如何实现的）。

## 级别混淆

分析评估器将表达式转换为

```
(if A B C) 
```

转换为一个过程

```
(lambda (env)
  (if (A-execution-procedure env)
      (B-execution-procedure env) 
      (C-execution-procedure env))) 
```

这可能看起来像是一种倒退；我们试图实现`if`，最终得到一个执行`if`的过程。这不是一个无限回归吗？

不，不是。执行过程中的`if`由底层 Scheme 处理，而不是由元循环 Scheme 处理。因此，没有回归；我们不为那个调用`analyze-if`。此外，底层 Scheme 中的`if`比在元 Scheme 中进行`if`的语法分析要快得多。

## 那又怎样？

表达式的语法分析是编译器的主要工作之一。在某种意义上，这个分析评估器就是一个编译器！它将 Scheme 编译成 Scheme，所以它不是一个非常有用的编译器，但是编译成其他东西，比如特���计算机的机器语言，其实并不难。

结构类似于这个的编译器被称为*递归下降*编译器。如今，在实践中，大多数编译器使用一种不同的技术（称为堆栈机），因为可以通过这种方式自动编写解析器。 （我之前提到过这是数据导向编程的一个例子。）但是，如果你手动编写解析器，最容易使用递归下降。

（在继续之前，请务必阅读 SICP 的[4.1.7](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-26.html#%_sec_4.1.7)部分）。

## 一个例子

这是一个使用分析评估器评估`阶乘`的好例子。让我们考虑以下 Scheme 代码：

```
 (define factorial
    (lambda (n)
      (if (= n 1)
          1
          (* (factorial (- n 1)) n))))
  (factorial 2) ;; low argument, so that the example is not too long))) 
```

这里有两个语句：一个定义和一个应用。

我们从定义开始，我们将在这里称之为`d`（其中`d`代表'(define (factorial n) ...)')：

```
 (eval d env)
  ((analyze d) env)
  ((analyze-definition d) env) 
```

`analyze-definition`将首先分析`definition-value`，然后创建一个执行过程，当执行时，将`define`变量名为分析的`definition-value`。

这一点至关重要。我们不只是将`lambda`分配给`factorial`，我们将*分析的*`lambda`分配给`factorial`。这将在以后提供性能优势。

因此，为了找出`factorial`的值，我们使用...当然是通过`analyze-lambda`来分析`lambda`（通过分析中的分派）。

`analyze-lambda`提供的好处真的是从*一次*分析主体开始，然后制作一个具有`analyzed`主体（一个 Scheme 过程）的过程抽象数据类型，而不是像旧的`eval`中那样简单的指令列表。

关键是，在调用我们的`lambda`时，我们不必处理解析。解析*仅*在创建`lambda`时完成。

让我们看看这个过程。

（注意：我将使用`:=`来表示存储：

```
var := value 
```

这并不是真正的 Scheme，但我认为这比有一堆`let`语句更容易。）

```
(analyze-lambda '(lambda (n) ...)') 
```

现在我们需要`analyze`主体，然后将其存储以供以后使用，这样我们就不会再次冗余地`analyze`主体。

```
analyzed-body := (analyze (lambda-body '(lambda (n) (if ...))'))

(analyze-if '(if (= n 1)
                 1
                 (* (factorial (- n 1)) n))') 
```

`analyze-if`分析其所给的所有内容，存储它，然后使用这些存储的值创建一个新的执行过程。

```
 if-pred := (analyze '(= n 1)')
  ; this is the execution procedure: (lambda (env)
  ;                                    (execute-application (analyzed/= env)

  if-true := (analyze '1')
  ; this is the execution procedure: (lambda (env) 1)

  if-false := (analyze '(* (factorial (- n 1)) n)')
  ; this is too long to write out, but it's
  ; kind of like if-pred

  ;;this is the execution procedure we return:
  ;;let's call this execution procedure 'analyzed-fact-if'
  (lambda (env)
    (if (true? (if-pred env))
        (if-true env)
        (if-false env))) 
```

现在我们知道了结果，让我们回到`analyze-lambda`。

```
 analyzed-body := analyzed-fact-if
  (analyze-lambda '(lambda (n) ...)')
     => (lambda (env) (make-procedure '(n) analyzed-body env')) 
```

我们将最后一个表达式存储到`factorial`变量中，然后我们完成了定义`factorial`。请注意，我们只在分析阶段*一次*分析主体：在评估阶段我们永远不会`analyze`！这意味着在评估期间，每次调用此`factorial`函数时，我们知道其主体包含一个`if`语句，并且`if`语句检查`n`是否等于`0`（以及如果谓词为真或假时该怎么做）。

现在，继续评估阶乘。这就是你将看到所有神秘分析工作的价值所在。

```
 (eval '(factorial 2) env') ; env has factorial definition

  ((analyze '(factorial 2)') env)

  ((analyze-application '(factorial 2)') env)

  ((lambda (env) (execute-application ...)) env)

  ((procedure-body {internal factorial value})
   (extend-environment ...)) ; extend-environment is same as old eval

  ;; let's call the extended environment, env2
  (analyzed-body env2) ; analyzed-body from definition above

 ((lambda (env)
   (if (true? (if-pred env))
       (if-true env)
       (if-false env)))
  env2)

 (if (true? (if-pred env2)) ; (= n 0)
     (if-true env2)   ; 1
     (if-false env2)) ; (* (factorial (- n 1)) n) 
```

这里，`n = 2 != 0`，所以我们最终会执行`(if-false env2)`。`if-false`会对`(factorial (- n 1))`和`n`进行`*`的应用，但这些参数已经被`分析`过了（当我们进行`analyze-lambda`时）。所以我们评估已经分析过的`(factorial (- n 1))`，即：

```
 (analyzed-factorial {result of calling analyzed (- n 1)})

  (analyzed-body env3)
  ;env3 := env2 extended with n := (- {previous n} 1) = (- 2 1) = 1

  (if (true? (if-pred env3)) ; (= n 0)
      (if-true env3)   ; 1
      (if-false env3)) ; (* (factorial (- n 1)) n) 
```

我们再次以相同的方式递归：

```
 (if (true? (if-pred env4)) ; (= n 0)
      (if-true env4) ; 1
      (if-false env4)) ; (* (factorial (- n 1)) n) 
```

这里，`n`实际上等于`0`，所以我们调用`(if-true env4)`。`if-true`忽略`env4`并返回数字`1`。然后，我们回到所有执行应用程序原语应用并将所有内容相乘。

然后我们得到... `2`。

所以，我们完成了。

请注意，在评估阶段，我们从不检查语句的语法。语法已经被查看并`分析`过了。我们只是执行这些`分析`过的语句告诉我们要做的事情。想想当计算类似`(factorial 100)`这样的东西时，这里的效率提高了多少。
