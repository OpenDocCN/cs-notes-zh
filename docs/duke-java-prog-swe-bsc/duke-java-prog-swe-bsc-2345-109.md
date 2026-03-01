# 109：从算法到代码实现 🧑‍💻

![](img/ec5c47247d6f97827c88bb9912a2cef1_0.png)

在本节课中，我们将学习如何将之前设计的、用于统计网络服务器日志中唯一IP地址数量的算法，转化为实际的Java代码。我们将遵循伪代码的步骤，逐步构建方法，并进行测试以确保其正确性。

---

## 算法回顾与代码框架

上一节我们介绍了统计唯一IP地址的算法。本节中，我们来看看如何将其转换为Java代码。我们从一个方法框架开始，其中包含了之前开发的伪代码。

```java
public int countUniqueIPs() {
    // 伪代码步骤将在此转换为实际代码
}
```

## 初始化数据结构

首先，我们需要创建一个列表来存储已发现的唯一IP地址。我们将使用一个`ArrayList`，并初始化为空列表。

```java
ArrayList<String> uniqueIPs = new ArrayList<String>();
```

## 遍历日志记录

接下来，我们需要遍历`records`列表中的每一条日志条目。`records`是我们类中的一个实例变量。我们将使用`for-each`循环来完成这个任务。

```java
for (LogEntry le : records) {
    // 处理每条日志
}
```

## 提取并检查IP地址

在循环体内，我们需要从每条日志条目中提取IP地址，并检查它是否已经存在于我们的`uniqueIPs`列表中。

以下是处理每条日志的具体步骤：
1.  从日志条目`le`中获取IP地址。
2.  检查该IP地址是否**不在**`uniqueIPs`列表中。
3.  如果不在，则将其添加到列表中。

```java
String ipAddr = le.getIpAddress();
if (!uniqueIPs.contains(ipAddr)) {
    uniqueIPs.add(ipAddr);
}
```

## 返回结果

![](img/ec5c47247d6f97827c88bb9912a2cef1_2.png)

当所有日志条目处理完毕后，`uniqueIPs`列表的大小就是唯一IP地址的数量。我们需要返回这个值。

```java
return uniqueIPs.size();
```

## 整合完整代码

现在，让我们将所有部分整合到一起，并调整代码格式以确保清晰可读。

```java
public int countUniqueIPs() {
    ArrayList<String> uniqueIPs = new ArrayList<String>();
    for (LogEntry le : records) {
        String ipAddr = le.getIpAddress();
        if (!uniqueIPs.contains(ipAddr)) {
            uniqueIPs.add(ipAddr);
        }
    }
    return uniqueIPs.size();
}
```

## 编译与测试

代码编写完成后，首要步骤是编译它，以确保没有语法错误。编译成功后，我们需要通过测试来验证其逻辑是否正确。

![](img/ec5c47247d6f97827c88bb9912a2cef1_4.png)

![](img/ec5c47247d6f97827c88bb9912a2cef1_5.png)

我们已准备了一个测试类`UniqueIPTester`。它会执行以下操作：
1.  创建一个`LogAnalyzer`对象。
2.  读取一个简短的测试日志文件（`short-test-log`）。
3.  调用刚编写的`countUniqueIPs`方法。
4.  打印出统计到的唯一IP地址数量。

![](img/ec5c47247d6f97827c88bb9912a2cef1_6.png)

测试日志文件包含多个IP地址，其中一些是重复的。根据设计，我们预期该方法能正确识别并统计出唯一的IP地址数量。

运行测试后，控制台输出了预期的结果，这增加了我们对代码正确性的信心。

---

![](img/ec5c47247d6f97827c88bb9912a2cef1_8.png)

本节课中我们一起学习了如何将伪代码算法系统地转化为可运行的Java代码。我们经历了从初始化数据结构、遍历集合、使用条件逻辑进行判断，到最终返回结果的完整流程，并通过测试验证了代码的功能。这个过程是软件开发中从设计到实现的关键一步。