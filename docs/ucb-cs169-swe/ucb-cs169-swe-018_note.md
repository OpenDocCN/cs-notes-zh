# 软件工程：018：软件设计模式与SOLID原则

在本节课中，我们将要学习软件设计模式，特别是SOLID设计原则中的前两项：单一职责原则和开闭原则。我们将探讨如何利用这些模式和原则来构建更易于维护、扩展和理解的代码。

---

## 单一职责原则

上一节我们介绍了设计模式的基本概念，本节中我们来看看SOLID原则中的第一个，也是最重要的一个：单一职责原则。

单一职责原则规定，一个类应该只有一个引起它变化的原因。换句话说，一个类应该只负责一件事。这与我们之前讨论的函数级重构原则“只做一件事”一脉相承。

### 如何识别违反SRP的类

以下是识别一个类是否承担了过多职责的一些迹象：

*   **高内聚性缺失**：类中的方法彼此关联性不强，使用了不同的、不相关的实例变量集合。
*   **方法簇**：某些方法总是成组出现，并接收相同的参数集合（例如，总是同时传递 `street_name`、`house_number`、`zip_code`）。这暗示这些参数应该被提取成一个新的类。
*   **冗长的类**：类文件过长，包含了处理多个不同领域逻辑的方法。

### 如何遵循SRP

遵循SRP的核心方法是**提取更小的类**，直到每个类都只专注于做好一件事。

让我们通过一个具体例子来理解。假设我们有一个 `Customer` 类，它存储了客户的地址信息，并包含了许多处理地址逻辑的方法（如计算税率、格式化地址等）。这违反了SRP，因为 `Customer` 类同时处理了“客户”和“地址”两种职责。

![](img/3be1d71e56856fc469366fb9d362137b_1.png)

![](img/3be1d71e56856fc469366fb9d362137b_2.png)

**解决方案**：我们可以创建一个新的 `Address` 类。

```ruby
class Address
  attr_reader :customer

  def initialize(customer)
    @customer = customer
  end

  def zip_code
    customer.zip_code
  end

  def street
    customer.street
  end

  # 其他与地址相关的方法，如计算税率、格式化等
end
```

然后，在 `Customer` 类中，我们可以使用 Rails 的 `delegate` 方法将地址相关的属性委托给 `Address` 实例。

```ruby
class Customer < ApplicationRecord
  has_one :address

  delegate :zip_code, :street, to: :address
end
```

这样，`Customer` 类只负责客户的核心逻辑，而 `Address` 类专门处理所有与地址相关的逻辑。这使得代码更清晰，单元测试也更易于编写。

---

## 开闭原则

在理解了如何让类职责单一之后，我们来看看如何让类更容易扩展。这就是开闭原则。

![](img/3be1d71e56856fc469366fb9d362137b_4.png)

![](img/3be1d71e56856fc469366fb9d362137b_6.png)

开闭原则规定：**软件实体（类、模块、函数等）应该对扩展开放，但对修改关闭**。这意味着，当需要添加新功能时，我们应该通过添加新代码（扩展）来实现，而不是修改已有的、已经工作正常的代码。

### 违反开闭原则的迹象

一个典型的违反开闭原则的代码特征是使用了 `case` 语句或一连串的 `if-elsif` 条件判断，根据不同的类型来执行不同的行为。

例如，一个 `Report` 类根据格式输出报告：

```ruby
class Report
  def output_report(format)
    case format
    when :html
      # 生成HTML报告
    when :pdf
      # 生成PDF报告
    # 当需要添加JSON格式时，必须修改这里的case语句
    end
  end
end
```

每增加一种新的报告格式（如JSON），我们就必须修改 `output_report` 方法，这违反了“对修改关闭”的原则。

### 应用设计模式遵循开闭原则

为了解决这个问题，我们可以应用几种设计模式。

#### 1. 抽象工厂模式

我们可以使用元编程动态地根据传入的格式字符串来查找并实例化对应的格式化器类。

```ruby
class Report
  def output_report(format)
    formatter_class = "#{format.to_s.camelize}Formatter"
    formatter = Object.const_get(formatter_class).new
    formatter.output_report(self)
  rescue NameError
    raise "Unknown report format: #{format}"
  end
end
```

这样，要添加一个新的 `JsonFormatter`，我们只需要创建这个新类，而无需修改 `Report` 类本身。

#### 2. 模板方法模式

当一系列步骤相同，但每个步骤的具体实现不同时，可以使用模板方法模式。我们定义一个抽象基类来规定步骤，子类来实现具体步骤。

```ruby
class ReportFormatter
  def output_report(report)
    output_start
    output_title(report.title)
    output_body(report.body)
    output_end
  end

  # 这些方法由子类实现
  def output_start; end
  def output_title(title); end
  def output_body(body); end
  def output_end; end
end

class HtmlFormatter < ReportFormatter
  def output_title(title)
    puts "<h1>#{title}</h1>"
  end
  # ... 实现其他方法
end

class PdfFormatter < ReportFormatter
  def output_title(title)
    # 使用PDF生成库的代码
  end
  # ... 实现其他方法
end
```

#### 3. 策略模式

策略模式比模板方法模式更灵活。它将可互换的算法或行为封装成独立的类。`Report` 类不关心具体使用哪个格式化器，它只依赖一个通用的 `Formatter` 接口。

```ruby
class Report
  attr_reader :title, :body
  attr_accessor :formatter

  def initialize(formatter)
    @title = 'Monthly Report'
    @body = ['Things', 'are', 'going', 'well']
    @formatter = formatter
  end

  def output_report
    formatter.output_report(self)
  end
end

class HtmlFormatter
  def output_report(context)
    # 输出HTML
  end
end

class PdfFormatter
  def output_report(context)
    # 输出PDF
  end
end

# 使用方式
report = Report.new(HtmlFormatter.new)
report.output_report
```

#### 4. 装饰器模式

装饰器模式允许我们通过包装（装饰）对象来动态地添加新功能，而不是通过继承创建大量子类。这在需要组合多种特性时特别有用。

例如，一个基础的 `PdfFormatter`，我们可以用 `PdfWithPasswordFormatter` 来装饰它，为其添加密码功能，再用 `PdfWithWatermarkFormatter` 来装饰前者，添加水印功能。这样就得到了一个同时具有密码和水印的PDF格式化器，而无需创建 `PdfWithPasswordAndWatermarkFormatter` 这样的具体子类。

![](img/3be1d71e56856fc469366fb9d362137b_8.png)

```ruby
class PdfFormatter
  def output
    # 生成基础PDF
  end
end

![](img/3be1d71e56856fc469366fb9d362137b_10.png)

class PdfWithPasswordFormatter
  def initialize(pdf_formatter)
    @pdf_formatter = pdf_formatter
  end

  def output
    pdf = @pdf_formatter.output
    add_password(pdf)
    pdf
  end

  def add_password(pdf)
    # 添加密码逻辑
  end
end

![](img/3be1d71e56856fc469366fb9d362137b_12.png)

# 组合使用
basic_pdf = PdfFormatter.new
secure_pdf = PdfWithPasswordFormatter.new(basic_pdf)
secure_pdf.output # 输出带密码的PDF
```

Rails 中的**作用域**是装饰器模式的一个绝佳例子。你可以链式调用多个作用域来组合复杂的查询，而无需为每种组合都定义一个单独的方法。

---

## 高级Cucumber/Capybara技巧

在掌握了核心设计原则后，让我们看一些能提升测试效率的实用工具。

![](img/3be1d71e56856fc469366fb9d362137b_14.png)

![](img/3be1d71e56856fc469366fb9d362137b_15.png)

以下是几个有用的技巧：

*   **`launchy` Gem**：这个gem可以在运行Cucumber步骤时自动打开浏览器，让你实时观察测试执行过程，对于调试非常有用。它提供了 `save_and_open_page` 方法。
*   **Capybara Cheat Sheet**：网上有很好的Capybara命令速查表，Piazza上也有链接，可以帮助你快速查找定位元素、填写表单等方法。
*   **`page` 对象**：在Capybara中，`page` 对象是你与浏览器交互的主要接口。你可以通过它执行自定义的JavaScript或CSS，这在测试复杂的前端交互时很有用。
*   **处理表格数据**：Cucumber提供了处理表格数据的便捷语法，可以让你在场景中直接使用结构化的数据。
*   **步骤间传递状态**：使用实例变量可以在不同的Cucumber步骤之间共享状态。
*   **使用 `Timecop`**：如果你的应用与日期时间相关（如截止日期、上映时间），`Timecop` gem可以“冻结”或“旅行”到特定时间，使时间相关的测试变得简单可靠。
*   **使用标签**：可以为不同的场景打上标签，以便只运行特定的测试集。

---

## 总结

![](img/3be1d71e56856fc469366fb9d362137b_17.png)

![](img/3be1d71e56856fc469366fb9d362137b_19.png)

本节课中我们一起学习了软件设计的基础——SOLID原则的前两项。我们深入探讨了**单一职责原则**，它要求一个类只做一件事，并通过提取小类来达成这一目标。接着，我们学习了**开闭原则**，它要求代码应对扩展开放，对修改关闭，并介绍了**抽象工厂**、**模板方法**、**策略**和**装饰器**等设计模式来帮助我们实现这一原则。最后，我们了解了一些能提升端到端测试效率的Cucumber和Capybara高级技巧。掌握这些原则和模式，将帮助你构建出更健壮、更灵活、更易于维护的软件系统。