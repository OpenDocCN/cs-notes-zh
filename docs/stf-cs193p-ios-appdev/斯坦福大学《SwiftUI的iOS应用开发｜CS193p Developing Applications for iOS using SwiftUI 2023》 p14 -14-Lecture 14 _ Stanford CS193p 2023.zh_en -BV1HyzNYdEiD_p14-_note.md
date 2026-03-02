# SwiftUI iOS应用开发：第14讲：颜色、图像与多线程编程 🎨

在本节课中，我们将学习两个主题。首先，我们会简要介绍颜色和图像在SwiftUI中的表示方式，这是一个相对简单的知识点。然后，我们将深入探讨今天的核心内容——多线程编程。我们还将重新审视错误处理，并学习更多相关知识。多线程编程的核心目标是确保我们的应用保持响应，避免因长时间操作而导致的界面卡顿，从而为用户提供流畅的体验。

## 颜色与图像 🎨

上一节我们概述了本节课的内容，本节中我们来看看颜色和图像的具体表示。

### 颜色

你已经了解过 `Color` 结构体。它是一个非常酷的结构体，因为它实现了多种协议。它可以用来指定颜色，例如 `Color.green` 表示将前景色设置为绿色。同时，正如我们所见，它也可以作为形状样式使用，例如 `fill(Color.green)` 可以像渐变或其他形状样式一样进行填充。有趣的是，`Color` 甚至可以作为视图使用，例如 `Color.white` 会创建一个填充为白色的矩形，因为 `Color` 也实现了 `View` 协议。

然而，在计算机世界中精确表示一个颜色是件复杂的事情。例如，一个特定的粉色色调，在广告中可能需要精确地激发用户的情感反应。因此，存在多种机制来非常具体和准确地指定颜色。`Color` 结构体本身并不直接处理这些底层细节。

实际上，我们使用 `UIColor` 来真正表示一个颜色。它知道如何在不同的色彩空间（如RGB或HSB）中创建颜色。你可以通过 `Color(uiColor: someUIColor)` 轻松地从 `UIColor` 创建一个 `Color` 结构体。理解 `Color` 和 `UIColor` 的区别很重要，因为你会在代码中同时看到它们。

此外，还有一个 `CGColor`，它是Core Graphics系统中颜色的底层表示。你可能会偶尔看到它，例如通过 `Color` 的 `cgColor` 属性获取，但这种情况相对少见。

### 图像

图像也存在类似的双重表示。我们熟悉 `Image` 结构体，用它来在屏幕上显示图像，特别是通过 `systemName` 参数使用系统图标。你也可以将JPEG等图像文件拖入项目的Assets资源目录中，并通过 `Image("name")` 来使用它们。Assets目录允许你指定图像的分辨率等属性。

`Image` 还可以通过 `.font` 修饰符来缩放系统图标以匹配字体大小。系统图标另一个常见用途是作为遮罩使用，例如底部标签栏的图标，它们会通过颜色过滤来显示。

但是，如果你想在代码中“持有”一个图像数据（例如从网络下载的JPEG数据），你需要使用 `UIImage`。`UIImage` 可以将JPEG等数据转换为图像对象。例如，`AsyncImage` 视图在从网络获取图像时，内部会先将数据转换为 `UIImage`，然后再用 `Image` 显示它。今天我们在构建自己的异步图像加载器时就会看到这个过程。

## 多线程编程 ⚙️

上一节我们介绍了颜色和图像的基础知识，本节中我们来看看为何以及如何进行多线程编程。

我们绝对不希望阻塞用户界面。所有用户都曾遇到过应用卡顿、触摸无响应的情况，这种体验非常糟糕，用户会因此停止使用这类应用。所以，我们必须找到方法避免这种情况，即使有时我们需要执行耗时的操作。

哪些操作会导致这个问题呢？任何网络访问操作都肯定需要多线程处理，因为网络请求可能耗时数秒甚至一分钟，我们不能让应用在此期间完全卡住。此外，一些非常消耗CPU的计算任务（例如机器学习模型推理）也可能耗时很长，同样不能在主线程上执行。

我们的解决方案是使用线程。线程是执行的路径。现代操作系统和设备大多支持多线程，即使是在单核处理器上，操作系统也可以通过快速切换来模拟并行执行。从程序员的角度看，就像是应用中的多段代码在同时运行。

在Swift中，线程由系统在幕后管理，我们不需要手动创建线程。但系统需要我们的帮助，通过一些API关键字来提示它何时可以将任务放到其他线程上执行。

### 使用 Task

以下是多线程编程中最基本的概念。如果你有一段可能耗时的代码，不希望它在运行UI的主线程上执行，你可以创建一个 `Task` 对象。

```swift
Task(priority: .background) {
    // 这里放置可能耗时的代码，例如网络请求
}
```

`Task` 接受一个优先级参数，表示这个任务的重要程度。UI相关的任务几乎总是拥有最高优先级。你只需提供一个闭包，闭包内的代码将在某个其他线程上运行。你不需要知道具体是哪个线程，系统会管理这一切。

关键点在于，创建 `Task` 的这行代码会立即返回。系统会获取这个闭包，并将其放入队列，准备在其他线程上执行。返回值是一个 `Task` 句柄，可以用来取消任务（但取消只是设置一个标志，任务本身需要检查并优雅退出）、等待任务完成等。不过，大多数时候我们只是简单地使用 `Task { ... }` 来启动一个任务，然后就不管它了。

这看起来很简单，但多线程编程有一个巨大的问题：对数据结构的并发访问。如果多个线程同时读写同一个数据结构（比如数组），会导致数据损坏。Swift通过一种类型帮助我们管理这种共享访问。

### 使用 Actor

除了之前提到的类、结构体、枚举和函数，Swift类型系统还有一个重要的成员：`actor`。`actor` 的声明方式与 `class` 或 `struct` 类似。

```swift
actor MyActor {
    var myData: [String] = []
    func updateData() { ... }
}
```

`actor` 有两个关键特性：
1.  它是引用类型（像类一样），可以有多处引用指向同一个 `actor` 实例。
2.  它会同步对其内部变量和函数的所有访问。`actor` 是同步的基本单元。

`actor` 的工作规则如下：
*   **规则一**：在任意时刻，一个 `actor` 中最多只能有一个函数或变量访问器正在运行。即使有100个线程可以运行这个 `actor` 的代码，同一时间也只有一个能执行。这从根本上防止了数据竞争。
*   **规则二**：`actor` 中的函数要么运行到完成，要么可以被**挂起**。如果一个函数被挂起，那么 `actor` 就可以去运行其他函数。正是这些“挂起点”使得在保证同步的同时，还能在多个函数间切换执行。

### 异步函数与 Await

为了让系统知道一个函数可能被挂起，我们需要将其标记为 `async`。

```swift
func fetchImage(from url: URL) async throws -> UIImage {
    // 这里可能包含网络请求等耗时操作
}
```

调用一个 `async` 函数时，必须使用 `await` 关键字。

```swift
let image = try await fetchImage(from: someURL)
```

`await` 意味着“等待”。它表明此处可能会发生挂起。当执行到 `await` 时，当前函数可能会被挂起，`actor` 就可以去执行其他任务。当 `await` 的操作完成后，`actor` 会在合适的时候恢复执行这个函数。

**重要提示**：由于在 `await` 期间 `actor` 可能执行了其他代码，改变了内部状态，因此在 `await` 之后，你需要检查之前的假设是否仍然成立。这是多线程编程中需要仔细思考的部分。

如果你想启动一个耗时任务，但又不想让当前函数被挂起（例如，你在主线程上，希望保持UI响应），你可以将这个任务包装在 `Task` 中。这样，耗时操作在 `Task` 的闭包中运行，而当前函数可以立即继续执行。

### 闭包与异步

闭包本身不能直接标记为 `async`。只有当函数明确声明其参数闭包可以是 `async` 时，你才能在该闭包内使用 `await`。例如，SwiftUI 中的 `.task` 和 `.refreshable` 修饰符就接受异步闭包。

```swift
.someView
    .task {
        // 这里可以安全地使用 await
        let data = try await loadData()
    }
```

`.task` 修饰符特别有用，它会在视图出现时启动任务，并在视图消失时自动取消任务，非常适合用于加载视图所需的数据。

### 主线程 Main Actor

UI 是一个巨大的、需要被保护的数据结构。所有 UI 操作都必须在**主线程**（Main Thread）上执行，在 Swift 并发模型中，这对应着 **主Actor（Main Actor）**。

*   所有视图（`View`）中的代码默认都在主Actor上运行。
*   你的视图模型（ViewModel）默认**不**在主Actor上运行。如果视图模型中的代码会更新UI，这就会导致问题。

解决方案是使用 `@MainActor` 属性包装器：

```swift
@MainActor
class MyViewModel: ObservableObject {
    // 这个类中的所有代码都将在主Actor上运行
}
```

你也可以只标记特定的方法：

```swift
class MyViewModel: ObservableObject {
    @MainActor
    func updateUI() {
        // 这个方法将在主Actor上运行
    }
}
```

如果你在非主Actor的线程上修改了 `@Published` 属性（从而触发UI更新），Xcode会在运行时显示紫色的警告。**永远不要忽略这些警告**，否则应用在用户设备上可能会出现不可预知的UI错误。

## 错误处理 🚨

上一节我们深入探讨了多线程机制，本节中我们来看看与之紧密相关的错误处理。

异步编程和错误处理配合得非常好。如果一个 `async` 函数在等待（`await`）时发生错误（例如网络故障），它可以立即 `throw` 这个错误。这使得等待该函数的任务能够被迅速唤醒并处理错误。

语法上，错误处理和多线程也很相似：
*   可能抛出错误的函数用 `throws` 标记，调用时用 `try`。
*   可能挂起的函数用 `async` 标记，调用时用 `await`。
*   两者经常结合使用：`async throws` 函数和 `try await` 调用非常常见。

### 抛出与捕获错误

要抛出自定义错误，可以定义一个遵循 `Error` 协议的类型（通常是枚举）：

```swift
enum MyError: Error {
    case networkFailure
    case invalidData
    case missedLecture
}

func doSomethingRisky() throws {
    if somethingBadHappened {
        throw MyError.missedLecture
    }
    // 如果抛出错误，函数会在此处退出
}
```

使用 `do-catch` 块来捕获和处理错误：

```swift
do {
    try doSomethingRisky()
    print("Success!")
} catch MyError.missedLecture {
    print("You missed the lecture!")
} catch {
    print("An unexpected error occurred: \(error)")
}
// 捕获错误后，代码会继续执行
```

你可以有多个 `catch` 分支来处理特定的错误类型，并使用 `is` 关键字进行类型判断。

## 实战：构建背景图片加载器 🖼️

现在，让我们将所学知识应用到一个实际案例中：为我们的应用构建一个背景图片加载器，替换掉之前使用的 `AsyncImage`，并实现更好的状态控制和错误处理。

我们将使用**状态机（State Machine）** 的概念来建模图片加载过程。状态机非常适合用枚举来表示。

### 定义状态

首先，我们定义一个枚举来表示所有可能的状态：

```swift
enum Background {
    case none // 无背景
    case fetching(URL) // 正在获取，关联要获取的URL
    case found(UIImage) // 获取成功，关联UIImage
    case failed(String) // 获取失败，关联错误信息字符串
}
```

为了方便使用，我们为这个枚举添加一些计算属性：

```swift
extension Background {
    var uiImage: UIImage? {
        if case .found(let image) = self { return image }
        return nil
    }
    var isFetching: Bool {
        if case .fetching = self { return true }
        return false
    }
    var failureReason: String? {
        if case .failed(let reason) = self { return reason }
        return nil
    }
}
```

在视图模型中，我们将使用 `@Published` 属性来存储当前状态：

![](img/b311cefdf46e6b0a9631e4d8ec511d35_1.png)

![](img/b311cefdf46e6b0a9631e4d8ec511d35_2.png)

```swift
@Published var background: Background = .none
```

### 在视图中使用状态

在视图中，我们可以根据状态来显示不同的内容：

```swift
// 如果成功获取到图片，则显示
if let uiImage = viewModel.background.uiImage {
    Image(uiImage: uiImage)
        .position(...)
}
// 如果正在获取，则显示进度指示器
if viewModel.background.isFetching {
    ProgressView()
        .scaleEffect(2)
        .tint(.blue)
        .position(...)
}
// 监听失败状态，显示警告框
.onChange(of: viewModel.background.failureReason) { reason in
    if reason != nil {
        showBackgroundFailureAlert = true
    }
}
.alert("Set Background",
       isPresented: $showBackgroundFailureAlert,
       presenting: viewModel.background.failureReason) { reason in
    Button("OK", role: .cancel) { }
} message: { reason in
    Text(reason)
}
```

### 实现状态转换

状态转换的触发点是在视图模型中，当背景URL发生变化时：

```swift
// 在视图模型的 didSet 观察器中
@Published var emojiArt: EmojiArt {
    didSet {
        if emojiArt.background != oldValue.background {
            // 不能直接在属性观察器中调用 async 函数，所以使用 Task
            Task {
                await fetchBackgroundImage()
            }
        }
    }
}
```

`fetchBackgroundImage` 函数驱动状态机运转：

![](img/b311cefdf46e6b0a9631e4d8ec511d35_4.png)

![](img/b311cefdf46e6b0a9631e4d8ec511d35_6.png)

```swift
private func fetchBackgroundImage() async {
    guard let url = emojiArt.background else {
        background = .none
        return
    }
    // 状态1: 开始获取
    background = .fetching(url)
    do {
        // 状态2 & 3: 尝试获取图片，可能成功或失败
        let image = try await fetchUIImage(from: url)
        // 关键检查：在等待期间，用户可能已经更改了URL
        if url == emojiArt.background {
            // 状态3: 获取成功
            background = .found(image)
        }
    } catch {
        // 状态4: 获取失败
        background = .failed("Could not set background: \(error.localizedDescription)")
    }
}
```

### 实现网络请求

`fetchUIImage(from:)` 函数执行实际的网络请求。**注意**：我们使用 `URLSession.shared.data(from:)` 这个 `async throws` 方法，而不是会阻塞线程的 `Data(contentsOf:)`。

```swift
private func fetchUIImage(from url: URL) async throws -> UIImage {
    let (data, _) = try await URLSession.shared.data(from: url)
    if let image = UIImage(data: data) {
        return image
    } else {
        throw FetchError.badImageData
    }
}

enum FetchError: Error {
    case badImageData
}
```

### 确保主线程更新

由于网络请求在 `Task` 中发起，它默认不在主Actor上运行。而更新 `@Published` 的 `background` 属性会触发UI更新，这必须在主线程上进行。我们有几种解决方法：

1.  **将整个视图模型标记为 `@MainActor`**（简单直接）：
    ```swift
    @MainActor
    class EmojiArtDocumentViewModel: ObservableObject { ... }
    ```
2.  **仅将更新状态的方法标记为 `@MainActor`**（更精确）：
    ```swift
    @MainActor
    private func fetchBackgroundImage() async { ... }
    ```

![](img/b311cefdf46e6b0a9631e4d8ec511d35_8.png)

这样，当 `fetchBackgroundImage` 函数需要执行时，系统会确保它在主Actor的线程上运行。如果主Actor正忙（例如用户正在交互），函数会挂起等待，直到主线程空闲。这完美地解决了线程安全问题。

![](img/b311cefdf46e6b0a9631e4d8ec511d35_10.png)

### 更多增强功能

基于这个清晰的状态机，我们可以轻松添加更多功能：
*   **双击缩放**：双击画布可以缩放以包含所有表情和背景图。
*   **自适应缩放**：当拖入新背景时，自动调整缩放比例以适应画布。
*   **这些功能都得益于我们对图片加载状态的精确掌控。**

## 总结 📚

本节课中我们一起学习了以下核心内容：

1.  **颜色与图像**：了解了 `Color`/`UIColor` 和 `Image`/`UIImage` 的区别与联系，前者用于界面描述，后者用于底层数据表示。
2.  **多线程编程的必要性**：为了避免耗时操作（网络、计算）阻塞用户界面，导致应用卡顿。
3.  **Swift 并发模型**：
    *   使用 `Task { ... }` 将耗时任务转移到后台线程。
    *   使用 `actor` 来安全地同步共享数据的访问。
    *   使用 `async` 标记可能挂起的函数，使用 `await` 调用它们，并理解在 `await` 后需要重新验证程序状态。
    *   理解了**主Actor（`@MainActor`）** 的重要性，所有UI更新都必须发生在主Actor上。
4.  **错误处理**：结合 `async`/`await` 使用 `throw`/`try`/`catch`，可以优雅地处理异步操作中的失败。
5.  **实战应用**：我们构建了一个基于状态机的背景图片加载器，它能够清晰地管理加载状态、显示进度、处理错误，并确保所有UI更新都在正确的线程上执行。这个案例展示了如何将并发编程、错误处理和状态管理结合起来，创建出健壮且响应迅速的用户界面。

![](img/b311cefdf46e6b0a9631e4d8ec511d35_12.png)

通过掌握这些知识，你能够编写出不会冻结、反应灵敏的iOS应用，从而为用户提供卓越的使用体验。