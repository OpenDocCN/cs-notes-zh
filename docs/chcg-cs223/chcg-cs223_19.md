# 实时队列

[`RealTimeQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/RealTimeQueue.elm)

将`reverse`和`append`组合成一个增量函数，每次执行一个步骤：

```
rotate : LazyList a -> List a -> LazyList a -> LazyList a
rotate xs ys acc =
  case (force xs, ys) of
    (Nil        , y::[])  -> lazy (\_ -> Cons y acc)
    (Cons x xs' , y::ys') ->
      lazy (\_ -> Cons x (rotate xs' ys' (lazy (\_ -> Cons y acc)))) 
```

从`BankersQueue`开始，使用普通的`List`描述`back`，并跟踪一个“schedule”`LazyList a`，它是`front`的一个需要强制的后缀。该实现强制执行不变量，即`sched`的大小等于`front`的大小减去`back`的大小。该不变量消除了显式维护`Int`大小信息的需要。

```
type Queue a = Q (LazyList a) (List a) (LazyList a) 
```

基本操作：

```
empty : Queue a
empty = Q (lazy (\_ -> Nil)) [] (lazy (\_ -> Nil))

isEmpty : Queue a -> Bool
isEmpty (Q front _ _) = case force front of {Nil -> True; _ -> False}

peek : Queue a -> Maybe a
peek (Q front _ _) = maybeHead front 
```

因为不变量的存在，当`front`和`back`的长度相同时，`sched`为空。所以在`enqueue`元素时，从`back`到`front`的旋转是在`sched`为空时启动的。

```
enqueue : a -> Queue a -> Queue a
enqueue x (Q front back sched) =
  case force sched of
    Cons _ sched' -> Q front (x::back) sched'
    Nil ->
      let front' = rotate front back (lazy (\_ -> Nil)) in
      Q front' [] front' 
```

类似地，当`back`变得比`front`更长时，`dequeue`启动旋转。

```
dequeue : Queue a -> Maybe (Queue a)
dequeue (Q front back sched) =
  case force front of
    Nil -> Nothing
    Cons _ front' ->
      case force sched of
        Cons _ sched' -> Just (Q (tail front') back sched')
        Nil ->
          let front'' = rotate front' back (lazy (\_ -> Nil)) in
          Just (Q front'' [] front'') 
```

这些操作的共同部分可以抽取到一个`exec`函数中。

```
enqueue : a -> Queue a -> Queue a
enqueue x (Q front back sched) = exec front (x::back) sched

dequeue : Queue a -> Maybe (Queue a)
dequeue (Q front back sched) =
  case force front of
    Nil       -> Nothing
    Cons _ f' -> Just (exec f' back sched)

exec front back sched =
  case force sched of
    Cons _ sched' -> Q front back sched'
    Nil ->
      let front' = rotate front back (lazy (\_ -> Nil)) in
      Q front' [] front' 
```

## 阅读

#### 推荐

+   Okasaki，第 7.1—7.2 章。虽然我们不会在课堂上仔细讨论这个材料，但鼓励你阅读这个材料以理解基本思想。
