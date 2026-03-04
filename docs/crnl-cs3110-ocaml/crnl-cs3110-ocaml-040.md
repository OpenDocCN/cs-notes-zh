# 040：为宝可梦设计代数数据类型 🐉

在本节课中，我们将学习如何使用OCaml的代数数据类型来建模一个简单的宝可梦战斗系统。我们将定义宝可梦的类型、攻击效果，并编写函数来计算伤害倍率。

## 概述

代数数据类型是OCaml中一种强大的数据建模工具。为了展示其应用，我们以宝可梦为例进行说明。宝可梦之间会进行战斗，并且每个宝可梦都有属性，例如火属性、水属性、虫属性等。为简化模型，我们假设每个宝可梦只拥有一种属性。当宝可梦相互攻击时，属性相克关系会决定攻击是“效果绝佳”、“效果一般”还是“效果不理想”。

![](img/84f73b9121db162c1428b1849eb7e421_1.png)

## 定义数据类型

首先，我们需要为宝可梦的属性定义一个类型。在OCaml中，`type`是保留关键字，因此我们将其命名为`ptype`。

```ocaml
type ptype = TNormal | TFire | TWater
```

接下来，我们定义攻击效果的类型。

```ocaml
type effectiveness = ENormal | ENotVery | ESuper
```

这里需要注意命名冲突。如果我们定义了两个都包含`Normal`构造子的类型，后定义的会“遮蔽”先定义的。一种惯用的解决方法是给构造子名称添加前缀以作区分，例如为`ptype`的构造子添加`T`，为`effectiveness`的构造子添加`E`。下周学习模块时，我们会看到更好的处理方式。

## 计算伤害倍率

现在，我们编写一个函数，根据攻击效果返回对应的伤害倍率。在OCaml中，将一种类型转换为另一种类型的函数通常命名为`xxx_of_yyy`的形式。

以下是计算倍率的函数：

```ocaml
let multiplier_of_effectiveness = function
  | ENormal -> 1.0
  | ENotVery -> 0.5
  | ESuper -> 2.0
```

此函数使用`function`关键字进行模式匹配，它接收一个`effectiveness`类型的参数并返回一个浮点数。

## 编码属性相克表

上一节我们定义了数据类型和伤害计算函数，本节我们将根据游戏规则编码属性相克表。这个函数接收攻击方和防御方的属性，并返回攻击效果。

```ocaml
let effectiveness_of_attack (attacker, defender) =
  match (attacker, defender) with
  | (TFire, TWater) | (TWater, TFire) -> ESuper
  | (TFire, TFire) | (TWater, TWater) -> ENotVery
  | _ -> ENormal
```

这个函数接收一个属性对（元组）作为参数。我们也可以将其写成接收两个独立参数的形式，这在功能上是等价的，选择哪种形式取决于你在代码其他部分的调用便利性。

```ocaml
let effectiveness_of_attack2 attacker defender =
  match (attacker, defender) with
  | (TFire, TWater) | (TWater, TFire) -> ESuper
  | (TFire, TFire) | (TWater, TWater) -> ENotVery
  | _ -> ENormal
```

## 创建宝可梦记录类型

最后，我们引入记录类型来完整地表示一只宝可梦。一个宝可梦记录可以包含名字、属性和生命值等信息。

```ocaml
type pokemon = { name : string; ptype : ptype; hp : int }
```

现在，我们可以用这个类型来创建具体的宝可梦实例：

```ocaml
let charmander = { name = "Charmander"; ptype = TFire; hp = 39 }
```

## 总结

![](img/84f73b9121db162c1428b1849eb7e421_3.png)

本节课我们一起学习了如何使用OCaml的代数数据类型和记录类型来建模一个领域。我们定义了宝可梦属性(`ptype`)和攻击效果(`effectiveness`)的类型，编写了计算伤害倍率的函数，并实现了属性相克逻辑。最后，我们创建了一个记录类型来完整描述一只宝可梦。通过这些步骤，你将代数数据类型的核心概念应用到了一个具体、有趣的例子中。