# SwiftUI iOS应用开发：CS193p 第5讲：协议、枚举与可选类型 🧩

在本节课中，我们将继续完善记忆卡片游戏，并深入学习Swift中的几个核心概念：协议、枚举和可选类型。我们将通过实践来理解如何让自定义类型遵循协议，如何使用枚举来定义离散值，以及如何利用可选类型安全地处理可能缺失的值。

## 课程概述

上一节我们介绍了视图模型和模型之间的数据流。本节中，我们将首先通过添加动画来引出对协议的需求，然后深入探讨枚举类型，并重点学习一个特殊的枚举——可选类型。最后，我们将运用这些知识来实现完整的游戏逻辑。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_1.png)

---

![](img/0d8de5d38475531ffb42f5d3d8445d0b_3.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_4.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_6.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_7.png)

## 状态对象与可观察对象的区别 🔍

在继续演示之前，我们先明确一下 `@StateObject` 和 `@ObservedObject` 的区别。理解它们的关键在于生命周期和作用域。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_9.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_10.png)

*   **生命周期**：`@StateObject` 的生命周期与声明它的视图紧密绑定。当视图出现在屏幕上时，该变量被创建；当视图从界面中移除时，它也随之销毁。如果将 `@StateObject` 声明在 App 层级，则其生命周期与整个应用相同。`@ObservedObject` 的生命周期则由传递给它的一方决定。
*   **作用域**：在视图中使用 `@StateObject` 声明的变量，只能在该视图及其子视图体中使用，无法在兄弟视图中共享。而 `@ObservedObject` 是外部传入的，可以被传递给多个兄弟视图。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_12.png)

关于预览，我们通常直接创建实例（例如 `MemoryGameViewModel()`），这是因为预览代码会频繁执行，每次都会生成新的实例，这有助于重置状态。

---

![](img/0d8de5d38475531ffb42f5d3d8445d0b_14.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_16.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_18.png)

## 为卡片添加动画 🎬

![](img/0d8de5d38475531ffb42f5d3d8445d0b_20.png)

虽然完整的动画教学将在后续课程进行，但今天我们将添加一个简单的动画，这能帮助我们理解协议和泛型约束。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_22.png)

我们的目标是让卡片在洗牌时能够平滑移动，而不是生硬地切换。我们在显示卡片的 `LazyVGrid` 上添加 `.animation` 视图修饰符。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_23.png)

```swift
// 在 CardView 的容器上添加动画
.animation(.default, value: viewModel.cards)
```

`.animation` 修饰符接受一个 `value` 参数。当这个值发生变化时，视图内部所有可动画化的变化都会以动画形式呈现。这里我们传入 `viewModel.cards`，意味着当卡牌数组发生变化时（如洗牌），会触发动画。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_25.png)

然而，添加这行代码后出现了错误：**“Referencing operator function '==' on 'Array' requires that 'MemoryGame<String>.Card' conforms to 'Equatable'”**。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_27.png)

这是因为 Swift 的动画系统需要比较动画前后的状态。它会在值变化时保存一份快照，变化后再比较新旧值是否相等（`==`），如果不相等则执行动画。数组的 `==` 操作要求其元素类型必须遵循 `Equatable` 协议。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_29.png)

---

![](img/0d8de5d38475531ffb42f5d3d8445d0b_31.png)

## 遵循 Equatable 协议 ⚖️

![](img/0d8de5d38475531ffb42f5d3d8445d0b_33.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_35.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_37.png)

为了解决上述错误，我们需要让 `Card` 结构体遵循 `Equatable` 协议。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_39.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_40.png)

1.  在模型文件中，为 `Card` 结构体声明遵循 `Equatable`。
    ```swift
    struct Card: Equatable {
        // ... 现有属性
    }
    ```
2.  Xcode 会提示我们实现协议要求。对于 `Equatable`，通常需要实现一个静态的 `==` 函数。我们可以使用 Fix-it 功能自动生成模板。
3.  生成的函数如下：
    ```swift
    static func == (lhs: Card, rhs: Card) -> Bool {
        return lhs.isFaceUp == rhs.isFaceUp &&
               lhs.isMatched == rhs.isMatched &&
               lhs.content == rhs.content
    }
    ```
    这个函数比较两张卡片的三个属性是否全部相等。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_42.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_44.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_46.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_47.png)

但这里又出现了新的错误：**“Referencing operator function '==' on 'Equatable' requires that 'CardContent' conforms to 'Equatable'”**。这是因为我们尝试比较 `lhs.content == rhs.content`，而 `content` 的类型 `CardContent` 是一个泛型占位符，我们不知道它是否能比较相等。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_49.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_51.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_53.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_55.png)

我们需要为泛型 `CardContent` 添加约束，要求它也必须遵循 `Equatable`。

```swift
struct Card<CardContent> where CardContent: Equatable {
    // ... 现有属性
}
// 或者使用更简洁的语法
struct Card<CardContent: Equatable> {
    // ... 现有属性
}
```

![](img/0d8de5d38475531ffb42f5d3d8445d0b_57.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_58.png)

这样我们就告诉编译器：`Card` 可以接受任何类型作为 `CardContent`，但该类型必须能够判断相等。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_60.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_62.png)

**Swift 的便利功能**：当你的 `==` 实现仅仅是逐一比较所有存储属性时（就像我们上面做的那样），Swift 可以自动合成（synthesize）这个实现。因此，我们可以直接删除整个 `==` 函数，Swift 会自动为我们生成正确的实现。现在错误消失了。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_64.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_66.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_68.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_69.png)

---

![](img/0d8de5d38475531ffb42f5d3d8445d0b_71.png)

## 修复动画与 Identifiable 协议 🆔

添加动画后，洗牌时卡片只是淡入淡出，而不是我们期望的移动效果。问题出在创建视图的 `ForEach` 上。

之前我们使用索引来遍历：
```swift
ForEach(viewModel.cards.indices) { index in
    CardView(card: viewModel.cards[index])
}
```
这种方式将视图与数组的**索引位置**绑定。洗牌时，卡片在数组中的位置变了，但 `ForEach` 仍然为索引 0 的位置创建视图，只是该位置上的卡片内容变了，所以表现为淡入淡出。

我们需要将视图与**卡片本身**绑定，这样当卡片在数组中移动时，对应的视图也会移动。

```swift
ForEach(viewModel.cards) { card in
    CardView(card: card)
}
```
我们将遍历对象从 `indices` 改为 `cards` 数组本身，并直接将 `card` 传递给 `CardView`。

但这导致了新的错误：**“Generic struct 'ForEach' requires that 'MemoryGame<String>.Card' conforms to 'Hashable'”**。这与 `ForEach` 的 `id` 参数有关。

`ForEach` 需要唯一标识每个数据项，以便正确管理视图的生命周期。之前使用 `\.self` 作为标识，意味着使用数据项本身作为 ID。这对于像 `Int` 这样本身可哈希且唯一的索引是有效的。但对于我们的 `Card`，其属性（如 `isFaceUp`）会变化，导致“标识”也变化，这不合适。

我们需要一个唯一且不变的标识符来代表每张卡片。这就是 `Identifiable` 协议的作用。

1.  让 `Card` 遵循 `Identifiable` 协议。
    ```swift
    struct Card: Identifiable {
        // ... 现有属性
        let id: String
    }
    ```
2.  `Identifiable` 协议要求有一个 `id` 属性，其类型只要遵循 `Hashable` 即可。我们通常使用 `String` 或 `Int`。这里我们添加一个 `let id: String`。
3.  在初始化卡片时，为 `id` 赋值。我们可以利用字符串插值来生成 ID，例如 `"\(pairIndex+1)a"` 和 `"\(pairIndex+1)b"`。

现在，`ForEach` 可以通过 `card.id` 来唯一识别每张卡片。再次运行洗牌，可以看到卡片现在能够正确移动了！

---

## 自定义调试输出 🐛

在开发过程中，我们经常在控制台打印对象以进行调试。Swift 为所有类型提供了默认的字符串表示，但有时过于冗长。我们可以让自定义类型遵循 `CustomDebugStringConvertible` 协议来提供更清晰的调试描述。

```swift
extension Card: CustomDebugStringConvertible {
    var debugDescription: String {
        return "\(id): \(content) \(isFaceUp ? "up" : "down")\(isMatched ? " matched" : "")"
    }
}
```
实现 `debugDescription` 计算属性，返回我们想要的格式字符串。之后在控制台打印 `Card` 对象时，就会使用这个简洁的格式。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_73.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_75.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_76.png)

---

## 实现卡片点击与游戏逻辑 🎮

![](img/0d8de5d38475531ffb42f5d3d8445d0b_78.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_80.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_81.png)

现在让我们实现卡片的点击翻转和完整的游戏匹配逻辑。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_82.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_84.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_85.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_86.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_87.png)

### 1. 添加点击手势
在 `CardView` 上添加 `.onTapGesture` 修饰符，调用视图模型的 `choose` 方法（这是一个“意图”）。
```swift
.onTapGesture {
    viewModel.choose(card)
}
```

![](img/0d8de5d38475531ffb42f5d3d8445d0b_89.png)

### 2. 处理点击意图
在模型的 `choose` 方法中，我们首先需要找到被点击卡片在数组中的索引。这里我们遇到了 **值类型** 的一个重要特性：**传递即拷贝**。我们不能直接修改传入的 `card` 参数，因为它只是原始卡片的一个副本。我们必须修改模型内部 `cards` 数组中的原始卡片。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_91.png)

我们创建一个工具函数来根据卡片的 `id` 查找索引：
```swift
private func index(of card: Card) -> Int? {
    for index in cards.indices {
        if cards[index].id == card.id {
            return index
        }
    }
    return nil // 如果没找到，返回 nil
}
```
注意，这个函数返回 `Int?`（可选整数），因为可能找不到对应的卡片。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_93.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_95.png)

### 3. 使用可选类型处理未找到的情况
在 `choose` 方法中，我们使用 `if let` 安全地解包这个可选索引：
```swift
if let chosenIndex = index(of: card) {
    // 只有找到索引时才执行游戏逻辑
    cards[chosenIndex].isFaceUp.toggle()
}
```
**可选类型（Optional）** 是 Swift 中用于表示值可能缺失的核心类型。它是一个枚举：`.none` 表示没有值（`nil`），`.some(Wrapped)` 表示包含某个类型的值。`Int?` 是 `Optional<Int>` 的语法糖。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_97.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_98.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_100.png)

### 4. 优化查找方法
我们可以利用数组的高阶函数 `firstIndex(where:)` 来更简洁地实现查找：
```swift
private func index(of card: Card) -> Int? {
    return cards.firstIndex(where: { $0.id == card.id })
}
```
`firstIndex(where:)` 接受一个返回布尔值的闭包，返回第一个使闭包为真的元素的索引（可选类型）。这同样体现了函数式编程的思想。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_102.png)

### 5. 实现完整游戏逻辑
游戏的核心规则是：
*   每次只能翻开一张或两张卡片。
*   如果翻开一张，等待下一张。
*   如果翻开两张，检查是否匹配。若匹配，则标记为已匹配；若不匹配，则在下一张卡片被点击时将它们翻回。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_104.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_106.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_107.png)

我们使用一个计算属性 `indexOfTheOneAndOnlyFaceUpCard` 来跟踪当前唯一面朝上的卡片索引（如果没有或有两张，则为 `nil`）。这个属性既是获取器也是设置器：
*   **获取器（get）**：遍历 `cards`，找出所有面朝上的卡片索引。如果恰好只有一个，则返回它；否则返回 `nil`。
*   **设置器（set）**：当设置这个属性时（例如，将其设为用户刚点击的卡片索引），我们将数组中**所有**卡片的 `isFaceUp` 设为 `false`，然后将指定索引的卡片设为 `true`。这保证了任何时候最多只有一张卡片是面朝上的（除非正在匹配过程中）。

在 `choose` 方法中，逻辑如下：
```swift
if let chosenIndex = cards.firstIndex(where: { $0.id == card.id }) {
    // 只处理未匹配且面朝下的卡片
    if !cards[chosenIndex].isFaceUp && !cards[chosenIndex].isMatched {
        // 如果已有一张面朝上的卡片，尝试匹配
        if let potentialMatchIndex = indexOfTheOneAndOnlyFaceUpCard {
            if cards[chosenIndex].content == cards[potentialMatchIndex].content {
                // 匹配成功
                cards[chosenIndex].isMatched = true
                cards[potentialMatchIndex].isMatched = true
            }
            // 无论是否匹配，现在有两张面朝上的卡片，所以将唯一面朝上索引设为 nil
            // 注意：此时卡片还未翻面，下面会统一处理
        } else {
            // 如果没有面朝上的卡片，则将所有其他卡片翻到背面，并将当前卡片设为唯一面朝上的
            indexOfTheOneAndOnlyFaceUpCard = chosenIndex
        }
        // 翻转被点击的卡片
        cards[chosenIndex].isFaceUp = true
    }
}
```

![](img/0d8de5d38475531ffb42f5d3d8445d0b_109.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_110.png)

### 6. 优化代码与函数式编程
我们可以利用函数式编程进一步简化计算属性的实现：

![](img/0d8de5d38475531ffb42f5d3d8445d0b_112.png)

**获取器** 可以使用 `filter` 和自定义的数组扩展方法 `only`：
```swift
var indexOfTheOneAndOnlyFaceUpCard: Int? {
    get {
        let faceUpCardIndices = cards.indices.filter { index in cards[index].isFaceUp }
        return faceUpCardIndices.only
    }
    set {
        cards.indices.forEach { index in
            cards[index].isFaceUp = (index == newValue)
        }
    }
}
```
我们为 `Array` 添加了一个扩展，提供 `only` 属性，当数组只有一个元素时返回该元素，否则返回 `nil`：
```swift
extension Array {
    var only: Element? {
        count == 1 ? first : nil
    }
}
```
**设置器** 使用 `forEach` 遍历所有索引，简洁地设置每张卡片的朝向。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_114.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_115.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_117.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_119.png)

---

![](img/0d8de5d38475531ffb42f5d3d8445d0b_121.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_122.png)

## 枚举（Enum）深度解析 📚

![](img/0d8de5d38475531ffb42f5d3d8445d0b_124.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_126.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_128.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_130.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_132.png)

枚举用于定义一组相关的离散值。与结构体和类不同，枚举没有存储属性。Swift 枚举的强大之处在于其**关联值**——可以为每个枚举案例附加额外的数据。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_133.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_135.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_137.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_139.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_140.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_142.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_144.png)

```swift
enum FastFoodMenuItem {
    case hamburger(numberOfPatties: Int)
    case fries(size: FryOrderSize)
    case drink(String, ounces: Int) // 未命名的 String 关联值
    case cookie
}
```
*   **赋值**：`let menuItem: FastFoodMenuItem = .hamburger(numberOfPatties: 2)`
*   **切换判断**：使用 `switch` 语句处理枚举值，并可以提取关联值。
    ```swift
    switch menuItem {
    case .hamburger(let pattyCount): print("Burger with \(pattyCount) patties!")
    case .fries(let size): print("\(size) fries!")
    case .drink(let brand, let ounces): print("\(ounces)oz \(brand)")
    case .cookie: print("Cookie")
    }
    ```
*   **必须穷尽**：`switch` 必须处理所有枚举案例，或用 `default` 涵盖剩余情况。
*   **方法和计算属性**：枚举也可以有方法和计算属性（但不能有存储属性）。
*   **遍历所有案例**：让枚举遵循 `CaseIterable` 协议，即可通过 `allCases` 进行遍历。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_146.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_148.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_150.png)

---

![](img/0d8de5d38475531ffb42f5d3d8445d0b_152.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_153.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_155.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_157.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_158.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_159.png)

## 可选类型（Optional）详解 🎁

![](img/0d8de5d38475531ffb42f5d3d8445d0b_161.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_163.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_165.png)

可选类型本质上就是一个枚举：
```swift
enum Optional<T> {
    case none
    case some(T)
}
```
它用于表示“可能有值，也可能是 `nil`（无值）”的场景。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_166.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_168.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_170.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_172.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_173.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_175.png)

**语法糖**：
*   **声明**：`var hello: String?` 等价于 `var hello: Optional<String>`
*   **赋值**：`hello = nil` 对应 `.none`；`hello = "world"` 对应 `.some("world")`
*   **强制解包**：`print(hello!)` – 如果 `hello` 为 `nil`，程序会崩溃。应谨慎使用。
*   **安全解包**：`if let safeHello = hello { ... }` – 这是安全处理可选值的标准方式。
*   **空合运算符**：`let y = x ?? "foo"` – 如果 `x` 为 `nil`，则使用默认值 `"foo"`。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_177.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_179.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_180.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_182.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_183.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_184.png)

在我们的游戏代码中，`index(of:)` 函数返回 `Int?`，以及在 `choose` 方法中使用 `if let` 来安全处理可能找不到卡片的情况，都是可选类型的典型应用。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_186.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_188.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_190.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_192.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_193.png)

---

![](img/0d8de5d38475531ffb42f5d3d8445d0b_195.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_197.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_199.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_200.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_202.png)

## 课程总结

![](img/0d8de5d38475531ffb42f5d3d8445d0b_204.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_205.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_207.png)

本节课我们完成了以下内容：

![](img/0d8de5d38475531ffb42f5d3d8445d0b_209.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_210.png)

![](img/0d8de5d38475531ffb42f5d3d8445d0b_211.png)

1.  **明确了 `@StateObject` 与 `@ObservedObject`** 在生命周期和作用域上的关键区别。
2.  **添加了动画**，并由此引出类型需要遵循 `Equatable` 协议才能被动画系统比较。
3.  **学习了协议遵循**：通过让 `Card` 遵循 `Equatable` 和 `Identifiable` 协议，解决了动画和 `ForEach` 的标识问题。
4.  **深入理解了枚举**，特别是其关联值的特性。
5.  **掌握了可选类型**，这是 Swift 安全处理缺失值的核心机制，并在游戏逻辑中用它来安全地查找卡片索引。
6.  **实现了完整的游戏逻辑**，包括卡片匹配、状态管理，并运用函数式编程思想优化了代码。

![](img/0d8de5d38475531ffb42f5d3d8445d0b_213.png)

通过本课的学习，你不仅完善了记忆卡片游戏，更重要的是掌握了 Swift 中协议、枚举和可选类型这几个构建健壮、安全应用程序的基石。在接下来的作业和项目中，你会反复运用这些概念。