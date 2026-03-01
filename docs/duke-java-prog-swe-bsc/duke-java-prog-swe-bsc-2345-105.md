# 105：解析日志文件

在本节课中，我们将学习如何解析Web服务器日志文件，以创建日志条目类的实例。我们将编写一个日志分析器类，其构造函数和读取文件的方法，为后续的数据分析工作做好准备。

## 解析日志行

上一节我们创建了日志条目类。本节中，我们来看看如何解析Web服务器日志的每一行，以便能够创建该类的实例。

此任务的核心是将字符串分割成适当的字段，以便将值传递给日志条目类的构造函数。虽然可以通过多次调用 `indexOf` 和 `substring` 方法来完成，但代码会非常繁琐。例如，处理时间部分需要将字符串转换为Java内置的 `Date` 对象。尽管Java提供了 `Date` 类和解析字符串的方法，但其接口复杂，且服务器日志中的日期格式并非Java默认格式。

因此，课程提供了现成的代码来简化这一过程。以下是使用该解析器的方法：

```java
LogEntry entry = WebLogParser.parseEntry(logLineString);
```

调用 `WebLogParser.parseEntry` 并传入要解析的字符串，该方法将返回一个 `LogEntry` 对象。

## 编写日志分析器类

了解了如何解析单行日志后，现在我们将注意力转向开始编写日志分析器类。目前，我们将在构造函数中编写初始化对象的代码，然后编写 `readFile` 方法。在后续课程中，我们将编写其他方法来对已读取的日志文件执行实际分析。

### 构造函数

首先，填写构造函数的代码。构造函数应将记录字段初始化为一个空的 `ArrayList`。以下是具体步骤：

```java
public LogAnalyzer() {
    records = new ArrayList<LogEntry>();
}
```

### readFile 方法

其次，填写 `readFile` 方法的代码。此方法将确定要读取的文件名，然后根据打开的文件信息，将日志条目添加到 `records` 字段中。以下是实现此任务的步骤：

1.  为请求的文件创建一个 `FileResource` 对象。
2.  遍历 `FileResource` 的每一行。
3.  对每一行，使用 `WebLogParser.parseEntry` 方法将文本行转换为 `LogEntry` 对象。
4.  将该 `LogEntry` 对象添加到 `records` 字段（这是一个 `ArrayList`）中。

以下是代码示例：

```java
public void readFile(String filename) {
    FileResource fr = new FileResource(filename);
    for (String line : fr.lines()) {
        LogEntry entry = WebLogParser.parseEntry(line);
        records.add(entry);
    }
}
```

## 测试代码

编写完构造函数和 `readFile` 方法后，需要测试代码。课程提供了一个名为 `printAll` 的便捷方法，它将打印存储在实例变量 `records` 中的所有日志条目。该方法会利用 `LogEntry` 类的 `toString` 方法，将每个日志条目表示为字符串进行输出。

当一切运行正常后，就可以开始分析已读入的数据了。

## 总结

![](img/17b914ff24b7ca8b4f5fbc7453c5897b_1.png)

![](img/17b914ff24b7ca8b4f5fbc7453c5897b_2.png)

本节课中，我们一起学习了如何解析Web服务器日志文件。我们利用提供的 `WebLogParser` 工具将日志行转换为 `LogEntry` 对象，并成功构建了 `LogAnalyzer` 类的框架，包括初始化数据结构的构造函数和从文件读取数据并填充列表的 `readFile` 方法。这为后续进行实际的日志数据分析奠定了坚实的基础。