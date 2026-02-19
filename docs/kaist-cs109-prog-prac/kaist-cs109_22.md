# 图像处理

要处理诸如照片之类的图像，我们需要能够将照片文件加载到图像对象中，读取和设置图像的像素值，并将图像保存回照片文件。

我们使用类 [java.awt.image.BufferedImage](http://docs.oracle.com/javase/7/docs/api/java/awt/image/BufferedImage.html) 存储图像数据。你可以通过以下方式创建这样的对象：

```
  import java.awt.image.BufferedImage

  val img = BufferedImage(width, height, BufferedImage.TYPE_INT_RGB)

```

或者你可以使用以下方式从文件加载图像：

```
  import javax.imageio.ImageIO

  val photo1 = ImageIO.read(java.io.File("photo.jpg"))

```

此调用的结果是一个 BufferedImage 对象。你可以使用以下方法找到此图像的宽度和高度：

```
  println("Photo size is ${photo1.width}, ${photo1.height}")

```

你可以使用以下方式将图像对象保存到文件中：

```
  ImageIO.write(photo1, "jpg", java.io.File("test.jpg"))

```

或者，如果你更喜欢 PNG 格式：

```
  ImageIO.write(photo1, "png", java.io.File("test.png"))

```

BufferedImage 对象的像素可以使用 getRGB 和 setRGB 方法读取和更改，见下文。

#### 示例脚本

以下小脚本读取一个名为 photo.jpg 的文件，获取其尺寸，创建一个新的大小相同的空图像，将旧图像 img 中的像素复制到新图像 out 中（通过水平镜像），在照片上对角画一条红线，最后将新图像保存在一个名为 test.jpg 的文件中（[image.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/90-image/image.kts)）：

```
import java.io.File
import javax.imageio.ImageIO
import java.awt.image.BufferedImage

fun phototest(img: BufferedImage): BufferedImage {
  // obtain width and height of image
  val w = img.width
  val h = img.height

  // create new image of the same size
  val out = BufferedImage(w, h, BufferedImage.TYPE_INT_RGB)

  // copy pixels (mirror horizontally)
  for (x in 0 until w)
    for (y in 0 until h)
      out.setRGB(x, y, img.getRGB(w - x - 1, y) and 0xffffff)

  // draw red diagonal line
  for (x in 0 until Math.min(h, w))
    out.setRGB(x, x, 0xff0000)

  return out
}

fun test() {
  // read original image, and obtain width and height
  val photo1 = ImageIO.read(File("photo.jpg"))

  val photo2 = phototest(photo1) 

  // save image to file "test.jpg"
  ImageIO.write(photo2, "jpg", File("test.jpg"))
}

test()

```

#### 颜色

方法 getRGB(x: Int, y: Int): Int 返回位置 (x, y) 处像素的颜色，方法 setRGB(x: Int, y: Int, color: Int) 设置此像素的颜色。

颜色以整数对象表示。红色、绿色和蓝色三个组件被"打包"成一个整数。每个组件有 8 位，因此其值可以在 0 和 255 之间。打包的颜色是一个 32 位整数，其位如下所示：

```
  tttt tttt rrrr rrrr gggg gggg bbbb bbbb

```

前 8 位要么为零，要么表示像素的"透明度"。我们不会使用这些透明度位。接下来的 8 位表示红色，再接下来的 8 位表示绿色，最后的 8 位表示蓝色。这就是为什么这种表示称为"RGB"。

给定值范围在 0 到 255 之间的红色、绿色和蓝色分量，我们可以像这样将它们打包在一起：

```
  val color = (red * 65536) + (green * 256) + blue

```

给定一个打包的整数颜色，我们可以按如下方式提取三个分量：

```
  val red = (color and 0xff0000) / 65536
  val green = (color and 0xff00) / 256
  val blue = (color and 0xff)

```

（这里的与运算符是按位与运算符。它确保只使用我们感兴趣的位。）
