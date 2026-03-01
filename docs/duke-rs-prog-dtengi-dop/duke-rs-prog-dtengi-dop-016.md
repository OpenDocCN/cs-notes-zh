# 016：哈希映射语言对比演示

![](img/2834a61bd92caf009d4d754b6b482907_0.png)

## 概述
在本节课中，我们将学习如何使用Rust的哈希映射（HashMap）来创建一个自定义的编程语言权重计算器。这个例子非常适合数据科学家或数据工程师，他们经常需要创建自定义指标，这些指标可以输入到仪表板或数据库中。我们将通过计算编程语言的活跃年限来为其分配权重，从而展示Rust在数据处理方面的简洁性和高效性。

---

## 创建语言哈希映射
首先，我们创建一个名为 `knit_languages` 的函数。在这个函数内部，我们初始化一个可变的哈希映射。这个映射将编程语言名称（字符串）与其首次出现的年份（i32整数）关联起来。

以下是该函数的代码实现：

```rust
fn knit_languages() -> HashMap<String, i32> {
    let mut languages = HashMap::new();
    languages.insert("JavaScript".to_string(), 1995);
    languages.insert("HTML".to_string(), 1993);
    languages.insert("Python".to_string(), 1991);
    languages.insert("SQL".to_string(), 1974);
    languages.insert("TypeScript".to_string(), 2012);
    languages.insert("Bash".to_string(), 1989);
    languages.insert("Java".to_string(), 1995);
    languages.insert("C#".to_string(), 2000);
    languages.insert("R".to_string(), 1993);
    languages.insert("C++".to_string(), 1985);
    languages.insert("C".to_string(), 1972);
    languages.insert("Rust".to_string(), 2010);
    languages
}
```

---

## 计算语言权重
上一节我们创建了包含语言和年份的映射，本节中我们来看看如何根据语言的活跃年限计算其权重。

我们创建一个名为 `calculate_weights` 的函数。它接收语言的哈希映射作为参数，并根据每种语言的“年龄”（当前年份减去其诞生年份）计算一个从1到100的权重值。最新的语言权重为1，最古老的语言权重为100。

以下是权重计算的逻辑：

```rust
fn calculate_weights(languages: HashMap<String, i32>) -> HashMap<String, i32> {
    let current_year = 2023; // 假设当前年份
    let mut weighted_languages = HashMap::new();

    for (lang, year) in languages {
        let age = current_year - year;
        // 将年龄映射到1-100的区间，这里使用简化线性映射
        // 注意：实际映射逻辑可能需要根据最大和最小年龄调整
        let weight = (age as f32 / 100.0 * 99.0 + 1.0) as i32;
        weighted_languages.insert(lang, weight);
    }
    weighted_languages
}
```

---

## 运行与结果分析
现在，我们将两个函数结合起来，运行程序并查看结果。

在主函数中，我们首先调用 `knit_languages` 获取基础数据，然后将其传递给 `calculate_weights` 函数进行计算。最后，我们打印出带权重的语言列表。

运行程序（`cargo run`）后，我们可以看到类似以下的输出：

```
TypeScript: 1
Rust: 2
C#: 30
Java: 28
JavaScript: 28
Python: 32
HTML: 30
Bash: 34
R: 30
C++: 38
SQL: 49
C: 51
```

根据这个权重排名（1代表最新，100代表最古老），我们可以得出一些观察：
*   TypeScript和Rust是相对较新的语言。
*   C语言是最古老的语言之一。
*   这种排名方式为技术选型提供了另一个维度：追求稳定可选择Python等历史悠久的语言；从事前沿项目可考虑Rust或TypeScript；而像C#这样排名居中的语言则是一个折中的选择。

---

![](img/2834a61bd92caf009d4d754b6b482907_2.png)

![](img/2834a61bd92caf009d4d754b6b482907_3.png)

## 总结
本节课中我们一起学习了如何利用Rust的哈希映射进行数据处理。我们创建了一个编程语言年限与权重的映射，并演示了如何根据自定义逻辑（活跃年限）计算和排序数据。这个例子虽然简单，但清晰地展示了Rust在构建高效、自定义数据管道方面的能力，这正是数据工程和DevOps工作中的常见任务。得益于Rust的编译特性和高效的哈希映射实现，此类计算性能表现卓越。