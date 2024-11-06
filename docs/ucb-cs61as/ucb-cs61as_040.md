# HOFs - 作为返回值的过程

我们已经看到如何编写一个接受另一个过程作为参数的过程。事实证明，我们也可以做相反的事情 - 我们可以创建一个*返回*过程的过程！返回过程是进一步抽象的好方法。我们可以让程序为我们创建过程，而不是直接创建过程！根据我们给程序的参数，它可以创建许多不同的过程。

## 例子：`make-power`

（我们实际上并没有制造幂。那将是滥用权力；)。）

假设我们想要定义一个过程`sum-powers`，它将计算`a`和`b`之间每个数字的第`n`次幂并将它们相加。我们已经有我们的`procedure`，如下所示：

```
(define (sum f a b)
    (if (> a b)
        0
        (+ (f a) (sum f (+ a 1) b)))) 
```

根据我们迄今所学到的，它看起来像这样：

```
(define (sum-powers n a b)
    (sum (lambda (x) (expt x n)) a b)) 
```

但是，如果我们创建一个名为`make-power`的新函数，该函数根据给定的幂`n`返回一个*函数*，该函数接受一个数字`x`并返回其第`n`次幂？它看起来像这样：

```
(define (make-power n)
    (lambda (x) (expt x n))) 
```

正如我们之前指出的，lambda 函数返回函数。这意味着如果我们将对`make-power`的调用定义为 lambda 函数，它将返回一个函数！现在我们可以这样做：

```
(define square (make-power 2))
(define cube (make-power 3)) 
```

现在我们可以这样重写我们的 sum-powers 函数：

```
(define (sum-powers n a b)
    (sum (make-power n) a b)) 
```

注意我们在抽象方面取得了多大进步。在这个实验室的开始，我们为每种不同类型的求和定义了不同的过程：`sum-doubles`，`sum-squares`和`sum-cubes`。

但现在，我们已经将求和本身抽象化，这样我们可以用一行清晰地表达任何求和。
