# 队列

`Queue`抽象使用先进先出（FIFO）策略来移除（“出列”）元素。

```
enqueue : a -> Queue a -> Queue a
dequeue : Queue a -> Maybe (Queue a)
peek    : Queue a -> Maybe a 
```

在没有*O(1)*时间访问`List`中最后一个元素的情况下，在纯函数语言中提供高效的`Queue`操作需要特别注意。

### 第一次尝试 — [`SlowQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Queues/SlowQueue.elm)

```
type Queue a = Q (List a)

empty : Queue a
empty = Q []

isEmpty : Queue a -> Bool
isEmpty q = q == empty

enqueue : a -> Queue a -> Queue a
enqueue x (Q xs) = Q (xs ++ [x])

dequeue : Queue a -> Maybe (Queue a)
dequeue (Q xs) = case xs of
  _::xs' -> Just (Q xs')
  []     -> Nothing

peek : Queue a -> Maybe a
peek (Q xs) = case xs of
  x::_   -> Just x
  []     -> Nothing 
```

运行时间：

+   `enqueue` : *Θ(n)*

+   `dequeue` : *O(1)*

+   `peek` : *O(1)*

### 第二次尝试 — [`AnotherSlowQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Queues/AnotherSlowQueue.elm)

```
type Queue a = Front (List a) | Back (List a)

empty : Queue a
empty = Front []

isEmpty : Queue a -> Bool
isEmpty q = case q of
  Front [] -> True
  Back []  -> True
  _        -> False

enqueue : a -> Queue a -> Queue a
enqueue x q = case q of
  Front xs -> Back (x :: List.reverse xs)
  Back xs  -> Back (x :: xs)

dequeue : Queue a -> Maybe (Queue a)
dequeue q = case q of
  Back []      -> Nothing
  Back (x::xs) -> Just (Back xs)
  Front xs     -> dequeue (Back (List.reverse xs))

peek : Queue a -> Maybe a
peek q = case q of
  Back []      -> Nothing
  Back (x::_)  -> Just x
  Front xs     -> peek (Back (List.reverse xs)) 
```

运行时间：

+   `enqueue` : *O(n)*

+   `dequeue` : *O(n)*

+   `peek` : *O(n)*

### 第三次尝试 — [`MediumQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Queues/MediumQueue.elm)

```
type Queue a = Q { front: List a, back: List a }

mkQ f b = Q {front = f, back = b}

empty : Queue a
empty = mkQ [] []

isEmpty : Queue a -> Bool
isEmpty q = q == empty

enqueue : a -> Queue a -> Queue a
enqueue x (Q {front, back}) = mkQ front (x::back)

dequeue : Queue a -> Maybe (Queue a)
dequeue (Q {front, back}) = case (front, back) of
  (_::f', _) -> Just (mkQ f' back) 
  ([], [])   -> Nothing
  ([], _)    -> dequeue (mkQ (List.reverse back) [])

peek : Queue a -> Maybe a
peek (Q {front, back}) = case (front, back) of
  (x::_, _)  -> Just x
  ([], [])   -> Nothing
  ([], _)    -> peek (mkQ (List.reverse back) []) 
```

运行时间：

+   `enqueue` : *O(1)*

+   `dequeue` : *O(n)*

+   `peek` : *O(n)*

### 最终版本 — [`FastQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Queues/FastQueue.elm)

与上一个版本相同的表示`Q {front, back}`，但具有不变性`front = []`意味着`back = []`。

```
enqueue : a -> Queue a -> Queue a
enqueue x (Q {front, back}) = case (front, back) of
  ([], _) -> mkQ [x] []
  _       -> mkQ front (x::back)

dequeue : Queue a -> Maybe (Queue a)
dequeue (Q {front, back}) = case (front, back) of
  ([]   , _) -> Nothing
  (_::[], _) -> Just (mkQ (List.reverse back) [])
  (_::f', _) -> Just (mkQ f' back) 

peek : Queue a -> Maybe a
peek (Q {front, back}) = case (front, back) of
  (x::_, _) -> Just x
  ([]  , _) -> Nothing 
```

我们可以从`enqueue`和`dequeue`中提取出一个共同的模式。注意到`checkFront`的参数`f`和`b`不一定满足不变性，但输出的`Queue`满足。

```
checkFront : List a -> List a -> Queue a
checkFront f b = case (f, b) of
  ([], _) -> mkQ (List.reverse b) []
  (_ , _) -> mkQ f b

enqueue' : a -> Queue a -> Queue a
enqueue' x (Q {front, back}) = checkFront front (x::back)

dequeue' : Queue a -> Maybe (Queue a)
dequeue' (Q {front, back}) = case front of
  []    -> Nothing
  _::f' -> Just (checkFront f' back) 
```

运行时间：

+   `enqueue` : *O(1)*

+   `dequeue` : *O(n)*

+   `peek` : *O(1)*

然而，`dequeue`的最坏情况边界并不能完全说明问题，因为它通常在*O(1)*时间内运行，只偶尔在*O(n)*时间内运行。通过摊销渐近分析，我们将能够证明`dequeue`平均运行时间为*O(1)*。

## 阅读

#### 必需的

+   Okasaki，第 5.2 章
