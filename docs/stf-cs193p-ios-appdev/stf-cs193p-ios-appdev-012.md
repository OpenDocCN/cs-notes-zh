# 012：数据持久化

在本节课中，我们将要学习数据持久化，即如何让数据在应用被关闭、设备重启等情况下依然保存在设备上。我们首先会讨论本地持久化，即数据存储在设备上，并会通过EmojiArt应用来实践这些概念。之后，我们将深入探讨属性包装器，如 `@State`、`@Published`、`@ObservedObject` 等，帮助你理解它们的工作原理。

## 概述

数据持久化是应用开发中的核心概念，它确保用户数据不会丢失。iOS提供了多种持久化方案，包括文件系统、SQL数据库、Core Data、iCloud以及UserDefaults等。本节课我们将重点介绍文件系统存储和UserDefaults这两种方式。

## 文件系统存储

iOS底层是一个类Unix操作系统，拥有一个受保护的文件系统。每个应用都运行在一个“沙盒”中，只能访问自己沙盒内的文件，这保证了安全性和隐私性。

### 沙盒目录

沙盒中包含几个重要的目录：
*   **应用程序目录**：存放应用的可执行文件和资源文件，只读。
*   **文档目录**：存放用户创建的数据，如文档。
*   **应用支持目录**：存放应用运行所需但不被用户直接感知的数据。
*   **缓存目录**：存放可重新生成的数据，不会备份到iCloud。

### 使用URL访问文件

我们使用 `URL` 结构体来定位沙盒中的文件。可以通过 `URL` 的静态属性获取沙盒目录的URL，然后通过追加路径组件来构建具体的文件路径。

```swift
let documentsURL = URL.documentsDirectory
let fileURL = documentsURL.appendingPathComponent("fileName.doc")
```

### 读写数据

`Data` 结构体代表一个字节包，是读写文件的主要方式。
*   **读取**：使用 `Data(contentsOf: url)` 初始化器。
*   **写入**：使用 `data.write(to: url)` 方法。

这些操作都可能抛出错误，例如磁盘已满或文件不存在。

### 文件管理器

`FileManager` 用于管理文件系统本身，例如复制文件、创建目录、列出目录内容等。通常使用其默认实例 `FileManager.default`。

## Codable与JSON编码

我们的应用数据通常是结构体或类，而非原始的 `Data`。`Codable` 协议可以将这些自定义类型与JSON数据相互转换。

![](img/cee66300f59cb9b7e3bf1b25d3ac7e85_1.png)

![](img/cee66300f59cb9b7e3bf1b25d3ac7e85_2.png)

### 使类型可编码

如果一个结构体的所有属性都是 `Codable` 的，那么只需声明该结构体遵循 `Codable` 协议即可自动获得编码和解码能力。Swift标准库中的许多类型（如 `String`、`Int`、`URL`、`Array`、`Dictionary`、`Optional`）都遵循 `Codable`。

### 编码与解码

*   **编码为JSON Data**：使用 `JSONEncoder().encode(object)`。
*   **从JSON Data解码**：使用 `JSONDecoder().decode(Type.self, from: data)`。

这两个操作都可能抛出错误，需要进行错误处理。

## UserDefaults

`UserDefaults` 是一个轻量级的持久化字典，适合存储用户偏好设置等小量数据。它并不是存储重要数据的首选方案。

### 使用UserDefaults

通常使用标准实例 `UserDefaults.standard`。存储的数据必须是“属性列表”类型，包括 `String`、`Data`、`Date`、`Array`、`Dictionary` 等。

*   **存储数据**：使用 `set(_:forKey:)` 方法。
*   **读取数据**：使用类型特定的方法，如 `string(forKey:)`、`array(forKey:)`、`data(forKey:)` 等，这些方法返回可选值。

由于 `Data` 是属性列表类型，我们可以将任何 `Codable` 对象编码为JSON Data后存入 `UserDefaults`。

## 错误处理

许多持久化操作可能失败，Swift使用“抛出错误”的机制来处理这些情况。

### 处理可能抛出错误的函数

调用标记为 `throws` 的函数时，必须使用 `try` 关键字。有几种处理方式：

![](img/cee66300f59cb9b7e3bf1b25d3ac7e85_4.png)

1.  **`try?`**：忽略错误，如果失败则返回 `nil`。
2.  **`try!`**：确信不会失败，如果失败则程序崩溃。常用于调试。
3.  **向上传递**：将当前函数也标记为 `throws`，让调用者处理。
4.  **`do-catch` 语句**：捕获并处理错误。

```swift
do {
    let data = try Data(contentsOf: fileURL)
    // 处理数据
} catch {
    print("读取文件失败: \(error.localizedDescription)")
}
```

## 属性包装器

属性包装器为属性添加了统一的管理逻辑。我们常用的 `@State`、`@Published`、`@ObservedObject` 等都是属性包装器。

### 工作原理

当声明 `@Published var emojiArt: EmojiArt` 时，Swift会创建一个 `Published` 结构体的实例。这个实例包含：
*   **`wrappedValue`**：存储实际的值（`EmojiArt`）。
*   **`projectedValue`**：通过 `$emojiArt` 访问，对于 `@Published`，这是一个发布者。

### 常见属性包装器详解

*   **`@State`**
    *   **作用**：将值存储到堆中，保持其稳定性，并在值改变时使视图失效（重新绘制）。
    *   **`$` 投影值**：一个 `Binding`（绑定），可以传递给其他视图，让它们修改此状态。
*   **`@ObservedObject` / `@StateObject`**
    *   **作用**：观察一个遵循 `ObservableObject` 的类（如ViewModel），当其发布变化（通过 `objectWillChange.send()`）时，使视图失效。
    *   **区别**：`@StateObject` 由当前视图创建并拥有生命周期；`@ObservedObject` 由外部传入。
    *   **`$` 投影值**：一个 `Binding`，可以访问到被观察对象内部的可变属性。
*   **`@Binding`**
    *   **作用**：创建一个到其他源（如 `@State` 或 `@ObservedObject` 的属性）的绑定。对该绑定的读写会直接反映到源上，并可能使相关视图失效。
    *   **用途**：在子视图中修改父视图的状态，或连接UI控件（如 `TextField`、`Toggle`）到状态。
*   **`@EnvironmentObject`**：用于接收通过环境传递的共享可观察对象。
*   **`@Environment`**：用于读取诸如颜色方案、布局方向等系统环境值。

### 绑定的重要性

绑定是SwiftUI数据流的核心，它确保了“单一数据源”原则。我们通过将 `@State` 或 `@ObservedObject` 属性的投影值（`$`）传递给子视图或UI控件，使它们能够直接修改源数据，而不是持有数据的副本。

## 总结

本节课我们一起学习了iOS数据持久化的基础知识。我们了解了如何使用文件系统来保存和加载应用数据，通过 `Codable` 协议将自定义类型与JSON格式相互转换，并使用了 `UserDefaults` 来存储轻量级的用户偏好。此外，我们还深入探讨了错误处理的方法以及SwiftUI中关键属性包装器的工作原理，特别是绑定如何在不同视图间建立数据连接。掌握这些概念对于构建能持久保存数据、反应灵敏的iOS应用至关重要。