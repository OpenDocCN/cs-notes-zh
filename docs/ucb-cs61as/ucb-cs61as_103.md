# 更多给 A 伙伴的练习

`adv.scm`包括`thief`类的定义，它是`person`的子类。`thief`是一个试图从其他人那里偷食物的角色。当然，伯克利不能容忍这种行为太久。你的任务是定义一个`police`类；`police`对象抓住`thieves`并直接送他们进`jail`。为此，你需要了解`thiefs`的工作原理。

由于`thief`是`person`的一种，每当另一个`person`进入`thief`所在的地方时，`thief`会从地方收到一个`notice`消息。当`thief`注意到一个新的人时，根据他内部`behavior`变量的状态，他会做两件事中的一件。如果这个变量设置为`steal`，小偷会四处查看是否有食物。如果有食物，小偷会从当前持有者那里拿走食物，并将他的行为设置为`run`。当小偷的行为是`run`时，他会在`notice`到有人进入他当前位置时随机移动到一个新的地方。`run`行为使得抓住小偷变得困难。

注意，一个`thief`对象将许多消息委托给它的`person`对象。

## 问题 A6：第一部分

为了帮助警察开展工作，你需要创建一个名为`jail`的地方（即，`jail`是`place`的一个实例）。Jail 没有出口。此外，你需要为人和小偷创建一个名为`go-directly-to`的方法。`go-directly-to`不要求`new-place`与`current-place`相邻。因此，通过调用`(ask thief 'go-directly-to jail)`，警察可以将小偷送进监狱，无论小偷当前位于何处，假设变量`thief`绑定到被逮捕的小偷。

## 问题 A6：第二部分

小偷有时会尝试朝随机选择的方向离开他们所在的地方。事实证明，如果那个地方没有出口，比如`jail`，这样做是行不通的。修改`thief`类，使得小偷不会尝试离开没有出口的地方。

## 结合工作

在继续之前，请让你的伙伴解释问题 B6 及其解决方案。同时，向你的伙伴解释问题 A6 及其解决方案。

## 问题 A7：第一部分

现在我们要创造餐厅对象。人们将通过在那里购买食物与餐厅互动。首先，我们必须让人们能够购买东西。给`person`对象一个`money`属性，这是一个数字，表示他们有��少美元。请注意，`money`不是一个对象。我们将其实现为一个数字，因为与椅子和锅贴等对象不同，一个人需要能够花一些钱而不是全部。原则上，我们可以有像`quarter`和`dollar-bill`这样的对象，但这会使找零过程变得复杂，没有充分的理由。

为了简化生活，我们让每个`person`从`$100`开始。（其实我们应该让人们一无所有，然后再发明银行、工作等等，但我们不会这样做。）为人们创建两个方法，`get-money`和`pay-money`，每个方法都接受一个数字作为参数，并适当更新人的`money`值。`Pay-money`必须根据人是否有足够的钱返回`true`或`false`。

```
> (ask brian 'money)
100
> (ask brian 'get-money 20) ;increases money
> (ask brian 'money)
120
> (ask brian 'pay-money 30) ;decreases money. Returns #t if has enough money  
#t  
> (ask brian 'money)
90 
```

## 问题 A7：第 2 部分

冒险游戏的另一个问题是，诺亚家只有一个百吉饼。一旦有人拿走了那个百吉饼，他们就破产了。其他餐厅也是一样。

为了解决这个问题，我们将发明一种新类型的地方，称为`restaurant`。（也就是说，`restaurant`是`place`的子类。）每个`restaurant`只提供一种食物。（当然，这是一个简化，当然，我们可以看到如何扩展项目以允许食物种类的列表。）当实例化一个`restaurant`时，除了所有地方都有的参数外，它还应该有两个额外的参数：这家餐厅销售的食品对象类别，以及这种类型的一个物品的价格：

```
 > (define-class (pasta) (parent (food ...)) ...)

   > (define somerestaurant (instantiate restaurant 'somerestaurant pasta 7)) 
```

注意，餐厅的参数是一个*class*，而不是一个特定的百吉饼（实例）。这里是意大利面食品类的一个例子。你的伙伴应该在问题 B6 的一部分中定义了一些食品类的示例。

```
> (define pesto-pasta (instantiate pasta))
> (ask pesto-pasta 'calories)
150 
```

餐厅应该有两个方法。`menu`方法返回一个包含餐厅销售的食品名称和价格的列表。`sell`方法接受两个参数，想要购买东西的`person`和人想要的食品的`name`。`sell`方法必须首先检查餐厅是否实际销售正确类型的食品。如果是这样，它应该要求买家以适当的金额`pay-money`。如果成功，该方法应该**实例化食品类**并返回**新的食品对象**。如果人无法购买食物，该方法应返回`#f`。

以下是一些例子：

```
> (ask somerestaurant 'menu)
(pasta 7)
> (ask somerestaurant 'sell someperson 'pasta) ;note that pasta is the name 
```

## 问题 A8

现在我们需要一个人的`buy`方法。它应该以我们想要购买的食品的**name**作为参数：

```
> (ask Brian 'buy 'bagel) 
```

该方法必须向餐厅发送一个`sell`消息。如果成功（也就是说，从`sell`方法返回的值是一个**对象**而不是`#f`），新食物应该被添加到人的财产中。如果人无法购买，返回一个**错误**。
