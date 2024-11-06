# 例子 - 扑克牌

如果我们能够使用抽象数据类型来表示一款纸牌游戏，那将是多么酷啊？让我们创建一个比有理数更复杂的接口，允许我们表示卡片、手牌和牌堆。通过这些抽象，我们将能够玩一些简单的纸牌游戏！

## 创建卡片

当你看任何一张卡片时，将其识别为扑克牌的两个属性是其等级和花色。当然，你可以观察其他属性，比如它的矩形形状或它的塑料表面，但这些不是你用来识别卡片的重要特性。因此，这里有我们的`make-card`构造函数，它接受一个`rank`和一个`suit`：

```
(define (make-card rank suit)
  (cons rank (first suit))) 
```

这里是它的选择器：

```
(define (rank card)
  (car card))

(define (suit card)
  (cdr card)) 
```

因此，我们可以创建一张卡片并使用以下调用提取其属性：

```
-> (define c (make-card 13 'heart))
card
-> (rank c)
13
-> (suit c)
h 
```

我们刚刚创建了红心王牌。

## 创建手牌

就像现实生活中一副牌是卡片的集合一样，在我们的抽象中，一副牌将是一组卡片的**列表**。我们下面定义了构造函数和选择器：

```
(define make-hand list) ;; constructor creates a list of cards

(define first-card car) ;; returns the first card in hand

(define rest-hand cdr) ;; returns the rest of the hand

(define empty-hand? null?) ;; checks if you have no cards in your hand 
```

注意我们将`make-hand`定义为**变量**分配给过程`list`。这是因为我们不想指定`make-hand`应该接受多少个参数 - 我们可以创建任意长度的手牌。我们只希望`make-hand`接受任意数量的卡片并将它们存储到列表中。以下是我们 ADT 的一些示例调用：

```
-> (define my-hand (make-hand (make-card 1 'heart)
                           (make-card 5 'diamond)
                           (make-card 10 'diamond)
                           (make-card 13 'club)))
my-hand
-> (first-card my-hand)
(1 . h)
-> (rest-hand my-hand)
((5 . d) (10 . d) (13 . c)) 
```

## 使用我们的实现

这就是我们表示卡片所需的全部！你有卡片，你有一组卡片。其他一切都可以根据这两个对象来定义。例如，一副牌只是一手牌，其中包含每一种等级和花色的卡片（加上两张王牌，但我们现在先忽略它）。

现在是时候使用我们的实现编写一些程序了。对于大多数纸牌游戏，卡片的等级代表着其*价值*。让我们编写一个找到你手中所有卡片总价值的程序。`total`接受一手牌并返回你卡片价值的总和。

```
(define (total hand)
    (if (empty-hand? hand)
        0
        (+ (rank (first-card hand)) (total (rest-hand hand))))) 
```

这里有一个例子：

```
-> (total my-hand)
29 
```

## 更改实现方式

如果我们改变了表示卡片的方式会发生什么？我们的`total`代码仍然有效吗？

答案是肯定的，`total`会正常工作，因为有一层*抽象*将其与牌或手牌的实现方式分隔开来。只要我们保持构造函数和选择器的名称不变，我们构建的所有程序都将继续工作。假设我们将表示卡片的方式更改为这样：

```
(define (make-card rank suit)
  (cond ((equal? suit ’heart) rank)
        ((equal? suit ’spade) (+ rank 13))
        ((equal? suit ’diamond) (+ rank 26))
        ((equal? suit ’club) (+ rank 39))
        (else (error "say what?")) ))

(define (rank card)
  (remainder card 13))

(define (suit card)
  (nth (quotient card 13) ’(heart spade diamond club))) 
```

我们的`total`程序在这种实现方式下仍然适用。在 Racket 解释器上试试吧！

使用这种编程风格，我们可以创建更大的程序。
