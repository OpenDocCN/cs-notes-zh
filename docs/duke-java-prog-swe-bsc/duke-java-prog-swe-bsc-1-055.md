# Java编程和软件工程基础：2-5：在多日数据中寻找最高温度 🌡️

![](img/102a88a76704a9c3b663259519cd6a5c_0.png)

在本节课中，我们将学习如何扩展之前的功能，从分析单日数据扩展到分析多日数据，并找出指定日期范围内的最高温度。我们将创建一个新的方法，并利用目录资源来批量处理多个文件。

## 概述

上一节我们介绍了如何在单个CSV文件中找到最高温度。本节中，我们来看看如何遍历多天的数据文件，找出这些天中的最高温度记录。我们将使用目录资源来选择多个文件，并循环处理每个文件。

![](img/102a88a76704a9c3b663259519cd6a5c_2.png)

## 实现 `hottestInManyDays` 方法

为了实现这个功能，我创建了一个名为 `hottestInManyDays` 的新方法。这个方法将使用目录资源，允许我们一次性选择并比较任意数量的文件。

以下是实现该方法的步骤：

![](img/102a88a76704a9c3b663259519cd6a5c_4.png)

1.  **创建文件资源**：首先，我们通过目录资源获取选中的文件列表，并遍历这个列表。
    ```java
    DirectoryResource dr = new DirectoryResource();
    for (File f : dr.selectedFiles()) {
        // 处理每个文件
    }
    ```

![](img/102a88a76704a9c3b663259519cd6a5c_6.png)

![](img/102a88a76704a9c3b663259519cd6a5c_7.png)

2.  **处理单个文件**：对于列表中的每一个文件，我们将其转换为文件资源，然后调用上一节中创建的 `hottestHourInFile` 方法来获取该文件中的最高温度记录。
    ```java
    FileResource fr = new FileResource(f);
    CSVRecord currentRow = hottestHourInFile(fr.getCSVParser());
    ```
    这与我们之前在测试中编写的代码完全相同，但现在我们将它放在一个循环中，以便可以按需处理任意数量的文件。

3.  **比较并更新最高记录**：与之前的例子类似，我们需要追踪目前找到的最高温度记录。为此，我们创建一个 `CSVRecord` 类型的变量 `largestSoFar`，并初始化为 `null`。
    ```java
    CSVRecord largestSoFar = null;
    ```
    在循环内部，我们将检查 `largestSoFar` 是否为空（即是否还未被赋值）。如果是，则直接将当前记录赋值给它。
    ```java
    if (largestSoFar == null) {
        largestSoFar = currentRow;
    }
    ```
    否则，我们需要比较当前记录的温度与目前最高记录的温度。

![](img/102a88a76704a9c3b663259519cd6a5c_9.png)

4.  **温度比较逻辑**：这段比较代码与之前非常相似。我们将从当前记录和 `largestSoFar` 记录中分别提取温度值，并进行比较。
    ```java
    else {
        double currentTemp = Double.parseDouble(currentRow.get("TemperatureF"));
        double largestTemp = Double.parseDouble(largestSoFar.get("TemperatureF"));
        if (currentTemp > largestTemp) {
            largestSoFar = currentRow;
        }
    }
    ```

![](img/102a88a76704a9c3b663259519cd6a5c_11.png)

5.  **返回结果**：循环结束后，`largestSoFar` 变量中存储的就是多日数据中的最高温度记录，我们将其返回。
    ```java
    return largestSoFar;
    ```

![](img/102a88a76704a9c3b663259519cd6a5c_13.png)

## 测试方法

编写完代码后，我编译了程序以确保没有语法错误。接着，我创建了一个测试方法来验证其功能。

![](img/102a88a76704a9c3b663259519cd6a5c_15.png)

1.  **创建测试**：我创建了一个名为 `testHottestInManyDays` 的测试方法。在这个方法中，我调用了 `hottestInManyDays` 方法，它不需要参数，但会返回一个 `CSVRecord` 对象。
    ```java
    public void testHottestInManyDays() {
        CSVRecord largest = hottestInManyDays();
        System.out.println("hottest temperature was " + largest.get("TemperatureF") +
                           " at " + largest.get("DateUTC"));
    }
    ```
    我打印出最高温度及其发生的日期（这里使用 `DateUTC` 字段，因为可能涉及不同天数）。

2.  **小规模测试**：为了初步验证，我选择了2015年的头两天数据进行测试。根据已知结果，1月1日的最高温度是51.1度，1月2日是54度。因此，我期望程序的输出是54度，发生在1月2日。运行测试后，结果符合预期。

![](img/102a88a76704a9c3b663259519cd6a5c_17.png)

![](img/102a88a76704a9c3b663259519cd6a5c_18.png)

3.  **大规模测试**：在有了初步信心后，我进行了更大规模的数据集测试。我尝试处理2014年全年的数据（这是我们拥有完整数据的最后一年）。程序运行后，结果显示最高温度为98.1度，发生在7月8日晚上10点51分。

通过先在小样本（两天）上测试成功，再扩展到大规模数据集（全年），我确信代码能够正确工作。这种从小到大的测试方法，使得验证大规模数据处理的正确性成为可能，而无需手动检查海量数据。

![](img/102a88a76704a9c3b663259519cd6a5c_20.png)

![](img/102a88a76704a9c3b663259519cd6a5c_21.png)

## 总结

本节课中，我们一起学习了如何扩展单日最高温度查找功能，使其能够处理多日数据。我们创建了 `hottestInManyDays` 方法，利用循环和目录资源遍历多个文件，并通过比较逻辑持续更新找到的最高温度记录。最后，我们通过从两天到全年的分层测试，验证了代码的正确性。