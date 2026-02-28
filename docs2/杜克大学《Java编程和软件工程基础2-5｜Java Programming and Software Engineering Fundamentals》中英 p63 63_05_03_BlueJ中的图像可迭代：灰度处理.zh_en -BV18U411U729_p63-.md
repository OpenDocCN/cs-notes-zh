# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p63 63_05_03_BlueJ中的图像可迭代：灰度处理.zh_en -BV18U411U729_p63-

![](img/d7e115f6adc5fe815fd4cebc362cb03a_0.png)

Now that we've developed our algorithm to convert to grayscaleale， we're ready to write code。

 we've started here with a class for the grayscale converter and we've already importededduu。duuc。

star， and before this video started， I went ahead and wrote in the steps that we came up with as comments in our code to guide us as we write。

The first thing we did in our algorithm was we started with the image we wanted in image in this case that's going to be a parameter that we pass to our function so that this function can operate on any image we want。

The next thing we did was we made a blank image of the same size as an image。

 so if I want to make a new image。Going to declare an image resource。

 we called it out image in our algorithm， and since I want to make a new thing。

 I'm going to say new the type of thing I want to make is an image resource and when I create this image resource。

 I need to pass in information in this case telling it how big I want my image to be This is going to be the width。

Of in image。 and the height。Of an image。The next thing we did in our algorithm was we said we wanted to do something for each pixel in out image。

 that's going to be a for loop， which you've seen before， pixel。In out。Image dot pixels。

And we're going to put。Curly braces around all of the steps of our algorithm that we want to do for each pixel。



![](img/d7e115f6adc5fe815fd4cebc362cb03a_2.png)

And you can see that blue J put this all in pink so we can easily see that these all are going to happen for each pixel。

In our algorithm， the next thing we did was we looked at the corresponding pixel in an image。

 so what we're going to want to do is in image。t git pixelixel at the same location as pixel。

 so pixelixel。t git x。In Pixel。gey。Now， when we do this。

 we need to give it a name so we can use it again。 That's going to mean we're declaring another variable。

 so it's going to be。In P。Gus。In image。getpixel。The next thing that we did was we said we wanted to compute in pixels red plus in pixels blue plus in pixels green。

 divide that by three and call the result average。So I want in pixel。So red。

 which is going to be in pixel。getread。Plus， in pixels blue in pixel。 get blue。Plus。

 in pixels green in pixel。 get green。And then I want to divide by3。 Now， if I write divide by3 here。

 I've made a small mistake because order of operations is going to make。In Pix。

t get green divided by3， I want to divide the whole thing by three so I need parentheses。

And we want to call this average， we're declaring a new variable， what type is this variable。

 well it's going to be just a plain number， so int。Average equals all of that math。

Now I want to set pixels red， so pixelel dot set red to average。And similarly， pixel dot set。

Green to average。And pixel。That set blue to average。



![](img/d7e115f6adc5fe815fd4cebc362cb03a_4.png)

Those are all of the steps I wanted to do for each pixel and then our last step at the bottom here says out image is our answer wheneverever we know the answer to a function。

 we return that answer， so in this case out image is our answer， we just return out image。



![](img/d7e115f6adc5fe815fd4cebc362cb03a_6.png)

So now I'm going to come up here and click compileile at the bottom it says class compiled no syntax errors。

You've frequently been testing your code by just making an object in the Blue J main window and calling it。

 it's methods， but making an image resource there is a little bit tricky。

 so we're going to write another method to help us test this out。



![](img/d7e115f6adc5fe815fd4cebc362cb03a_8.png)

Public void， let's call it test gray。 is going to take no parameters。 It's going to make。

An image resource will call it I R with。New image resource。

And that's going to pop up a dialogue and ask us what image we want。

And then we're going to make gray。On this。Image resource。 And then we're going to draw that。 Now。

 if we'd forgotten the name of the method we just wrote， we could， we could scroll up and look。

 but I just remember it's called make gray。 I'm going to compile again， no syntax errors。

 We obey the rules of the language。 We don't yet know if our code works。 Now。

 I'm going to come over here to the main window。 I'm going to hit new grayscale converter。

 and it's going to give me this object in my blue J。



![](img/d7e115f6adc5fe815fd4cebc362cb03a_10.png)

Now I'm going to hit test gray， it's going to pop up a dialogue asking me。What image I want。

 I'm just going to choose these nice， colorful Easter eggs。



![](img/d7e115f6adc5fe815fd4cebc362cb03a_12.png)

But when I run it through my grayscale converter， I get Easter eggs in gray。

 since my code past this test case， I'm more confident that it works。

 and in general the more test cases we run， the more confident will be in our code's correctness。

