# SwiftUI iOS应用开发：07：视图组件化、形状与视图修饰器

![](img/f36af5341ca7ca8012163fa542bfc823_1.png)

![](img/f36af5341ca7ca8012163fa542bfc823_3.png)

![](img/f36af5341ca7ca8012163fa542bfc823_4.png)

![](img/f36af5341ca7ca8012163fa542bfc823_5.png)

在本节课中，我们将学习如何将视图组件化到独立的文件中，管理代码中的常量，并深入探讨SwiftUI中形状和视图修饰器的工作原理。我们将通过构建一个“卡片化”视图修饰器和一个自定义的饼图形状来实践这些概念。

![](img/f36af5341ca7ca8012163fa542bfc823_7.png)

![](img/f36af5341ca7ca8012163fa542bfc823_9.png)

![](img/f36af5341ca7ca8012163fa542bfc823_10.png)

## 演示环节：分离CardView

![](img/f36af5341ca7ca8012163fa542bfc823_12.png)

上一节我们介绍了如何构建复杂的视图。本节中，我们来看看如何将视图组件化，以提高代码的可维护性。

![](img/f36af5341ca7ca8012163fa542bfc823_14.png)

![](img/f36af5341ca7ca8012163fa542bfc823_15.png)

![](img/f36af5341ca7ca8012163fa542bfc823_17.png)

目前，`CardView` 直接定义在 `EmojiMemoryGameView` 中。随着其功能变得复杂，最好将其分离到独立的文件中。

![](img/f36af5341ca7ca8012163fa542bfc823_19.png)

![](img/f36af5341ca7ca8012163fa542bfc823_21.png)

![](img/f36af5341ca7ca8012163fa542bfc823_23.png)

![](img/f36af5341ca7ca8012163fa542bfc823_25.png)

以下是操作步骤：
1.  在Xcode中，选择 **File > New > File...**。
2.  在模板选择器中，选择 **SwiftUI View**。
3.  将文件命名为 `CardView.swift`，并确保将其保存在项目的正确目录中。
4.  回到 `EmojiMemoryGameView`，将 `CardView` 的代码剪切并粘贴到新创建的文件中。

分离后，`CardView` 的使用不受影响，因为它是一个独立的 `struct`。

现在，我们需要为 `CardView` 创建预览。由于 `CardView` 需要一个 `Card` 参数来初始化，我们不能直接使用默认的预览。

![](img/f36af5341ca7ca8012163fa542bfc823_27.png)

以下是创建预览的方法：
```swift
struct CardView_Previews: PreviewProvider {
    static var previews: some View {
        let card = MemoryGame<String>.Card(content: "X", id: "test1")
        CardView(card: card)
            .padding()
            .foregroundColor(.green)
    }
}
```
在预览中添加填充和颜色有助于在开发时快速检查视图的外观。

此外，我们可以使用类型别名来简化冗长的类型名称。例如，在 `EmojiMemoryGameViewModel` 中：
```swift
typealias Card = MemoryGame<String>.Card
```
然后就可以在代码中使用 `Card` 来代替 `MemoryGame<String>.Card`。请注意，类型别名的作用域是局部的。

## 管理常量

我们的代码中开始出现一些“魔法数字”（即未经解释的硬编码数值）。良好的实践是将它们定义为常量。

对于简单的常量，可以直接在视图中定义：
```swift
private let aspectRatio: CGFloat = 2/3
private let spacing: CGFloat = 4
```

对于拥有多个相关常量的视图（如 `CardView`），更好的做法是使用一个嵌套的 `struct` 来组织它们：
```swift
private struct Constants {
    static let cornerRadius: CGFloat = 12
    static let lineWidth: CGFloat = 2
    static let inset: CGFloat = 5

    struct FontSize {
        static let largest: CGFloat = 200
        static let smallest: CGFloat = 10
        static let scaleFactor = smallest / largest
    }
}
```
然后，在代码中通过 `Constants.cornerRadius` 等方式使用它们。这种方式不仅将常量组织在一起，还通过 `static` 属性确保了它们是真正的常量，并且可以包含计算属性甚至函数。

通常，将这些常量 `struct` 放在视图文件的底部，这样它们不会干扰对主体视图逻辑的阅读。

对于像 `.white`、`.black` 或 `.orange` 这样的颜色，如果它们是设计系统的一部分且可能调整，也可以定义为常量。但像 `.white` 这样的基础颜色通常直接使用。

![](img/f36af5341ca7ca8012163fa542bfc823_29.png)

## 理解与创建形状

![](img/f36af5341ca7ca8012163fa542bfc823_31.png)

![](img/f36af5341ca7ca8012163fa542bfc823_33.png)

上一节我们整理了代码结构。本节中，我们来看看SwiftUI中形状的工作原理以及如何创建自定义形状。

![](img/f36af5341ca7ca8012163fa542bfc823_35.png)

![](img/f36af5341ca7ca8012163fa542bfc823_36.png)

`Shape` 是一个继承自 `View` 的协议。这意味着所有形状同时也是视图。你已经见过 `Circle`、`RoundedRectangle` 等内建形状。

形状默认使用当前前景色填充自身。我们也可以使用 `.stroke()` 或 `.fill()` 修饰器来描边或使用特定样式填充。这些修饰器是专门用于 `Shape` 的，它们将形状转换为视图。

`.fill()` 修饰器实际上是一个泛型函数，它接受一个符合 `ShapeStyle` 协议的类型，例如 `Color`、`LinearGradient` 或 `ImagePaint`。

### 创建自定义形状：Pie（饼图）

为了演示，我们将创建一个饼图形状，它将用于后续的动画计时器。

要创建自定义形状，需要实现 `Shape` 协议。该协议要求实现一个 `path(in rect: CGRect) -> Path` 方法，用于在给定的矩形区域内定义形状的路径。

以下是 `Pie` 形状的核心实现思路：
1.  形状需要知道起始角和终止角。
2.  计算矩形的中心点和半径（取宽度和高度中较小值的一半）。
3.  使用 `Path` API 移动画笔到中心点，画一条线到起始点，沿圆弧画到终点，再画一条线回到中心点。

![](img/f36af5341ca7ca8012163fa542bfc823_38.png)

![](img/f36af5341ca7ca8012163fa542bfc823_39.png)

**注意**：iOS的坐标系原点在左上角，Y轴向下为正。这与常见的笛卡尔坐标系不同。此外，“顺时针”方向也是基于这个坐标系定义的。

以下是 `Pie` 形状的简化代码结构：
```swift
import SwiftUI
import CoreGraphics

struct Pie: Shape {
    var startAngle: Angle = .zero
    var endAngle: Angle
    var clockwise: Bool = true

    func path(in rect: CGRect) -> Path {
        let center = CGPoint(x: rect.midX, y: rect.midY)
        let radius = min(rect.width, rect.height) / 2
        let start = CGPoint(
            x: center.x + radius * cos(startAngle.radians),
            y: center.y + radius * sin(startAngle.radians)
        )

        var p = Path()
        p.move(to: center)
        p.addLine(to: start)
        p.addArc(center: center,
                 radius: radius,
                 startAngle: startAngle,
                 endAngle: endAngle,
                 clockwise: !clockwise) // 调整坐标系方向
        p.addLine(to: center)
        return p
    }
}
```
创建后，就可以像使用其他形状一样使用 `Pie`，例如 `Pie(startAngle: .degrees(-90), endAngle: .degrees(20)).fill(.blue)`。

## 理解与创建视图修饰器

![](img/f36af5341ca7ca8012163fa542bfc823_41.png)

![](img/f36af5341ca7ca8012163fa542bfc823_43.png)

视图修饰器是SwiftUI的基石。我们每天都在使用 `.font()`、`.padding()`、`.foregroundColor()` 等。本节中，我们来看看它们背后的机制以及如何创建自己的修饰器。

![](img/f36af5341ca7ca8012163fa542bfc823_45.png)

![](img/f36af5341ca7ca8012163fa542bfc823_46.png)

视图修饰器本质上是一个符合 `ViewModifier` 协议的结构体。该协议要求实现一个方法：
```swift
func body(content: Content) -> some View
```
当我们将 `.modifier(MyModifier())` 应用到一个视图上时，该视图会作为 `content` 参数传递给修饰器的 `body` 方法。修饰器则返回一个新的、经过修改的视图。

### 创建 Cardify 视图修饰器

我们将创建一个名为 `Cardify` 的修饰器，它可以将任何视图“卡片化”，即加上圆角矩形边框、背景等，就像我们记忆游戏中的卡片一样。

首先，创建 `Cardify.swift` 文件，并定义符合 `ViewModifier` 协议的结构体：
```swift
struct Cardify: ViewModifier {
    var isFaceUp: Bool

    func body(content: Content) -> some View {
        ZStack {
            let base = RoundedRectangle(cornerRadius: Constants.cornerRadius)
            if isFaceUp {
                base.fill(.white)
                base.strokeBorder(lineWidth: Constants.lineWidth)
                content // 这是被“卡片化”的原始内容
            } else {
                base.fill() // 使用前景色填充（例如橙色）
            }
        }
    }

    private struct Constants {
        static let cornerRadius: CGFloat = 12
        static let lineWidth: CGFloat = 2
    }
}
```
然后，为了能像 `.cardify(isFaceUp: true)` 这样优雅地使用，我们为 `View` 协议添加一个扩展：
```swift
extension View {
    func cardify(isFaceUp: Bool) -> some View {
        modifier(Cardify(isFaceUp: isFaceUp))
    }
}
```
现在，在 `CardView` 中，我们可以将包裹内容的ZStack替换为：
```swift
Pie(endAngle: .degrees(240))
    .opacity(Constants.pieOpacity)
    .overlay(Text(card.content))
    .cardify(isFaceUp: card.isFaceUp)
```
这样代码更简洁，并且将卡片样式逻辑封装在了独立的修饰器中。更重要的是，这为**动画**打下了基础。当 `isFaceUp` 状态改变时，我们可以在这个修饰器内部添加自定义的翻转动画（这将在下周的动画课程中实现）。

## 协议进阶：扩展与泛型

最后，我们简要探讨Swift类型系统中协议的强大功能，特别是通过扩展进行代码共享。

之前我们主要将协议视为一份要求清单。但实际上，可以通过 `extension` 为协议添加默认实现。这就是为什么 `Array`、`String`、`Dictionary` 这些数据表示完全不同的类型，都能拥有像 `.filter()`、`.map()` 这样的方法。这些方法被实现在它们共同遵循的协议（如 `Sequence`）的扩展中。

在SwiftUI中，`View` 协议本身只要求一个 `body` 属性。而 `.padding()`、`.foregroundColor()` 等数百个修饰器方法，都是通过 `extension View` 添加的。这实现了强大的功能共享，而无需传统的继承，避免了继承带来的数据表示约束。

### 泛型协议与 some、any

有些协议是泛型的，例如 `Identifiable`，它有一个关联类型 `ID`。这确保了每个可识别实体都有一个唯一标识符。

*   **`some`**：用于指代“某个遵循了特定协议的具体类型”，但类型对使用者是透明的（不透明的）。你已熟悉 `var body: some View`。它要求函数或计算属性每次都必须返回相同的具体类型。
*   **`any`**：用于存在类型包装，允许你将**不同类型**但遵循同一协议的对象放入集合（如数组）中。由于类型信息被“装箱”，使用时通常需要将其传递给接受 `some` 类型参数的函数来“拆箱”使用。在本课程中，你较少会直接使用 `any`。

理解 `some` 和泛型协议有助于阅读文档和高级API。例如，之前提到的 `.fill(_ style: some ShapeStyle)`，其参数可以是任何符合 `ShapeStyle` 的类型（`Color`、`Gradient`等）。

## 总结

本节课中我们一起学习了：
1.  **视图组件化**：将 `CardView` 分离到独立文件，并为其创建预览。
2.  **常量管理**：使用嵌套的 `struct` 组织和管理魔法数字，提高代码可读性和可维护性。
3.  **自定义形状**：理解了 `Shape` 协议，并创建了一个 `Pie` 饼图形状，学习了 `Path` API 和iOS坐标系。
4.  **视图修饰器**：深入了解了 `ViewModifier` 协议的工作原理，创建了 `Cardify` 修饰器来封装卡片样式，这为后续添加动画做好了准备。
5.  **协议进阶**：了解了如何通过扩展协议来共享代码实现，并简要介绍了泛型协议中的 `some` 和 `any` 关键字。

![](img/f36af5341ca7ca8012163fa542bfc823_48.png)

这些知识帮助你更好地组织SwiftUI代码，并理解其底层部分工作机制。下一周，我们将聚焦于**动画**，利用视图修饰器来实现卡片翻转等动态效果。