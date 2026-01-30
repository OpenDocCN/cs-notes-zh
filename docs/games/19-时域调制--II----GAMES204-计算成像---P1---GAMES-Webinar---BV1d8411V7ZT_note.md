![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_1.png)

# 19.时域调制 (II) ｜ GAMES204-计算成像 - P1 - GAMES-Webinar - BV1d8411V7ZT

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_3.png)

## 概述

在本节课中，我们将学习非视域成像技术，这是一种能够捕捉隐藏在障碍物后面的物体图像的技术。我们将探讨非视域成像的原理、挑战和实现方法。

## 非视域成像概述

非视域成像，也称为“绕过角落看”成像，是一种能够捕捉隐藏在障碍物后面的物体图像的技术。它通过分析光在物体和障碍物之间的传播路径来实现。

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_5.png)

## 非视域成像的挑战

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_7.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_9.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_11.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_13.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_15.png)

非视域成像面临着以下挑战：

* **信号微弱**：由于多次反射和散射，到达传感器的光子数非常少，导致信号微弱。
* **逆问题**：需要从复杂的信号中恢复出隐藏物体的三维结构，这是一个高度非线性的逆问题。
* **数据量庞大**：需要处理大量的数据，这给计算带来了巨大的挑战。

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_17.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_19.png)

## 非视域成像的实现方法

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_21.png)

### 1. 传统方法

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_23.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_25.png)

传统的非视域成像方法包括：

* **基于扫描的方法**：通过扫描激光束和相机来获取图像。
* **基于投影的方法**：通过投影图像并分析反射光来获取图像。

### 2. 共聚焦非视域成像

共聚焦非视域成像通过将测量点与激光点重合来简化问题。这种方法将五维问题简化为三维问题，并提高了成像效率。

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_27.png)

### 3. 频率-波数迁移

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_29.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_31.png)

频率-波数迁移是一种将信号从频率域迁移到波数域的方法。这种方法可以有效地去除噪声并提高成像质量。

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_33.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_35.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_37.png)

## 实验结果

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_39.png)

实验结果表明，非视域成像技术可以有效地捕捉隐藏在障碍物后面的物体图像。

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_41.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_43.png)

## 总结

本节课介绍了非视域成像技术，探讨了其原理、挑战和实现方法。非视域成像技术具有广阔的应用前景，例如在医疗、安全和机器人领域。

## 代码示例

以下是一个简单的非视域成像代码示例：

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_45.png)

```python
import numpy as np

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_47.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_49.png)

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_51.png)

def non_visual_imaging(data):
  """
  非视域成像

  Args:
    data: 输入数据

  Returns:
    成像结果
  """

  # ... 处理数据 ...

  return image
```

## 参考资料

![](img/a90f0abe78d74cf5f8c1d0a03ca886cf_53.png)

* [非视域成像技术综述](https://www.google.com/search?q=non-visual+imaging+technology+review)
* [共聚焦非视域成像](https://www.google.com/search?q=confocal+non-visual+imaging)
* [频率-波数迁移](https://www.google.com/search?q=frequency-wavenumber+migration)