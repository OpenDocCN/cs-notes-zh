# 05：处理图像数据

在本节课中，我们将学习如何对图像数据进行基本操作，包括算术运算、数据类型转换、色彩空间转换、几何变换以及如何保存处理结果。

图像以数字矩阵的形式存储。这意味着处理图像数据与处理其他矩阵和数组类似。例如，裁剪灰度图像等同于访问矩阵的一个子集。然而，需要注意大多数图像的数据类型是 `uint8`。这种类型占用内存较少，但如果不小心处理，可能会导致一些意想不到的错误。

## 算术运算与数据类型转换

上一节我们提到了图像作为矩阵的本质，本节中我们来看看对图像进行算术运算时需要注意的关键问题。一个常见的图像处理任务是将多张图像进行平均，这通常可以提高信噪比。让我们通过平均这些猎户座星云的图像来练习处理图像数据。

要创建平均图像，只需将图像相加，然后除以图像总数。

![](img/58010d1f4a1aa92203ec59ce015ade4b_1.png)

```matlab
average_image = (image1 + image2 + image3 + image4 + image5) / 5;
```

![](img/58010d1f4a1aa92203ec59ce015ade4b_3.png)

然而，结果看起来并不正确。与单张图像相比，平均后的图像中心区域显得均匀，整体也更暗。这是为什么呢？

![](img/58010d1f4a1aa92203ec59ce015ade4b_5.png)

![](img/58010d1f4a1aa92203ec59ce015ade4b_7.png)

请注意，这些图像的数据类型是 `uint8`。`uint8` 数据类型只能存储 0 到 255 之间的整数值。这虽然节省内存，但存在限制。例如，在 `uint8` 数据类型中计算 200 + 200，结果是 255，而不是 400。这个操作导致数据饱和，达到了该数据类型的最大值 255。

![](img/58010d1f4a1aa92203ec59ce015ade4b_9.png)

这解释了为什么平均图像的中心看起来均匀，但同时整体变暗。在进行加法运算时，许多像素值饱和到了最大值 255。随后将这些像素值除以 5，结果变成了 51。

因此，在对图像进行算术运算之前，应使用 `im2double` 函数将其转换为 `double` 数据类型。此函数还会将值重新缩放到 0 到 1 之间，这是许多图像处理算法的标准。

```matlab
image_double = im2double(image_uint8);
average_image_double = (im2double(image1) + im2double(image2) + ... ) / 5;
```

![](img/58010d1f4a1aa92203ec59ce015ade4b_11.png)

转换为 `double` 类型后得到的平均图像，给出了预期的结果。

![](img/58010d1f4a1aa92203ec59ce015ade4b_13.png)

我们可以使用 `montage` 函数来比较平均图像与其中一张原始图像。

```matlab
montage({single_image, average_image_double});
```

要使用此函数，请在花括号内提供以逗号分隔的图像列表。此处的差异很难看清，但放大后可以看到，平均图像中星云的噪声更少。

![](img/58010d1f4a1aa92203ec59ce015ade4b_15.png)

请注意，`double` 数据类型所需的内存远多于 `uint8` 数据类型。可以使用 `im2uint8` 函数转换回 `uint8` 类型。

![](img/58010d1f4a1aa92203ec59ce015ade4b_17.png)

![](img/58010d1f4a1aa92203ec59ce015ade4b_18.png)

```matlab
average_image_uint8 = im2uint8(average_image_double);
```

![](img/58010d1f4a1aa92203ec59ce015ade4b_20.png)

像求平均这样的计算，需要你显式地在数据类型之间转换。然而，Matlab 中的大多数图像处理函数会为你自动完成此操作。

![](img/58010d1f4a1aa92203ec59ce015ade4b_22.png)

## 转换为灰度图像

接下来，我们看看如何简化图像。将彩色图像转换为灰度图像就是一个例子，函数内部会自动完成所有必要的数据类型转换。

![](img/58010d1f4a1aa92203ec59ce015ade4b_24.png)

灰度图像占用内存更少，处理速度更快，并且可用于更广泛的图像处理任务。

```matlab
gray_image = rgb2gray(color_image);
```

你可能会想，转换为灰度是否会丢失信息？答案是肯定的，但通常颜色信息并非必需。假设你要计算这张图像中的星星数量，你只需要亮度信息，而这已由灰度强度值捕获。

![](img/58010d1f4a1aa92203ec59ce015ade4b_26.png)

让我们比较一下灰度图像与彩色图像的大小。所有这些变量都相当大，其中彩色图像所需的内存是灰度图像的三倍。

## 调整图像尺寸与旋转

![](img/58010d1f4a1aa92203ec59ce015ade4b_28.png)

降低图像分辨率可以减少所需内存。使用 `imresize` 函数来调整图像尺寸。此函数有两种使用方式。

第一种是提供一个缩放因子。例如，以下代码将图像缩小到原始分辨率的 75%。

```matlab
resized_image = imresize(original_image, 0.75);
```

第二种方法是指定输出图像的行数和列数。

![](img/58010d1f4a1aa92203ec59ce015ade4b_30.png)

```matlab
resized_image = imresize(original_image, [new_rows, new_cols]);
```

![](img/58010d1f4a1aa92203ec59ce015ade4b_32.png)

如果你的应用要求图像具有特定尺寸，请使用第二种方法。需要注意的是，如果 X 和 Y 方向的缩放因子不同，调整大小后的图像将会失真。

![](img/58010d1f4a1aa92203ec59ce015ade4b_34.png)

旋转图像也很常见，目的是确保多张图像或不同设置下的图像具有相同的对齐方式。使用 `imrotate` 函数旋转图像，输入角度单位为度。

![](img/58010d1f4a1aa92203ec59ce015ade4b_35.png)

```matlab
rotated_image = imrotate(original_image, angle);
```

![](img/58010d1f4a1aa92203ec59ce015ade4b_37.png)

负角度表示顺时针旋转。请注意，旋转后图像的大小变大了，因为需要额外的行和列来为旋转后的图像腾出空间。如果希望输出图像与原始图像大小相同，请使用 `‘crop’` 选项。

![](img/58010d1f4a1aa92203ec59ce015ade4b_39.png)

```matlab
rotated_image_cropped = imrotate(original_image, angle, ‘crop’);
```

![](img/58010d1f4a1aa92203ec59ce015ade4b_41.png)

## 保存处理后的图像

![](img/58010d1f4a1aa92203ec59ce015ade4b_43.png)

最后，我们来学习如何保存处理结果。要保存处理后的图像，请使用 `imwrite` 函数。

第一个输入参数是要保存的图像变量名，第二个输入参数是使用的文件名。写入文件时，将使用文件名扩展名中指定的文件格式。

![](img/58010d1f4a1aa92203ec59ce015ade4b_45.png)

```matlab
imwrite(image_to_save, ‘output_image.png’);
```

以上代码创建一个 PNG 文件。PNG 文件使用无损压缩，但文件大小大于 JPEG 等有损压缩格式。这也是 JPEG 压缩被广泛使用的原因之一。

![](img/58010d1f4a1aa92203ec59ce015ade4b_47.png)

![](img/58010d1f4a1aa92203ec59ce015ade4b_49.png)

保存 JPEG 时，可以指定从 1 到 100 的图像质量。数值越高，图像还原越准确。但请注意，即使质量因子为 100，仍然使用的是有损压缩。

```matlab
imwrite(image_to_save, ‘output_image.jpg’, ‘Quality’, 90);
```

![](img/58010d1f4a1aa92203ec59ce015ade4b_51.png)

你会注意到这三种图像格式的文件大小存在显著差异。建议尝试重复本视频中的分析，并打开图像查看图像质量是否存在明显差异。

![](img/58010d1f4a1aa92203ec59ce015ade4b_53.png)

## 总结

![](img/58010d1f4a1aa92203ec59ce015ade4b_55.png)

本节课中我们一起学习了图像数据处理的基础操作。我们了解了在对 `uint8` 类型图像进行算术运算前转换为 `double` 类型的重要性，掌握了使用 `rgb2gray` 进行色彩空间转换，使用 `imresize` 和 `imrotate` 进行几何变换，以及使用 `imwrite` 保存图像并选择不同格式和质量参数的方法。这些是进行更复杂图像处理前必须掌握的基本技能。