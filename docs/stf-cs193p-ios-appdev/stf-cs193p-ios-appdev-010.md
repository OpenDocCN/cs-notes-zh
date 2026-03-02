# 010：EmojiArt应用入门与拖放功能 🎨

在本节课中，我们将开始构建一个全新的应用——EmojiArt。这个应用允许用户使用表情符号创作艺术作品。我们将学习拖放功能、手势操作、多视图模型（MVVM）架构，以及如何处理颜色、图像和多线程错误。课程将从创建项目开始，逐步实现应用的核心功能。

## 概述 📋

EmojiArt应用的核心功能包括：
- 使用表情符号创作艺术作品。
- 通过拖放功能添加背景图像和表情符号。
- 支持缩放和平移操作。
- 使用多视图模型（MVVM）架构管理应用状态。

接下来，我们将从创建项目开始，逐步实现这些功能。

## 创建项目与模型 🛠️

首先，我们需要在Xcode中创建一个新项目。选择“App”模板，将项目命名为“EmojiArt”，并确保选择iPad作为目标设备，以便在开发过程中获得更大的操作空间。

### 定义数据模型

数据模型是应用的核心，它定义了艺术作品的结构。我们的模型包括背景图像和表情符号的位置、大小等信息。

以下是EmojiArt数据模型的代码：

```swift
struct EmojiArt {
    var background: URL?
    var emojis: [Emoji]

    struct Emoji: Identifiable {
        let id: Int
        let string: String
        var position: Position
        var size: Int

        struct Position {
            var x: Int
            var y: Int
        }
    }
}
```

在这个模型中：
- `background` 存储背景图像的URL。
- `emojis` 是一个数组，包含所有表情符号及其位置和大小信息。
- `Emoji` 结构体实现了 `Identifiable` 协议，确保每个表情符号都有唯一的标识符。

### 添加表情符号功能

为了管理表情符号的添加，我们在模型中添加一个函数：

```swift
mutating func addEmoji(_ emoji: String, at position: Emoji.Position, size: Int) {
    uniqueEmojiID += 1
    emojis.append(Emoji(id: uniqueEmojiID, string: emoji, position: position, size: size))
}
```

![](img/15c6a875e6864a9723d1c9635dc2cb11_1.png)

![](img/15c6a875e6864a9723d1c9635dc2cb11_3.png)

这个函数会为每个新添加的表情符号分配一个唯一的ID，并确保模型的状态可以被正确修改。

## 视图模型（ViewModel） 🧩

视图模型负责将数据模型转换为视图可以使用的格式。在EmojiArt中，视图模型还提供了拖放功能的支持。

以下是视图模型的核心代码：

```swift
class EmojiArtDocument: ObservableObject {
    @Published private var emojiArt = EmojiArt()

    var emojis: [EmojiArt.Emoji] {
        emojiArt.emojis
    }

    var background: URL? {
        emojiArt.background
    }

    func setBackground(_ url: URL) {
        emojiArt.background = url
    }

    func addEmoji(_ emoji: String, at position: CGPoint, size: CGFloat) {
        let emojiPosition = EmojiArt.Emoji.Position(x: Int(position.x), y: Int(position.y))
        emojiArt.addEmoji(emoji, at: emojiPosition, size: Int(size))
    }
}
```

视图模型通过 `@Published` 属性包装器确保数据变化时视图能够及时更新。同时，它提供了添加表情符号和设置背景图像的功能。

## 视图（View）设计 🖼️

视图是用户与应用交互的界面。在EmojiArt中，视图包括背景图像和表情符号的显示区域。

### 主视图结构

主视图使用 `ZStack` 布局，将背景图像和表情符号叠加显示：

![](img/15c6a875e6864a9723d1c9635dc2cb11_5.png)

![](img/15c6a875e6864a9723d1c9635dc2cb11_7.png)

```swift
struct EmojiArtDocumentView: View {
    @ObservedObject var document: EmojiArtDocument

    var body: some View {
        GeometryReader { geometry in
            ZStack {
                Color.white
                AsyncImage(url: document.background)
                    .position(CGPoint(x: geometry.size.width / 2, y: geometry.size.height / 2))
                ForEach(document.emojis) { emoji in
                    Text(emoji.string)
                        .font(.system(size: CGFloat(emoji.size)))
                        .position(emoji.position.in(geometry))
                }
            }
        }
    }
}
```

![](img/15c6a875e6864a9723d1c9635dc2cb11_9.png)

![](img/15c6a875e6864a9723d1c9635dc2cb11_10.png)

![](img/15c6a875e6864a9723d1c9635dc2cb11_12.png)

![](img/15c6a875e6864a9723d1c9635dc2cb11_14.png)

在这个视图中：
- `GeometryReader` 用于获取视图的坐标系统，以便正确放置表情符号。
- `AsyncImage` 异步加载背景图像，避免阻塞用户界面。
- 表情符号通过 `ForEach` 循环动态生成，并根据其位置和大小进行布局。

### 添加拖放功能

拖放功能是EmojiArt的核心交互之一。我们通过 `draggable` 和 `dropDestination` 修饰符实现。

以下是实现拖放功能的代码：

```swift
struct EmojiArtDocumentView: View {
    // ... 其他代码

    var body: some View {
        GeometryReader { geometry in
            ZStack {
                // ... 背景和表情符号
            }
            .dropDestination(for: SterileData.self) { items, location in
                return drop(items, at: location, in: geometry)
            }
        }
    }

    private func drop(_ items: [SterileData], at location: CGPoint, in geometry: GeometryProxy) -> Bool {
        for item in items {
            switch item {
            case .url(let url):
                document.setBackground(url)
                return true
            case .string(let emoji):
                let emojiPosition = emojiPosition(at: location, in: geometry)
                document.addEmoji(emoji, at: emojiPosition, size: 40)
                return true
            default:
                break
            }
        }
        return false
    }
}
```

在这个实现中：
- `dropDestination` 修饰符允许视图接收拖放的数据。
- `SterileData` 是一个自定义类型，支持字符串、URL和图像数据的拖放。
- `drop` 函数根据拖放的数据类型执行相应的操作，例如设置背景图像或添加表情符号。

![](img/15c6a875e6864a9723d1c9635dc2cb11_16.png)

## 手势操作与缩放功能 ✋

![](img/15c6a875e6864a9723d1c9635dc2cb11_18.png)

![](img/15c6a875e6864a9723d1c9635dc2cb11_20.png)

![](img/15c6a875e6864a9723d1c9635dc2cb11_22.png)

接下来，我们将为EmojiArt添加手势操作功能，支持缩放和平移。这是通过 `gesture` 修饰符实现的。

![](img/15c6a875e6864a9723d1c9635dc2cb11_24.png)

![](img/15c6a875e6864a9723d1c9635dc2cb11_26.png)

以下是实现缩放功能的代码：

```swift
struct EmojiArtDocumentView: View {
    @State private var zoomScale: CGFloat = 1.0

    var body: some View {
        GeometryReader { geometry in
            ZStack {
                // ... 背景和表情符号
            }
            .scaleEffect(zoomScale)
            .gesture(
                MagnificationGesture()
                    .onChanged { value in
                        zoomScale = value
                    }
            )
        }
    }
}
```

在这个实现中：
- `MagnificationGesture` 用于检测缩放手势。
- `scaleEffect` 修饰符根据缩放比例调整视图的大小。

## 总结 🎉

在本节课中，我们一起学习了如何构建EmojiArt应用的核心功能。我们从创建项目和定义数据模型开始，逐步实现了视图模型和视图的设计。通过拖放功能，用户可以轻松添加背景图像和表情符号。此外，我们还介绍了手势操作的基本实现，为后续的缩放和平移功能打下基础。

![](img/15c6a875e6864a9723d1c9635dc2cb11_28.png)

在接下来的课程中，我们将进一步完善EmojiArt应用，添加更多交互功能，例如多选表情符号、调整大小和位置等。希望本节课的内容能够帮助你更好地理解SwiftUI和iOS应用开发的核心概念。继续加油，期待在下一节课中与你再次相见！