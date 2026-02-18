# 28：XML 查询与 XSLT 实践教程 📘

![](img/efd01bb0d4d6e4eea8c18808748a281d_1.png)

在本节课中，我们将学习如何使用 XPath、XQuery 和 XSLT 对 XML 数据进行查询与转换。我们将通过两个数据集（课程目录和世界各国）的练习题，掌握这些技术的核心语法和应用场景。

![](img/efd01bb0d4d6e4eea8c18808748a281d_3.png)

---

![](img/efd01bb0d4d6e4eea8c18808748a281d_5.png)

## 🗂️ 概述与数据集介绍

![](img/efd01bb0d4d6e4eea8c18808748a281d_7.png)

首先，我们需要了解我们将要使用的两个 XML 数据集的结构。

**课程目录数据集 (`courses.xml`)** 的根元素是 `<catalog>`，其下包含 `<department>` 元素。每个 `<department>` 下又有多个 `<course>` 元素。课程信息包括编号（`@number` 属性）、标题（`<title>`）、描述（`<description>`）、注册人数（`<enrollment>`）和讲师（`<instructors>`）等。

**世界各国数据集 (`countries.xml`)** 的根元素是 `<mondial>`，其下包含多个 `<country>` 元素。每个国家有名称（`@name`）、人口（`@population`）、面积（`@area`）等属性，并可能包含 `<language>` 和 `<city>` 子元素。

![](img/efd01bb0d4d6e4eea8c18808748a281d_9.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_11.png)

理解数据结构是编写正确查询的第一步。接下来，我们将开始具体的练习。

![](img/efd01bb0d4d6e4eea8c18808748a281d_13.png)

---

## 🔍 第一部分：XPath 与 XQuery 练习

![](img/efd01bb0d4d6e4eea8c18808748a281d_15.png)

上一节我们介绍了数据集的结构，本节中我们来看看如何使用 XPath 和 XQuery 进行查询。

### 练习 1：查找跨列课程

![](img/efd01bb0d4d6e4eea8c18808748a281d_17.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_18.png)

**目标**：返回描述中包含 “cross-listed as Ling 180” 的课程编号。

![](img/efd01bb0d4d6e4eea8c18808748a281d_19.png)

我们需要定位到 `<course>` 元素，并筛选其 `<description>` 中的文本。课程编号存储在 `@number` 属性中。

**XPath 查询**：
```xpath
//course[contains(description, "cross-listed as Ling 180")]/data(@number)
```
**解释**：
*   `//course`：选择文档中所有 `<course>` 元素。
*   `[contains(description, “...”)]`：筛选条件，要求 `<description>` 元素包含指定文本。
*   `/data(@number)`：从筛选后的课程中提取 `@number` 属性的值。

此查询将返回 **CS124**。

![](img/efd01bb0d4d6e4eea8c18808748a281d_21.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_23.png)

---

![](img/efd01bb0d4d6e4eea8c18808748a281d_25.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_27.png)

### 练习 2：查找特定讲师教授的课程

![](img/efd01bb0d4d6e4eea8c18808748a281d_29.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_31.png)

**目标**：返回由名字是 “Daphne” 或 “Julie” 的讲师教授的课程编号。

![](img/efd01bb0d4d6e4eea8c18808748a281d_33.png)

我们需要在 `<course>` 元素内，检查 `<instructors>` 下的子元素（可能是 `<lecturer>` 或 `<professor>`）的 `<first_name>`。

![](img/efd01bb0d4d6e4eea8c18808748a281d_34.png)

**XPath 查询**：
```xpath
//course[instructors/*[first_name="Daphne" or first_name="Julie"]]/data(@number)
```
**解释**：
*   `instructors/*`：使用通配符 `*` 匹配 `<instructors>` 下的任何直接子元素（即讲师或教授）。
*   `[first_name=“Daphne” or first_name=“Julie”]`：筛选条件，要求名字匹配。
*   最终返回满足条件的课程的编号，例如 **CS107** 和 **CS228**。

---

### 练习 3：查找同时拥有讲师和教授的课程

![](img/efd01bb0d4d6e4eea8c18808748a281d_36.png)

**目标**：返回同时拥有 `<lecturer>` 和 `<professor>` 作为讲师的课程标题，且每个标题只出现一次。

![](img/efd01bb0d4d6e4eea8c18808748a281d_38.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_40.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_41.png)

这个查询更适合用 XQuery 表达，因为它涉及对元素集合的迭代和条件判断。

**XQuery 查询**：
```xquery
for $c in doc(“courses.xml”)//course
where $c/instructors/lecturer and $c/instructors/professor
return $c/title
```
**解释**：
*   `for $c in …`：遍历每一个 `<course>` 元素。
*   `where …`：条件为课程下同时存在 `<instructors/lecturer>` 和 `<instructors/professor>` 路径。
*   `return $c/title`：返回满足条件的课程的 `<title>` 元素内容。

此查询将返回 **Programming Methodology** 和 **Programming Abstractions**。

---

## 🌍 第二部分：世界各国数据集查询

完成了课程目录的练习，我们接下来看看更复杂的国家数据查询。

![](img/efd01bb0d4d6e4eea8c18808748a281d_43.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_44.png)

### 练习 11：查找符合特定条件的国家

![](img/efd01bb0d4d6e4eea8c18808748a281d_46.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_47.png)

**目标**：返回所有没有语言或城市数据，但人口超过 1000 万的国家的名称。

![](img/efd01bb0d4d6e4eea8c18808748a281d_49.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_50.png)

我们需要使用 `count()` 函数来检查子元素的数量，并结合属性值进行筛选。

![](img/efd01bb0d4d6e4eea8c18808748a281d_52.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_54.png)

**XPath 查询**：
```xpath
//country[count(language)=0 and count(city)=0 and @population > 10000000]/data(@name)
```
**解释**：
*   `count(language)=0`：确保 `<country>` 下没有 `<language>` 子元素。
*   `count(city)=0`：确保没有 `<city>` 子元素。
*   `@population > 10000000`：确保人口属性值大于一千万。
*   最终返回满足所有条件的国家的 `@name` 属性值。

![](img/efd01bb0d4d6e4eea8c18808748a281d_56.png)

---

![](img/efd01bb0d4d6e4eea8c18808748a281d_57.png)

### 练习 12：查找拥有最大城市的国家

**目标**：返回拥有所有城市中人口最多的城市所在国家的名称。

![](img/efd01bb0d4d6e4eea8c18808748a281d_59.png)

这是一个复杂的查询，需要比较所有城市的人口。我们需要使用 XQuery 的 `every` 量词进行遍历比较，并注意将人口数据转换为整数类型。

![](img/efd01bb0d4d6e4eea8c18808748a281d_61.png)

**XQuery 查询**：
```xquery
for $c in doc(“countries.xml”)//country
for $city in $c/city
where every $city2 in doc(“countries.xml”)//city
satisfies xs:integer($city2/@population) <= xs:integer($city/@population)
return $c/data(@name)
```
**解释**：
*   使用两层循环：外层遍历国家 `$c`，内层遍历该国的每个城市 `$city`。
*   `where every … satisfies …`：核心条件。它检查对于数据集中的每一个其他城市 `$city2`，其人口是否都小于或等于当前城市 `$city` 的人口。如果成立，则 `$city` 就是人口最多的城市。
*   `xs:integer(…)`：将 `@population` 属性值显式转换为整数，以确保进行数值比较而非字符串比较。
*   最终返回该城市所属国家的名称。正确结果是 **South Korea**。

![](img/efd01bb0d4d6e4eea8c18808748a281d_63.png)

---

![](img/efd01bb0d4d6e4eea8c18808748a281d_65.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_67.png)

## 🛠️ 第三部分：XSLT 转换练习

上一节我们使用 XPath 和 XQuery 进行查询，本节我们将学习如何使用 XSLT 对 XML 文档进行转换。

![](img/efd01bb0d4d6e4eea8c18808748a281d_69.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_71.png)

### 练习 1：筛选并保留课程结构

![](img/efd01bb0d4d6e4eea8c18808748a281d_72.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_73.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_75.png)

**目标**：返回所有注册人数大于 500 的课程，并保留其完整的原始 XML 结构。

XSLT 通过模板匹配和复制来实现。我们需要一个模板来匹配目标课程，另一个模板来阻止无关文本的输出。

![](img/efd01bb0d4d6e4eea8c18808748a281d_77.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_78.png)

**XSLT 样式表**：
```xml
<xsl:stylesheet version=“1.0” xmlns:xsl=“http://www.w3.org/1999/XSL/Transform”>
    <!-- 匹配并复制注册人数大于500的课程 -->
    <xsl:template match=“course[enrollment > 500]”>
        <xsl:copy-of select=“.”/>
    </xsl:template>
    <!-- 匹配文本节点但不输出，防止无关文本泄露 -->
    <xsl:template match=“text()”/>
</xsl:stylesheet>
```
**解释**：
*   第一个模板匹配 `enrollment > 500` 的 `<course>` 元素，并使用 `<xsl:copy-of select=“.”/>` 将其完整复制到输出。
*   第二个模板 `match=“text()”` 匹配所有文本节点，但不产生任何输出，这可以防止未被显式处理的文本出现在结果中。

---

### 练习 2：从数据中删除特定课程

![](img/efd01bb0d4d6e4eea8c18808748a281d_80.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_82.png)

**目标**：从课程目录中删除所有注册人数大于 60 或没有列出注册人数的课程，并保持其他结构不变。

![](img/efd01bb0d4d6e4eea8c18808748a281d_84.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_86.png)

思路是使用一个“通配”模板复制整个文档结构，然后为需要删除的元素创建一个“空”模板。

![](img/efd01bb0d4d6e4eea8c18808748a281d_88.png)

**XSLT 样式表**：
```xml
<xsl:stylesheet version=“1.0” xmlns:xsl=“http://www.w3.org/1999/XSL/Transform”>
    <!-- 通配模板，复制所有元素和属性并继续处理其子节点 -->
    <xsl:template match=“@*|node()”>
        <xsl:copy>
            <xsl:apply-templates select=“@*|node()”/>
        </xsl:copy>
    </xsl:template>
    <!-- 匹配需要删除的课程：注册人数>60 或 无注册人数元素 -->
    <xsl:template match=“course[enrollment > 60 or not(enrollment)]”/>
</xsl:stylesheet>
```
**解释**：
*   `match=“@*|node()”`：这是一个强大的模板，匹配所有属性(`@*`)和所有类型的节点(`node()``)。它通过 `<xsl:copy>` 和 `<xsl:apply-templates>` 递归地复制整个文档的骨架。
*   `match=“course[enrollment > 60 or not(enrollment)]”`：这个模板匹配需要删除的课程。模板体为空，意味着这些元素不会被复制到输出结果中，从而实现了“删除”。

![](img/efd01bb0d4d6e4eea8c18808748a281d_90.png)

---

![](img/efd01bb0d4d6e4eea8c18808748a281d_92.png)

### 练习 3：从国家数据中删除特定国家

![](img/efd01bb0d4d6e4eea8c18808748a281d_94.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_96.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_98.png)

**目标**：从世界各国数据中删除所有面积大于 40,000 或没有列出城市的国家。

![](img/efd01bb0d4d6e4eea8c18808748a281d_100.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_101.png)

此练习与上一个 XSLT 练习模式完全相同，只是匹配条件换成了国家数据集的属性。

![](img/efd01bb0d4d6e4eea8c18808748a281d_103.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_105.png)

**XSLT 样式表**：
```xml
<xsl:stylesheet version=“1.0” xmlns:xsl=“http://www.w3.org/1999/XSL/Transform”>
    <xsl:template match=“@*|node()”>
        <xsl:copy>
            <xsl:apply-templates select=“@*|node()”/>
        </xsl:copy>
    </xsl:template>
    <!-- 匹配需要删除的国家：面积>40000 或 无城市数据 -->
    <xsl:template match=“country[@area > 40000 or count(city)=0]”/>
</xsl:stylesheet>
```
**解释**：
*   逻辑与练习2完全一致。通配模板负责维持文档结构。
*   第二个模板匹配需要删除的 `<country>` 元素：`@area > 40000` 或 `count(city)=0`。空模板确保这些国家不会出现在最终输出里。

![](img/efd01bb0d4d6e4eea8c18808748a281d_107.png)

---

![](img/efd01bb0d4d6e4eea8c18808748a281d_109.png)

## 📝 总结

![](img/efd01bb0d4d6e4eea8c18808748a281d_111.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_113.png)

本节课中我们一起学习了 XML 数据处理的三种核心技术：
1.  **XPath**：用于在 XML 文档中导航和定位节点，非常适合简单的条件筛选和值提取。
2.  **XQuery**：功能更强大的查询语言，支持变量、循环（FLWOR 表达式）和复杂条件判断，适合完成需要遍历和比较的数据查询任务。
3.  **XSLT**：一种转换语言，用于将 XML 文档转换为其他格式（如另一个 XML、HTML 或文本）。其核心思想是模板匹配，通过定义不同的模板规则来重组、筛选或修改原始数据。

![](img/efd01bb0d4d6e4eea8c18808748a281d_114.png)

![](img/efd01bb0d4d6e4eea8c18808748a281d_116.png)

通过针对课程目录和世界各国数据集的实践练习，我们掌握了如何根据不同的需求选择合适的工具，并编写出正确的查询与转换语句。记住，理解 XML 文档的层次结构是成功编写任何查询的第一步。