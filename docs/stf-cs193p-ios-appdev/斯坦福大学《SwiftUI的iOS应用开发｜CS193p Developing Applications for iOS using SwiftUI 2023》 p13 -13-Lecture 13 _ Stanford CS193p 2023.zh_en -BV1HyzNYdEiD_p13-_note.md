# SwiftUI iOS应用开发：第13讲：模态视图、导航与多窗格界面

在本节课中，我们将学习如何构建更复杂的用户界面，包括使用模态视图（如Sheet和Popover）来编辑数据，利用导航栈（NavigationStack）和导航链接（NavigationLink）实现界面间的层级跳转，以及创建适用于iPad的多窗格（NavigationSplitView）布局。这些是构建功能丰富、结构清晰的iOS应用的核心技能。

![](img/a889660acbcc6bfb2f8c97c2d79590a3_1.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_2.png)

上一节我们介绍了数据绑定和视图模型，本节中我们来看看如何通过模态视图和导航来组织和管理复杂的用户界面。

## 模态视图：Sheet与Popover

![](img/a889660acbcc6bfb2f8c97c2d79590a3_4.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_5.png)

模态视图是一种临时覆盖在现有内容之上的界面，要求用户立即处理某项任务。SwiftUI提供了两种主要的模态视图：`.sheet`和`.popover`。

![](img/a889660acbcc6bfb2f8c97c2d79590a3_7.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_8.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_10.png)

### 使用`.sheet`展示全屏编辑器

![](img/a889660acbcc6bfb2f8c97c2d79590a3_12.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_14.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_15.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_17.png)

`.sheet`修饰符用于展示一个覆盖大部分屏幕的视图。它需要一个绑定到布尔值的`isPresented`参数来控制显示与隐藏。

```swift
@State private var showPaletteEditor = false

Button("编辑") {
    showPaletteEditor = true
}
.sheet(isPresented: $showPaletteEditor) {
    // 要展示的视图，例如一个编辑器
    PaletteEditor()
        .font(.nil) // 重置字体，避免继承父视图的字体样式
}
```

![](img/a889660acbcc6bfb2f8c97c2d79590a3_19.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_20.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_22.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_24.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_26.png)

当我们将`showPaletteEditor`设置为`true`时，`PaletteEditor`视图会以模态形式弹出。当用户关闭这个视图时，系统会自动将绑定值设回`false`。

![](img/a889660acbcc6bfb2f8c97c2d79590a3_28.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_30.png)

### 使用`.popover`展示上下文相关视图

`.popover`与`.sheet`类似，但它通常指向触发它的UI元素（比如一个按钮），并且不会覆盖整个屏幕，更适合展示额外的选项或信息。

```swift
.popover(isPresented: $showPaletteEditor) {
    PaletteEditor()
        .frame(minWidth: 300, minHeight: 350) // 可以设置最小尺寸
}
```

**核心概念**：无论是`.sheet`还是`.popover`，其`isPresented`参数都是一个**双向绑定**。我们通过代码设置它来显示视图，系统在用户关闭视图时将其设回`false`。

## 构建表单（Form）编辑器

对于数据编辑界面，SwiftUI的`Form`视图是理想的选择。它能自动将内容组织成美观、易用的列表样式，类似于系统设置应用。

```swift
struct PaletteEditor: View {
    @Binding var palette: Palette // 绑定到要编辑的数据源

    var body: some View {
        Form {
            Section(header: Text("名称")) {
                TextField("名称", text: $palette.name) // 绑定到名称
            }
            Section(header: Text("表情符号")) {
                // ... 添加和删除表情符号的UI
            }
        }
    }
}
```

**关键点**：编辑器通过`@Binding`接收数据。这意味着对`TextField`的修改会直接写回外部的视图模型（ViewModel），实现了**单一数据源**的实时同步。

## 实现导航（Navigation）

导航允许用户在视图层级中深入和返回，是大多数应用的基础。

### 导航三要素

![](img/a889660acbcc6bfb2f8c97c2d79590a3_32.png)

实现导航需要三个步骤：

![](img/a889660acbcc6bfb2f8c97c2d79590a3_34.png)

1.  **导航容器**： 使用`NavigationStack`包裹所有需要参与导航的视图。
2.  **导航链接**： 使用`NavigationLink`标记可点击以触发导航的视图。
3.  **导航目标**： 使用`.navigationDestination`修饰符定义点击链接后要显示的目标视图。

```swift
// 1. 导航容器
NavigationStack {
    // 2. 导航链接
    List(stores) { store in
        NavigationLink(value: store) { // 关联的值是`store`
            Text(store.name)
        }
    }
    // 3. 导航目标
    .navigationDestination(for: Store.self) { store in
        // 当`NavigationLink`的value是`Store`类型时，显示此视图
        EditablePaletteList(store: store)
    }
}
```

### 导航标题

![](img/a889660acbcc6bfb2f8c97c2d79590a3_36.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_38.png)

可以通过`.navigationTitle`修饰符为当前显示的视图设置标题。标题会自动显示在导航栏，并且返回按钮的文字也会随之变化。

```swift
EditablePaletteList(store: store)
    .navigationTitle(store.name)
```

## 创建可编辑列表

![](img/a889660acbcc6bfb2f8c97c2d79590a3_40.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_42.png)

列表（`List`）结合`ForEach`可以轻松实现滑动删除和移动排序功能。

以下是实现可编辑列表的操作：

*   **滑动删除**： 在`ForEach`上使用`.onDelete`修饰符。
*   **移动排序**： 在`ForEach`上使用`.onMove`修饰符。
*   **工具栏按钮**： 在`NavigationStack`内的视图上使用`.toolbar`修饰符添加顶部按钮。

```swift
List {
    ForEach(store.palettes) { palette in
        PaletteRow(palette: palette)
    }
    .onDelete { indexSet in // 滑动删除
        store.palettes.remove(atOffsets: indexSet)
    }
    .onMove { indexSet, newOffset in // 长按移动
        store.palettes.move(fromOffsets: indexSet, toOffset: newOffset)
    }
}
.toolbar {
    Button {
        store.palettes.insert(Palette(name: "", emojis: ""), at: 0) // 添加新项
    } label: {
        Image(systemName: "plus")
    }
}
```

## 为iPad设计：多窗格界面（NavigationSplitView）

![](img/a889660acbcc6bfb2f8c97c2d79590a3_44.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_46.png)

在iPad或Mac等大屏设备上，可以使用`NavigationSplitView`同时展示多个层级的视图，提供更高效的导航体验。

```swift
// 三栏布局示例
NavigationSplitView {
    // 侧边栏：第一栏（例如商店列表）
    List(stores, selection: $selectedStore) { store in
        Text(store.name).tag(store) // `.tag`将视图与选择值关联
    }
} content: {
    // 内容栏：第二栏（例如选中商店的表情符号集列表）
    if let selectedStore {
        EditablePaletteList(store: selectedStore)
    } else {
        Text("选择一个商店")
    }
} detail: {
    // 详情栏：第三栏（例如选中表情符号集的编辑器）
    if let selectedPaletteID {
        // 根据ID查找并显示编辑器
    }
}
```

![](img/a889660acbcc6bfb2f8c97c2d79590a3_48.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_50.png)

**关键点**：
*   `selection`参数配合`@State`变量和`.tag()`修饰符，可以管理列表中的选中项。
*   各栏视图可以根据选中状态动态变化。
*   确保导航逻辑（`NavigationLink`）与`NavigationSplitView`的层级配合，有时需要移除内层的`NavigationStack`以避免冲突。

## 处理键盘焦点

![](img/a889660acbcc6bfb2f8c97c2d79590a3_52.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_54.png)

为了让视图出现时自动聚焦到某个输入框并弹出键盘，可以使用`@FocusState`。

![](img/a889660acbcc6bfb2f8c97c2d79590a3_56.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_58.png)

```swift
enum Field { case name, addEmojis }

![](img/a889660acbcc6bfb2f8c97c2d79590a3_60.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_62.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_64.png)

struct PaletteEditor: View {
    @Binding var palette: Palette
    @FocusState private var focusedField: Field? // 可选的焦点状态

    var body: some View {
        Form {
            TextField("名称", text: $palette.name)
                .focused($focusedField, equals: .name) // 绑定到.name状态
            TextField("添加表情符号", text: $emojiInput)
                .focused($focusedField, equals: .addEmojis) // 绑定到.addEmojis状态
        }
        .onAppear {
            // 视图出现时，根据条件设置焦点
            focusedField = palette.name.isEmpty ? .name : .addEmojis
        }
    }
}
```

![](img/a889660acbcc6bfb2f8c97c2d79590a3_66.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_68.png)

![](img/a889660acbcc6bfb2f8c97c2d79590a3_70.png)

本节课中我们一起学习了SwiftUI中构建复杂界面的几种关键模式：使用Sheet和Popover进行模态展示，利用NavigationStack和NavigationLink实现视图导航，通过Form和List构建数据编辑界面，以及为iPad适配多窗格的NavigationSplitView。掌握这些模式，你将能够设计出结构清晰、交互流畅的iOS应用程序。