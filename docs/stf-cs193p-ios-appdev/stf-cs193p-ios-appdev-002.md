# 002：视图构建与交互 🧩

![](img/ef5ad7969d0279c35432f44999e44831_1.png)

![](img/ef5ad7969d0279c35432f44999e44831_3.png)

## 概述
在本节课中，我们将深入学习SwiftUI的核心概念，包括视图的构建、状态管理、用户交互以及如何组织代码以提高可读性。我们将通过构建一个记忆卡片游戏来实践这些概念。

![](img/ef5ad7969d0279c35432f44999e44831_5.png)

![](img/ef5ad7969d0279c35432f44999e44831_7.png)

---

## 回顾与补充

![](img/ef5ad7969d0279c35432f44999e44831_9.png)

上一讲我们介绍了SwiftUI的基础知识，本节我们将回顾并补充一些重要细节。

![](img/ef5ad7969d0279c35432f44999e44831_11.png)

![](img/ef5ad7969d0279c35432f44999e44831_13.png)

![](img/ef5ad7969d0279c35432f44999e44831_14.png)

### 检查器与选择模式
检查器允许您通过选择模式调整界面元素。即使您熟悉代码，检查器也很有用，例如用于微调颜色或内边距，而无需频繁编辑源代码。选择是双向的：在画布中选择一个元素会同时选中对应的代码行，反之亦然。

![](img/ef5ad7969d0279c35432f44999e44831_16.png)

![](img/ef5ad7969d0279c35432f44999e44831_18.png)

### 项目设置
在导航器的文件区域，除了应用文件外，还有一个项目设置项。这里可以配置构建目标、部署版本、签名和功能等。Xcode是一个强大的构建引擎，用于管理具有依赖关系的复杂项目。

### 视图行为
`ContentView: View` 表示 `ContentView` 结构体**行为像**一个视图。这与面向对象编程中的继承无关。我们将在后续课程中深入探讨“行为像”的含义。

### `some View` 详解
`some View` 是一种不透明返回类型，它让编译器推断视图的具体类型。例如，如果 `body` 只包含一个 `Text`，那么 `some View` 就是 `Text` 类型。如果包含一个 `VStack`，类型会变得复杂（如 `TupleView<(Text, Text)>`）。`some View` 简化了我们的工作，我们无需关心这些底层类型。

### GitHub集成
我们使用Git进行版本控制。在Xcode中，可以通过“Source Control”菜单提交更改。提交时需添加注释以描述更改内容。提交后，可以推送到远程仓库（如GitHub）以提交作业。反馈分支用于查看助教的评分意见。

---

## SwiftUI语法深入

### 尾随闭包语法
当函数的最后一个参数是闭包时，可以使用尾随闭包语法。例如，`ZStack` 的 `content` 参数是一个返回视图的闭包。我们可以省略参数标签，并将闭包写在函数调用括号之后。

```swift
ZStack {
    // 视图内容
}
```

如果所有参数都有默认值，并且使用了尾随闭包，甚至可以省略空括号。

### 视图构建器中的限制
在视图构建器（如 `body` 或 `ViewBuilder` 闭包）中，只能使用条件语句、列表和局部变量。不能使用循环或其他复杂逻辑。为了创建动态视图列表，我们使用 `ForEach` 视图。

---

## 状态管理与交互

![](img/ef5ad7969d0279c35432f44999e44831_20.png)

### 视图的不可变性
SwiftUI视图是结构体，因此是不可变的。视图中的属性在创建后不能更改。这是SwiftUI声明式编程模型的核心。

![](img/ef5ad7969d0279c35432f44999e44831_22.png)

### `@State` 属性包装器
为了在视图中管理可变状态，我们使用 `@State` 属性包装器。它用于存储与视图显示相关的临时状态（如动画状态），而不是应用的核心数据模型。`@State` 在内存中创建一个指向状态的引用，因此视图本身保持不变，但指向的数据可以改变。

```swift
@State private var isFaceUp = false
```

### 添加交互：按钮与点击手势
我们可以使用 `onTapGesture` 修饰符为视图添加点击交互。也可以使用 `Button` 视图创建标准的交互式按钮。

```swift
// 点击手势
ZStack()
    .onTapGesture {
        isFaceUp.toggle()
    }

// 按钮
Button("添加卡片") {
    cardCount += 1
}
```

按钮的标签可以是任何视图，这提供了极大的灵活性。我们可以使用系统提供的符号（SF Symbols）作为按钮图标。

---

## 构建用户界面

![](img/ef5ad7969d0279c35432f44999e44831_24.png)

![](img/ef5ad7969d0279c35432f44999e44831_26.png)

### 使用栈布局
`HStack` 和 `VStack` 是用于水平或垂直排列子视图的基本布局容器。通过嵌套这些栈，可以构建复杂的界面。

### 创建动态视图列表：`ForEach`
由于视图构建器中不能使用 `for` 循环，我们使用 `ForEach` 视图来动态创建视图列表。`ForEach` 需要一个数据集合（如数组或范围）和一个为每个元素提供视图的闭包。

```swift
ForEach(emojis.indices, id: \.self) { index in
    CardView(content: emojis[index])
}
```

`id` 参数帮助SwiftUI识别列表中的每个元素，这对于动画和性能优化至关重要。

### 网格布局：`LazyVGrid`
为了将卡片排列成网格，我们可以使用 `LazyVGrid`。它通过 `GridItem` 数组来定义列。使用 `.adaptive` 类型的 `GridItem` 可以创建自适应的网格布局。

```swift
LazyVGrid(columns: [GridItem(.adaptive(minimum: 65))]) {
    ForEach(emojis.indices, id: \.self) { index in
        CardView(content: emojis[index])
    }
}
```

### 滚动视图：`ScrollView`
如果内容超出屏幕范围，可以将其包裹在 `ScrollView` 中，以实现滚动浏览。

![](img/ef5ad7969d0279c35432f44999e44831_28.png)

---

## 代码组织与最佳实践

### 提取子视图和计算属性
为了保持 `body` 属性的简洁和可读性，可以将复杂的UI部分提取为单独的计算属性或函数。

```swift
var body: some View {
    VStack {
        cards
        cardCountAdjusters
    }
}

var cards: some View {
    LazyVGrid(columns: [GridItem(.adaptive(minimum: 65))]) {
        // ...
    }
}

func cardCountAdjuster(by offset: Int, symbol: String) -> some View {
    Button {
        // 调整卡片数量
    } label: {
        Image(systemName: symbol)
    }
    .disabled(/* 禁用条件 */)
}
```

### 隐式返回
如果函数或计算属性只有一行代码，可以省略 `return` 关键字，这称为隐式返回。

### 使用 `Group` 应用修饰符
`Group` 是一个视图容器，它本身不改变布局，但允许我们将修饰符同时应用到多个子视图上。

### 使用不透明度替代条件显示
有时，为了保持布局的稳定性（避免视图因条件显示而改变大小），我们可以使用 `.opacity` 修饰符来控制视图的可见性，而不是完全添加或移除视图。

```swift
Group {
    // 卡片正面
}
.opacity(isFaceUp ? 1 : 0)

Group {
    // 卡片背面
}
.opacity(isFaceUp ? 0 : 1)
```

---

![](img/ef5ad7969d0279c35432f44999e44831_30.png)

![](img/ef5ad7969d0279c35432f44999e44831_32.png)

![](img/ef5ad7969d0279c35432f44999e44831_34.png)

## 总结
本节课我们一起学习了SwiftUI的多个核心概念。我们回顾了检查器和项目设置，深入理解了 `some View` 和视图的不可变性。我们掌握了如何使用 `@State` 管理临时状态，以及如何通过 `onTapGesture` 和 `Button` 添加用户交互。在界面构建方面，我们使用了 `HStack`、`VStack`、`ForEach`、`LazyVGrid` 和 `ScrollView` 来创建灵活且响应式的布局。最后，我们探讨了通过提取子视图、使用函数以及合理应用修饰符来组织代码的最佳实践，使代码更清晰、更易维护。这些知识为我们构建更复杂的iOS应用奠定了坚实的基础。