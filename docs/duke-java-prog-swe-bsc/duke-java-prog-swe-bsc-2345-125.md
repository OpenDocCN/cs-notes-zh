# Java编程和软件工程基础：2-5：编写震级过滤器

![](img/d2120059f5136543bb0ee5f35b6b1ce3_0.png)

在本节课中，我们将学习如何使用Java处理和筛选地震数据。我们将从一个现有的地震客户端类开始，学习如何读取和打印地震数据，并最终编写一个方法来筛选出震级大于特定值的地震。

我们将使用CSV格式的数据，这些数据可以来自实时的美国地质调查局数据源，也可以来自本地文件。通过编写筛选逻辑，你将获得处理和分析任何类型数据的通用技能。

![](img/d2120059f5136543bb0ee5f35b6b1ce3_2.png)

## 读取并打印地震数据

首先，我们使用现有的 `createCSV` 方法来处理数据。这个方法可以从文件或网络链接读取地震数据，并将其以CSV格式打印出来。CSV格式便于你将数据复制到电子表格中进行查看和调试。

以下是读取数据并打印的基本代码结构：

```java
EarthquakeClient client = new EarthquakeClient();
client.createCSV();
```

运行此代码后，控制台会输出CSV格式的地震数据。例如，从我们的示例文件中读取了1518次地震的信息。

## 筛选“大地震”

上一节我们介绍了如何读取和打印原始数据。本节中，我们来看看如何从中筛选出震级较大的地震。

我们的目标是编写一个名为 `bigQuakes` 的方法，它能找出所有震级大于5.0的地震。

以下是实现此功能的初步代码：

```java
public void bigQuakes() {
    EarthQuakeParser parser = new EarthQuakeParser();
    String source = "data/nov20quakedatasmall.atom";
    ArrayList<QuakeEntry> list = parser.read(source);
    System.out.println("read data for " + list.size() + " quakes");

    for (QuakeEntry qe : list) {
        if (qe.getMagnitude() > 5.0) {
            System.out.println(qe);
        }
    }
}
```

在这段代码中，我们遍历了地震条目列表，并使用 `getMagnitude()` 方法获取每个地震的震级。如果震级大于5.0，我们就将其打印出来。

## 创建通用的震级过滤器

虽然上述方法有效，但为了代码的复用性和灵活性，我们可以创建一个更通用的筛选方法。

以下是创建一个名为 `filterByMagnitude` 的通用筛选方法的步骤。该方法接收一个地震列表和一个最小震级值作为参数，并返回一个包含所有符合条件地震的新列表。

```java
public ArrayList<QuakeEntry> filterByMagnitude(ArrayList<QuakeEntry> quakeData, double magMin) {
    ArrayList<QuakeEntry> answer = new ArrayList<QuakeEntry>();
    for (QuakeEntry qe : quakeData) {
        if (qe.getMagnitude() > magMin) {
            answer.add(qe);
        }
    }
    return answer;
}
```

## 在 `bigQuakes` 方法中使用过滤器

现在，我们可以在 `bigQuakes` 方法中调用这个新编写的通用过滤器，而不是直接在里面编写筛选逻辑。

以下是更新后的 `bigQuakes` 方法：

```java
public void bigQuakes() {
    EarthQuakeParser parser = new EarthQuakeParser();
    String source = "data/nov20quakedatasmall.atom";
    ArrayList<QuakeEntry> list = parser.read(source);
    System.out.println("read data for " + list.size() + " quakes");

    // 使用通用过滤器
    ArrayList<QuakeEntry> listBig = filterByMagnitude(list, 5.0);
    for (QuakeEntry qe : listBig) {
        System.out.println(qe);
    }
}
```

![](img/d2120059f5136543bb0ee5f35b6b1ce3_4.png)

运行此方法，你将得到与之前相同的结果：所有震级大于5.0的地震列表。我们利用了 `QuakeEntry` 类的 `toString` 方法，使输出格式清晰易读。

## 总结

本节课中我们一起学习了如何用Java处理地震数据。我们从读取和打印CSV格式的数据开始，然后编写了直接筛选“大地震”的代码。为了提高代码质量，我们进一步创建了一个通用的 `filterByMagnitude` 方法，它可以根据任意给定的最小震级来筛选数据。最后，我们重构了 `bigQuakes` 方法来使用这个通用过滤器。这些筛选和遍历数据的技巧，可以广泛应用于其他类型的数据处理任务中。