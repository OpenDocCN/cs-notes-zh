# 随机数生成

在游戏中，我们经常需要生成随机数。我们首先在全局变量中设置一个随机数生成器：

```
  val random = java.util.Random()

```

然后，要在范围 0 到 k-1 内生成一个随机整数，我们调用

```
  val random_number = random.nextInt(k)

```

你也可以使用随机数生成器在范围\(0.0 \leq x < 1.0\)内生成一个随机的双精度数。

```
  val x = random.nextDouble()

```
