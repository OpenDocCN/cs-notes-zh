# 异常。

+   我们已经看到一些“返回”任何类型的函数。

    ```
    undefined :: a error :: String -> a
    ```

    +   返回类型可以是任意的，因为函数实际上并不返回。

+   这些函数抛出*语言级别*的异常。

    +   要直接使用异常，请按照以下方式导入[`Control.Exception`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Exception.html)：

    ```
    import Prelude hiding (catch) -- not necessary with new GHCs import Control.Exception
    ```

    +   旧的`Prelude`有一个旧的、不太通用的`catch`版本，你应该避免使用。

        （`hiding`关键字阻止特定符号的导入）

    +   [`Control.Exception`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Exception.html)让你可以访问以下符号：

    ```
    class (Typeable e, Show e) => Exception e where ... throw :: Exception e => e -> a throwIO :: Exception e => e -> IO a catch :: Exception e => IO a -> (e -> IO a) -> IO a
    ```

## 简单示例。

```
{-# LANGUAGE DeriveDataTypeable #-} import Prelude hiding (catch) import Control.Exception import Data.Typeable data MyError = MyError String deriving (Show, Typeable) instance Exception MyError catcher :: IO a -> IO (Maybe a) catcher action = fmap Just action `catch` handler where handler (MyError msg) = do putStrLn msg; return Nothing
```

```
*Main> catcher $ readFile "/dev/null" Just "" *Main> catcher $ throwIO $ MyError "something bad" something bad Nothing
```

+   需要`DeriveDataTypeable`语言扩展（稍后讲座）。

+   `handler`的类型无法推断（使用构造函数或类型签名）。

    +   构造模式`e@(SomeException _)`捕获所有异常。

## 纯代码中的异常。

+   先前的示例在 IO 操作周围包裹了`catcher`。

+   可以在纯代码中`throw`异常，但只能在`IO`中`catch`它们。

    +   这是因为评估顺序取决于实现。

    +   `(error "one") + (error "two")`会抛出哪个错误？

        可能是非确定性的，如果`catch`限制在`IO` Monad 中，则[可以接受](http://research.microsoft.com/en-us/um/people/simonpj/papers/imprecise-exn.htm)。

+   在`IO`中，使用`throwIO`（而不是`throw`）使异常序列精确。

    ```
     do x <- throwIO (MyError "one") -- this exception thrown y <- throwIO (MyError "two") -- this code not reached return $ x + y
    ```

    +   通常只在无法使用`throwIO`时使用`throw`。

+   纯异常对于错误和未实现的代码非常有用，例如：

    ```
    -- Simplified version of functions in standard Prelude: error :: String -> a error a = throw (ErrorCall a) undefined :: a undefined = error "Prelude.undefined"
    ```

## 异常和惰性。

+   考虑以下函数。

    ```
    pureCatcher :: a -> IO (Maybe a) pureCatcher a = (a `seq` return (Just a)) `catch` \(SomeException _) -> return Nothing
    ```

    ```
    pureCatcher $ 1 + 1 Just 2 *Main> pureCatcher $ 1 `div` 0 Nothing *Main> pureCatcher (undefined :: String) Nothing
    ```

+   如果你这样做会发生什么？

    ```
    *Main> pureCatcher (undefined:undefined :: String)
    ```

## 异常和惰性。

+   考虑以下函数。

    ```
    pureCatcher :: a -> IO (Maybe a) pureCatcher a = (a `seq` return (Just a)) `catch` \(SomeException _) -> return Nothing
    ```

    ```
    pureCatcher $ 1 + 1 Just 2 *Main> pureCatcher $ 1 `div` 0 Nothing *Main> pureCatcher (undefined :: String) Nothing
    ```

+   如果你这样做会发生什么？

    ```
    *Main> pureCatcher (undefined:undefined :: String) Just "*** Exception: Prelude.undefined
    ```

## 异常和惰性。

+   考虑以下函数。

    ```
    pureCatcher :: a -> IO (Maybe a) pureCatcher a = (a `seq` return (Just a)) `catch` \(SomeException _) -> return Nothing
    ```

    ```
    pureCatcher $ 1 + 1 Just 2 *Main> pureCatcher $ 1 `div` 0 Nothing *Main> pureCatcher (undefined :: String) Nothing
    ```

+   如果你这样做会发生什么？

    ```
    *Main> pureCatcher (undefined:undefined :: String) Just "*** Exception: Prelude.undefined
    ```

+   `catch`只在实际评估 thunks 时才捕获异常！

## 异常和惰性继续。

+   评估列表不会评估头部或尾部。

    ```
    *Main> seq (undefined:undefined) () ()
    ```

    +   只评估构造函数（即`(:)`或`[]`）。

+   练习：强制评���列表的每个元素。

    +   编写具有以下签名的类似于`seq`的函数，它在评估第二个参数之前评估列表的每个元素。

    ```
    seqList :: [a] -> b -> b
    ```

    ```
    *Main> seqList [1, 2, 3] () () *Main> seqList [1, 2, 3, undefined] () *** Exception: Prelude.undefined
    ```

## 解决方案。

```
seqList :: [a] -> b -> b seqList [] b = b seqList (a:as) b = seq a $ seqList as b
```

+   注意，库中有一个名为[`deepseq`](http://hackage.haskell.org/package/deepseq-1.3.0.2/docs/Control-DeepSeq.html#v:deepseq)的函数，可以为许多常见数据类型执行此操作。

## 还有一些异常函数。

+   `try`通常返回`Right a`，如果发生异常则返回`Left e`。

    ```
    try :: Exception e => IO a -> IO (Either e a)
    ```

+   `finally`和`onException`运行清理操作。

    ```
    finally :: IO a -> IO b -> IO a -- cleanup always onException :: IO a -> IO b -> IO a -- after exception
    ```

    +   清理操作（`b`）的结果被丢弃。

+   `catchJust`仅捕获与值上的谓词匹配的异常。

    ```
    catchJust :: Exception e => (e -> Maybe b) -> IO a -> (b -> IO a) -> IO a readFileIfExists f = catchJust p (readFile f) (\_ -> return "") where p e = if isDoesNotExistError e then Just e else Nothing
    ```

    ```
    *Main> readFileIfExists "/nosuchfile" "" *Main> readFileIfExists "/etc/shadow" *** Exception: /etc/shadow: openFile: permission denied ...
    ```

## 单子异常。

+   语言级别的异常对于非`IO`操作可能很麻烦。

    +   非确定性很烦人。

    +   经常希望在不假设`IO`单子的情况下检测错误。

    +   许多建立在`IO`之上的单子也无法捕获异常。

+   通常最好在 Monad 中实现错误处理。

    +   回想一下`Maybe` Monad，可以使用`Nothing`表示失败。

    ```
    instance Monad Maybe where (Just x) >>= k = k x Nothing >>= _ = Nothing return = Just fail _ = Nothing
    ```

    +   注意，在`do`块中绑定模式匹配失败时调用`fail`方法。

    ```
    *Main> (do 1 <- return 2; return 3) :: Maybe Int Nothing
    ```

## Haskell 线程

+   Haskell 在[`Control.Concurrent`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Concurrent.html)中实现了用户级线程

    +   线程轻量级（在时间和空间上）

    +   在其他语言中会使用更便宜的结构的地方使用线程

    +   运行时以非阻塞的方式模拟阻塞的操作系统调用

    +   线程切换可以在任何可能调用 GC 的时候发生

+   `forkIO` 调用创建一个新线程：

    ```
    forkIO :: IO () -> IO ThreadId -- creates a new thread
    ```

+   还有一些非常有用的线程函数：

    ```
    throwTo :: Exception e => ThreadId -> e -> IO () killThread :: ThreadId -> IO () -- = flip throwTo ThreadKilled threadDelay :: Int -> IO () -- sleeps for # of µsec myThreadId :: IO ThreadId
    ```

## 例子：超时

+   执行`IO`操作，或在µ秒数后中止

    +   [`System.Timeout`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/System-Timeout.html)有一个稍微好一点的版本的这个函数

```
data TimedOut = TimedOut UTCTime deriving (Eq, Show, Typeable) instance Exception TimedOut timeout :: Int -> IO a -> IO (Maybe a) timeout usec action = do -- Create unique exception val (for nested timeouts): expired <- fmap TimedOut getCurrentTime ptid <- myThreadId let child = do threadDelay usec throwTo ptid expired parent = do ctid <- forkIO child result <- action killThread ctid return $ Just result catchJust (\e -> if e == expired then Just e else Nothing) parent (\_ -> return Nothing)
```

## [`MVar`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Concurrent-MVar.html)

+   [`MVar`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Concurrent-MVar.html)类型允许线程通过共享变量进行通信

    +   一个`MVar t`是一个可变变量，类型为`t`，它可以是*满的*或者*空的*

    ```
    newEmptyMVar :: IO (MVar a) -- create empty MVar newMVar :: a -> IO (MVar a) -- create full MVar given val takeMVar :: MVar a -> IO a putMVar :: MVar a -> a -> IO ()
    ```

    +   如果一个`MVar`是满的，`takeMVar`会使其为空并返回以前的内容

    +   如果一个`MVar`是空的，`putMVar`会用一个值填充它

    +   取一个空的`MVar`或者放一个满的`MVar`会使线程进入睡眠状态，直到`MVar`变得可用

    +   只有一个线程会被唤醒，如果有几个线程阻塞在同一个`MVar`上

    +   还有`MVar`调用的非阻塞版本

    ```
    tryTakeMVar :: MVar a -> IO (Maybe a) -- Nothing if empty tryPutMVar :: MVar a -> a -> IO Bool -- False if full
    ```

## 例子：乒乓球基准测试

```
import Control.Concurrent import Control.Exception import Control.Monad pingpong :: Bool -> Int -> IO () pingpong v n = do mvc <- newEmptyMVar -- MVar read by child mvp <- newEmptyMVar -- MVar read by parent let parent n | n > 0 = do when v $ putStr $ " " ++ show n putMVar mvc n takeMVar mvp >>= parent | otherwise = return () child = do n <- takeMVar mvc putMVar mvp (n - 1) child tid <- forkIO child parent n `finally` killThread tid when v $ putStrLn ""
```

```
*Main> pingpong True 10 10 9 8 7 6 5 4 3 2 1
```

## 旁注：基准测试

+   Bryan 有一个厉害的基准测试库 [criterion](http://hackage.haskell.org/package/criterion)

```
import Criterion.Main ... main :: IO () main = defaultMain [ bench "thread switch test" mybench ] where mybench = pingpong False 10000
```

```
$ ghc -O pingpong.hs [1 of 1] Compiling Main ( pingpong.hs, pingpong.o ) Linking pingpong ... $ ./pingpong ... benchmarking thread switch test mean: 3.774590 ms, lb 3.739223 ms, ub 3.808865 ms, ci 0.950 ...
```

+   20,000 次线程切换约为 3.8 毫秒 = 约为 190 纳秒/切换

## 操作系统线程

+   GHC 也有*两个*版本的 Haskell 运行时

    +   默认情况下，所有的 Haskell 线程都在一个操作系统线程中运行

    +   链接时加上 `-threaded` 来允许 OS 线程（`pthread_create`）

+   `forkOS` 调用创建一个 Haskell 线程*绑定*到一个新的操作系统线程上

    ```
    forkOS :: IO () -> IO ThreadId
    ```

+   同样，当链接时使用 `-threaded`，初始线程是被绑定的

+   哇... 发生了什么？ `-threaded`慢了 30 倍？

```
$ rm pingpong $ ghc -threaded -O pingpong.hs Linking pingpong ... $ ./pingpong ... mean: 121.1729 ms, lb 120.5601 ms, ub 121.7044 ms, ci 0.950 ...
```

## 绑定与非绑定线程

+   没有`-threaded`，所有的 Haskell 线程都在一个操作系统线程中运行

    +   线程切换基本上只是一个过程调用，即超级快速

+   `-threaded`引入了多个操作系统级线程

    +   一些 Haskell 线程是绑定到特定的 OS 线程上的

    +   *非绑定*的 Haskell 线程共享（并在之间迁移）操作系统线程

    +   *非绑定*的 Haskell 线程和没有`-threaded`的性能相同

+   初始线程被绑定，所以我们实际上是在对 Linux 进行基准测试

    +   可以用`forkIO`包装父线程使其变为非绑定状态

    ```
    wrap :: IO a -> IO a wrap action = do mv <- newEmptyMVar _ <- forkIO $ (action >>= putMVar mv) `catch` \e@(SomeException _) -> putMVar mv (throw e) takeMVar mv
    ```

    +   但是库有更好的函数[`runInUnboundThread`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Concurrent.html#v:runInUnboundThread)

## 操作系统线程有什么用？

+   如果一个非绑定线程阻塞，可能会阻塞整个程序

    +   Unix 运行时试图避免阻塞系统调用，但无法避免像文件系统 IO 和页面交换之类的阻塞

    +   还与外部函数接口（FFI）相关

    +   GHC 允许向 C 代码调用两种类型的调用，`safe` 和 `unsafe`

    +   使用 `-threaded`，GHC 确保 `safe` FFI 调用在单独的 OS 线程中运行

    +   未绑定线程中的 `unsafe` FFI 调用可能会阻塞其他线程

+   FFI 函数可能期望从同一线程调用

    +   例如，从迁移的未绑定线程调用 `pthread_getspecific` 的外部代码可能会混淆

+   可能想要覆盖调度程序并在特定 CPU 上运行

    +   例如，查看[`forkOn`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Concurrent.html#v:forkOn)

## 异步异常

+   一些方便的 `MVar` 实用函数用于更新值

    ```
    modifyMVar :: MVar a -> (a -> IO (a, b)) -> IO b modifyMVar_ :: MVar a -> (a -> IO a) -> IO ()
    ```

    +   例如，"`modifyMVar x (\n -> return (n+1, n))`" 就像 C 中的 "`x++`"

+   你会如何实现 `modifyMVar`？

    ```
    modifyMVar :: MVar a -> (a -> IO (a,b)) -> IO b modifyMVar m action = do v0 <- takeMVar m (v, r) <- action v0 `onException` putMVar m v0 putMVar m v return r
    ```

    +   有人看到问题了吗？（提示：记住 `throwTo`，`killThread`）

## 异步异常

+   一些方便的 `MVar` 实用函数用于更新值

    ```
    modifyMVar :: MVar a -> (a -> IO (a, b)) -> IO b modifyMVar_ :: MVar a -> (a -> IO a) -> IO ()
    ```

    +   例如，"`modifyMVar x (\n -> return (n+1, n))`" 就像 C 中的 "`x++`"

+   你会如何实现 `modifyMVar`？

    ```
    modifyMVar :: MVar a -> (a -> IO (a,b)) -> IO b modifyMVar m action = do v0 <- takeMVar m -- -------------- oops, race condition (v, r) <- action v0 `onException` putMVar m v0 putMVar m v return r
    ```

    +   如果另一个线程在当前线程在 `takeMVar` 和 `onException` 之间时调用 `killThread` 会怎么样

    +   几张幻灯片前的 `timeout` 和 `wrap` 函数存在相同问题

## 屏蔽异常

+   [`mask`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Exception.html#v:mask) 函数可以规避这种竞争条件

    ```
    mask :: ((forall a. IO a -> IO a) -> IO b) -> IO b
    ```

    +   这是一个有趣的类型签名--使用了一个叫做 `RankNTypes` 的扩展。暂时忽略 "`forall a.`"--只是使函数更灵活

    +   `mask $ \f -> b` 使用异步异常*屏蔽*运行动作 `b`

    +   函数 `f` 允许再次为动作取消*屏蔽*异常

    +   如果线程休眠（例如在 `takeMVar` 中），异常也会取消屏蔽

+   例如：修复 `modifyMVar`

    ```
    modifyMVar :: MVar a -> (a -> IO (a,b)) -> IO b modifyMVar m action = mask $ \unmask -> do v0 <- takeMVar m -- automatically unmasked while waiting (v, r) <- unmask (action v0) `onException` putMVar m v0 putMVar m v return r
    ```

## 屏蔽异常（续）

+   `forkIO` 保留当前屏蔽状态

    +   可以在子线程中使用 `unmask` 函数

+   例如：修复 `wrap` 函数

```
wrap :: IO a -> IO a -- Fixed version of wrap wrap action = do mv <- newEmptyMVar mask $ \unmask -> do tid <- forkIO $ (unmask action >>= putMVar mv) `catch` \e@(SomeException _) -> putMVar mv (throw e) let loop = takeMVar mv `catch` \e@(SomeException _) -> throwTo tid e >> loop loop
```

+   注意我们在父线程中不调用 `unmask`

    +   `loop` 在 `takeMVar` 上休眠，这会隐式取消屏蔽

    +   在休眠时取消屏蔽通常是你想要的，但可以通过[uninterruptibleMask](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Exception.html#v:uninterruptibleMask)来避免

## [`bracket`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Exception.html#v:bracket) 函数

+   `mask` 很棘手，但库函数[`bracket`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Exception.html#v:bracket)简化了使用

    ```
    bracket :: IO a -> (a -> IO b) -> (a -> IO c) -> IO c
    ```

+   例如：处理文件而不泄漏句柄

    ```
    bracket (openFile "/etc/mtab" ReadMode) -- first hClose -- last (\h -> hGetContents h >>= doit) -- main
    ```

+   例如：修复我们 `timeout` 示例中的 `parent` 函数

    ```
     parent = do ctid <- forkIO child -- old code, result <- action -- bad if async killThread ctid -- exception return $ Just result
    ```

    ```
     parent = bracket (forkIO child) killThread $ -- new code \_ -> fmap Just action
    ```

## 使用 `MVar` 工作

+   `MVar` 作为互斥锁运行得很好：

    ```
    -- type introduces type alias (like typedef in C) type Mutex = MVar () mutex_create :: IO Mutex mutex_create = newMVar () mutex_lock, mutex_unlock :: Mutex -> IO () mutex_lock = takeMVar mutex_unlock mv = putMVar mv () mutex_synchronize :: Mutex -> IO a -> IO a mutex_synchronize mv action = bracket (mutex_lock mv) (\_ -> mutex_unlock mv) (\_ -> action)
    ```

+   请注意任何人都可以解锁 `Mutex`，如果它被锁定

    +   如果调用者没有持有锁，你会如何抛出断言失败？

## 替代 `Mutex`

+   使用*完整的* `MVar` 而不是空的来表示锁已持有

    ```
    type Mutex = MVar ThreadId mutex_create :: IO Mutex mutex_create = newEmptyMVar mutex_lock, mutex_unlock :: Mutex -> IO () mutex_lock mv = myThreadId >>= putMVar mv mutex_unlock mv = do mytid <- myThreadId lockTid <- tryTakeMVar mv unless (lockTid == Just mytid) $ error "mutex_unlock"
    ```

    +   在 `MVar` 中存储锁所有者的 `ThreadId`

+   你会如何实现条件变量？

    +   许多条件变量的用途不适用于异步异常

    +   所以让我们不要为这个问题担心 `mask`...

## 条件变量

```
data Cond = Cond (MVar [MVar ()]) cond_create :: IO Cond cond_create = liftM Cond $ newMVar [] -- liftM is fmap for Monads (i.e., no required Functor instance): -- liftM f m1 = do x <- m1; return (f m1) cond_wait :: Mutex -> Cond -> IO () cond_wait m (Cond waiters) = do me <- newEmptyMVar modifyMVar_ waiters $ \others -> return $ others ++ [me] mutex_unlock m -- note we don't care if preempted after this takeMVar me `finally` mutex_lock m cond_signal, cond_broadcast :: Cond -> IO () cond_signal (Cond waiters) = modifyMVar_ waiters wakeone where wakeone [] = return [] wakeone (w:ws) = putMVar w () >> return ws cond_broadcast (Cond waiters) = modifyMVar_ waiters wakeall where wakeall ws = do mapM_ (flip putMVar ()) ws return []
```

+   关键思想：在`MVar`中放置`MVar`非常强大

## 通道

+   [`Control.Concurrent.Chan`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Concurrent-Chan.html)提供了无限制的*通道*

    +   实现为两个`MVar` -- 用于读取和写入`Stream`的端点

    ```
    data Item a = Item a (Stream a) type Stream a = MVar (Item a) data Chan a = Chan (MVar (Stream a)) (MVar (Stream a))
    ```

![](img/8055b0591ad69832c238495ef6b072c6.svg)

## 通道实现[简化]

```
data Item a = Item a (Stream a) type Stream a = MVar (Item a) data Chan a = Chan (MVar (Stream a)) (MVar (Stream a)) newChan :: IO (Chan a) newChan = do empty <- newEmptyMVar liftM2 Chan (newMVar empty) (newMVar empty) -- liftM2 is like liftM for functions of two arguments: -- liftM2 f m1 m2 = do x1 <- m1; x2 <- m2; return (f x1 x2) writeChan :: Chan a -> a -> IO () writeChan (Chan _ w) a = do empty <- newEmptyMVar modifyMVar_ w $ \oldEmpty -> do putMVar oldEmpty (Item a empty) return empty readChan :: Chan a -> IO a readChan (Chan r _) = modifyMVar r $ \full -> do (Item a newFull) <- takeMVar full return (newFull, a)
```

## 网络

+   在[`Network`](http://hackage.haskell.org/packages/archive/network/latest/doc/html/Network.html)中有高级别的流（TCP 和 Unix 域）套接字支持

    ```
    connectTo :: HostName -> PortID -> IO Handle listenOn :: PortID -> IO Socket accept :: Socket -> (Handle, HostName, PortNumber) sClose :: Socket -> IO () hClose :: Handle -> IO ()
    ```

+   练习：网络版的石头剪刀布。定义：

    ```
    withClient :: PortID -> (Handle -> IO a) -> IO a
    ```

+   这个程序接受连接，进行单局游戏，然后退出

    ```
    *Main> withClient (PortNumber 1617) (computerVsUser Rock)
    ```

    ```
    $ nc localhost 1617 Please enter one of [Rock,Paper,Scissors] Rock You Tie
    ```

+   从上周的代码开始：`wget` [`cs240h.stanford.edu/rock2.hs`](http://cs240h.stanford.edu/rock2.hs)

## 解决方案

```
withClient :: PortID -> (Handle -> IO a) -> IO a withClient listenPort fn = bracket (listenOn listenPort) sClose $ \s -> do bracket (accept s) (\(h, _, _) -> hClose h) $ \(h, host, port) -> do putStrLn $ "Connection from host " ++ host ++ " port " ++ show port fn h
```

## 练习

+   构建一个名为`netrock`的程序，让两个用户相互对战，并在一局游戏结束后退出

    ```
    $ nc localhost 1617 Please enter one of [Rock,Paper,Scissors] Rock You Win
    ```

    ```
    $ nc localhost 1617 Please enter one of [Rock,Paper,Scissors] Scissors You Lose
    ```

+   从这里开始：`wget` [`cs240h.stanford.edu/netrock.hs`](http://cs240h.stanford.edu/netrock.hs)，实现：

    ```
    netrock :: PortID -> IO ()
    ```

    +   你可能会发现定义和使用以下内容很有用：

        ```
        play :: MVar Move -> MVar Move -> (Handle, HostName, PortNumber) -> IO () play myMoveMVar opponentMoveMVar (h, host, port) = do
        ```

    +   如果你的操作系统缺少`nc`：`wget` [`cs240h.stanford.edu/netcat.hs`](http://cs240h.stanford.edu/netcat.hs)

## 解决方案

```
play :: MVar Move -> MVar Move -> (Handle, HostName, PortNumber) -> IO () play myMoveMVar opponentMoveMVar (h, host, port) = do putStrLn $ "Connection from host " ++ host ++ " port " ++ show port myMove <- getMove h putMVar myMoveMVar myMove opponentMove <- takeMVar opponentMoveMVar let o = outcome myMove opponentMove hPutStrLn h $ "You " ++ show o netrock :: PortID -> IO () netrock listenPort = bracket (listenOn listenPort) sClose $ \s -> do mv1 <- newEmptyMVar mv2 <- newEmptyMVar let cleanup mv (h,_,_) = do tryPutMVar mv (error "something blew up") hClose h wait <- newEmptyMVar forkIO $ bracket (accept s) (cleanup mv1) (play mv1 mv2) `finally` putMVar wait () bracket (accept s) (cleanup mv2) (play mv2 mv1) takeMVar wait
```

## 网络

+   在[`Network.Socket`](http://hackage.haskell.org/packages/archive/network/latest/doc/html/Network-Socket.html)中还有低级别的 BSD 套接字支持

    ```
    socket :: Family -> SocketType -> ProtocolNumber -> IO Socket connect :: Socket -> SockAddr -> IO () bindSocket :: Socket -> SockAddr -> IO () listen :: Socket -> Int -> IO () accept :: Socket -> IO (Socket, SockAddr)
    ```

    +   [`getAddrInfo`](http://hackage.haskell.org/packages/archive/network/latest/doc/html/Network-Socket.html#v:getAddrInfo)像[[RFC3493]](http://tools.ietf.org/html/rfc3493)一样查找主机名（返回[`AddrInfo`](http://hackage.haskell.org/packages/archive/network/latest/doc/html/Network-Socket.html#t:AddrInfo)`]`)

    ```
    getAddrInfo :: Maybe AddrInfo -> Maybe HostName -> Maybe ServiceName -> IO [AddrInfo]
    ```

    +   例如：获取与 web 服务器通信的`SockAddr`：

    ```
    webServerAddr :: String -> IO SockAddr webServerAddr name = do addrs <- getAddrInfo Nothing (Just name) (Just "www") return $ addrAddress $ head $ addrs
    ```

## 例如：netcat

```
netcat :: String -> String -> IO () netcat host port = do -- Extract address from first AddrInfo in list AddrInfo{ addrAddress = addr, addrFamily = family }:_ <- getAddrInfo Nothing (Just host) (Just port) -- Create a TCP socket connected to server s <- socket family Stream 0 connect s addr -- Convert socket to handle h <- socketToHandle s ReadWriteMode hSetBuffering h NoBuffering -- THIS IS IMPORTANT -- Punt on complex locale stuff hSetBinaryMode stdout True -- Copy data back and forth taking advantage of laziness done <- newEmptyMVar forkIO $ (hGetContents h >>= putStr) `finally` putMVar done () getContents >>= hPutStr h takeMVar done
```
