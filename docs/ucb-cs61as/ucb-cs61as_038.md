# 使用 Let 创建局部变量

**局部变量** 是仅存在于局部环境中的变量。这里是一个例子：

```
(define (foo x)
  (define a 5)
  (+ x a)) 
```

局部环境是由函数 `foo` 创建的环境，局部变量是 `a`。请注意，`x` *不是* 局部变量，即使它也不能在 `foo` 外部访问—它正式称为参数。

## 介绍 `let`

特殊形式 `let` 本质上是对 lambda 函数的调用，排列不同。例如，看下面的 lambda 函数调用：

```
-> ((lambda (x y z) (+ x y x z)) 1 2 3)
7 
```

这等同于以下 let 语句：

```
-> (let ((x 1) (y 2) (z 3)) (+ x y x z))
7 
```

这什么时候会有用呢？两个词：局部变量。我们很少会使用 `let` 语句来简单地调用 lambda 函数。相反，我们使用它在函数内部创建局部变量。

## 一个例子：多项式

假设我们想要使用 Racket 计算给定 *x* 和 *y* 的以下多项式：

[mathjax]f(x,y) = x(1+xy)² + y (1-y) + (1+xy)(1-y)[/mathjax]

将这个丑陋的多项式重写为一个丑陋的过程：

```
(define (f x y)
  (+ (* x (+ 1 (square (* x y)))) (* y (- 1 y)) (* (+ 1 (* x y)) (- 1 y)))) 
```

呸。相反，我们可以使用一些替代：

[mathjax]\displaystyle a = 1 + xy[/mathjax]

[mathjax]\displaystyle b = 1 -y[/mathjax]

以便我们得到：

[mathjax]\displaystyle f(x,y) = xa² + yb + ab[/mathjax]

好吧，我想这样更好。在 Racket 中编写这个，我们将定义一个名为 `f-helper` 的辅助函数，以便我们可以进行替换：

```
(define (f x y)
    (define (f-helper a b)
        (+ (* x (square a))
           (* y b)
           (* a b)))
    (f-helper (+ 1 (* x y))
              (- 1 y))) 
```

花一分钟确认这是否与之前对 `f` 的定义做的事情相同。正如我们在前一节中学到的，我们实际上不需要在 `f` 中再定义一个额外的函数。相反，我们可以使用 lambda：

```
(define (f x y)
    ((lambda (a b)
        (+ (* x (square a))
           (* y b)
           (* a b)))
    (+ 1 (* x y))
    (- 1 y))) 
```

遗憾的是，即使经过所有这些替换和重新组织，它仍然有点混乱。这就是 `let` 的用武之地！

```
(define (f x y)
   (let ((a (+ 1 (* x y)))
         (b (- 1 y)))
     (+ (* x (square a)) (* y b) (* a b)))) 
```

最后，我们得到了一个更易读的初始多项式函数 `f` 版本。我们清楚地看到我们正在给 `a` 和 `b` 赋值，然后将其插入到 `let` 语句的主体中。

## `let`：一般形式

let 语句的一般结构是

```
(let ((<var1> <exp1>)
      (<var2> <exp2>)
      ...
      (<varn> <expn>))
  <body>) 
```

记住，在底层，这只不过是一个 lambda 调用。上面的结构等同于

```
((lambda (<var1> <var2> ... <varn>) <body>)
  <exp1> <exp2> ... <expn> ) 
```

在 Racket 解释器中尝试这些表达式（以及更多！）。

（注意：分号表示注释。Racket 将忽略分号后的行的其余部分。）

```
(define y 10)  

(let ((y 0)) y) ;; notice that let overrides global vars  

(let ((x 10)  
      (z x))   
    z) ;; this will break, translate to lambda to see why  

(let ((a 1))  
  (let ((a 2))  
    (let ((a 3))  
       a))) ;; nested lets are valid.   

(let ((test 'wait-what?))  
  5)  
test  ;; let only binds variables inside its body  

(let ((a 1))  
  (+ a (let ((a 2))  
    (+ a (let ((a 3))  
            a))))) ;; challenge: figure out what that last one returns, before checking interpreter 
```
