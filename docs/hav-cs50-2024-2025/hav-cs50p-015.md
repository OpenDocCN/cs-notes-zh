# 015：random模块 🎲

![](img/d599875aee7f49738a513fca7cd6b5ba_0.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_2.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_3.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_4.png)

在本节课中，我们将要学习Python的`random`模块。这个模块可以为你的程序引入随机性或机会元素。我们将通过一个模拟发牌的程序来了解如何使用它。

![](img/d599875aee7f49738a513fca7cd6b5ba_5.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_6.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_7.png)

## 导入模块

![](img/d599875aee7f49738a513fca7cd6b5ba_9.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_10.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_11.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_12.png)

首先，要使用`random`模块，我们需要在程序顶部导入它。

![](img/d599875aee7f49738a513fca7cd6b5ba_14.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_15.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_16.png)

```python
import random
```

## 随机选择单个元素

![](img/d599875aee7f49738a513fca7cd6b5ba_18.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_19.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_20.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_21.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_22.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_23.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_24.png)

`random`模块内置了多个函数。其中一个我们已经见过的是`choice`函数。这个函数接收一个列表作为输入，并随机返回该列表中的一个元素。

![](img/d599875aee7f49738a513fca7cd6b5ba_25.png)

以下是使用`choice`函数的代码示例：

```python
card = random.choice(cards)
print(card)
```

![](img/d599875aee7f49738a513fca7cd6b5ba_27.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_28.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_29.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_30.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_31.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_32.png)

运行程序，每次可能会得到不同的结果，例如“Queen”、“Jack”或“King”。这证明了选择的随机性。

![](img/d599875aee7f49738a513fca7cd6b5ba_33.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_34.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_35.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_36.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_37.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_38.png)

## 随机选择多个元素（有放回抽样）

![](img/d599875aee7f49738a513fca7cd6b5ba_40.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_41.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_42.png)

除了选择单个元素，`random`模块还提供了`choices`函数，允许你从列表中随机选择多个元素。这个函数采用“有放回抽样”，意味着每次选择后，被选中的元素会放回原列表，因此有可能被再次选中。

`choices`函数需要两个参数：要选择的列表和要选择的元素数量`k`。

![](img/d599875aee7f49738a513fca7cd6b5ba_44.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_45.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_46.png)

以下是使用`choices`函数选择两张牌的代码示例：

![](img/d599875aee7f49738a513fca7cd6b5ba_47.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_48.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_49.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_50.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_51.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_52.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_53.png)

```python
selected_cards = random.choices(cards, k=2)
print(selected_cards)
```

![](img/d599875aee7f49738a513fca7cd6b5ba_55.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_56.png)

运行程序，你可能会得到类似`['Queen', 'King']`或`['Queen', 'Queen']`的结果。出现重复牌的情况是因为采用了有放回抽样。

## 随机选择多个元素（无放回抽样）

![](img/d599875aee7f49738a513fca7cd6b5ba_58.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_59.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_60.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_61.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_62.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_63.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_64.png)

如果你希望进行“无放回抽样”，即选中的元素不会再次出现，可以使用`sample`函数。这类似于从一副牌中抽出一张后，剩下的牌中再抽一张。

![](img/d599875aee7f49738a513fca7cd6b5ba_65.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_66.png)

`sample`函数的参数与`choices`相同。

![](img/d599875aee7f49738a513fca7cd6b5ba_68.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_69.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_70.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_71.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_72.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_73.png)

以下是使用`sample`函数选择两张牌的代码示例：

```python
selected_cards = random.sample(cards, k=2)
print(selected_cards)
```

![](img/d599875aee7f49738a513fca7cd6b5ba_75.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_76.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_77.png)

运行程序，由于我们只有三张不同的牌（Jack, Queen, King），结果将总是两张不同的牌，例如`['Queen', 'King']`。

![](img/d599875aee7f49738a513fca7cd6b5ba_78.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_79.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_80.png)

## 设置权重

有时，你可能希望某些结果出现的概率更高。`choices`函数支持一个可选的`weights`参数，用于为列表中的每个元素设置权重。

![](img/d599875aee7f49738a513fca7cd6b5ba_82.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_83.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_84.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_85.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_86.png)

权重是一个数字列表，长度必须与选择列表相同。数字越大，对应元素被选中的概率就越高。

![](img/d599875aee7f49738a513fca7cd6b5ba_88.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_89.png)

以下是一个设置权重的示例，使“Jack”被选中的概率为75%，“Queen”为20%，“King”为5%：

![](img/d599875aee7f49738a513fca7cd6b5ba_91.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_92.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_93.png)

```python
selected_cards = random.choices(cards, k=2, weights=[75, 20, 5])
print(selected_cards)
```

![](img/d599875aee7f49738a513fca7cd6b5ba_94.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_95.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_96.png)

运行程序多次，你会发现“Jack”出现的频率远高于其他牌。

![](img/d599875aee7f49738a513fca7cd6b5ba_98.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_99.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_100.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_101.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_102.png)

## 设置随机种子以方便调试

随机性虽然有趣，但在调试程序时可能会带来麻烦，因为每次运行结果都不同。为了解决这个问题，`random`模块提供了`seed`函数。

![](img/d599875aee7f49738a513fca7cd6b5ba_104.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_105.png)

“种子”是伪随机数生成器的输入。通过设置一个固定的种子，可以确保每次程序运行时产生的随机序列完全相同。这在调试时非常有用，因为你可以获得可预测的“随机”结果。

![](img/d599875aee7f49738a513fca7cd6b5ba_106.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_107.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_108.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_109.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_110.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_111.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_112.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_113.png)

以下是设置随机种子的代码示例：

![](img/d599875aee7f49738a513fca7cd6b5ba_114.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_116.png)

```python
random.seed(0)  # 将种子设置为0
selected_cards = random.choices(cards, k=2)
print(selected_cards)
```

![](img/d599875aee7f49738a513fca7cd6b5ba_118.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_119.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_120.png)

现在，无论你运行程序多少次，只要种子是0，输出的结果都会是一样的（例如`['King', 'King']`）。如果将种子改为1，则会得到另一个固定的随机序列（例如`['Jack', 'King']`）。

![](img/d599875aee7f49738a513fca7cd6b5ba_122.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_123.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_125.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_126.png)

## 总结

![](img/d599875aee7f49738a513fca7cd6b5ba_128.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_129.png)

![](img/d599875aee7f49738a513fca7cd6b5ba_130.png)

本节课中我们一起学习了Python的`random`模块。我们了解了如何导入模块，以及如何使用`choice`、`choices`和`sample`函数进行随机选择。我们还探讨了如何通过`weights`参数设置选择权重，以及如何使用`seed`函数设置随机种子来获得可重复的结果，以便于程序调试。现在，你可以将这些技巧应用到自己的程序中，为其增添随机性。