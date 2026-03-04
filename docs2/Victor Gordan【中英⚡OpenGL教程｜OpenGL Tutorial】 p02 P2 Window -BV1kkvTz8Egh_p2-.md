# Victor Gordan【中英⚡OpenGL教程｜OpenGL Tutorial】 p02 P2 Window -BV1kkvTz8Egh_p2-

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_0.png)

In the previous tutorial， I showed you how to set up OpenGL in Viual Studio。

 so now we're going to pick up where we left off and create a window。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_2.png)

We're going to use GFW to do that， so the first thing we need to do is initialize it so we can properly use its functions。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_4.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_5.png)

And since we've initialized it， we should also terminate it before the function ends。

 so I'll add this at the end of the function。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_7.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_8.png)

Now JLFW doesn't really know what version of OpenGL we're using。

 so we need to tell it that we can do that by giving it so called hints with a special function that takes a type of hint and a value。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_10.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_11.png)

For example， here， I'm giving it a hint that we are going to specify the major version of openGL that we are using。

 and then I give it the version itself， which is3 since we are using OpenGL 3。3。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_13.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_14.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_15.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_16.png)

Now I' just going to do the same for the minor version， which is the exact same one。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_18.png)

The last hint we have to give it is about which open GL profile we want to use。

 So I'll type GL F W underscore Open GL underscore profile。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_20.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_21.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_22.png)

Now an open gel profile is sort of like a package of functions， as far as I know。

 there are only two packages。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_24.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_25.png)

Core， which contains all the modern functions and compatibility。

 which contains both the modern and outdated functions。 We only care about the modern ones。

 so I'm going to use the core profile。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_27.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_28.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_29.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_30.png)

No， for doing the itself。This is the data type of a window object in GFW。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_32.png)

Let's just name in the window。And use the create a window function。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_34.png)

This will take five inputs， the width of the window， the height of the window。

 the name of the window。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_36.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_37.png)

Whether we want it full screen or not， which we do not。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_39.png)

And the last thing is not important。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_41.png)

And just be on the safe side， I'll add a bit of error checking in the case in which the window fails to create。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_43.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_44.png)

So grid， we now have a window object。Problem is GHW isn't the brightest heat around the block。

 so I don' have to tell him that since we've created the window， we would also like to use it。🤢。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_46.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_47.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_48.png)

Who would have thought。This tells GFW to make the window part of the current context。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_50.png)

A context being a sort of object that holds the whole of open gel。 It's a bit abstract。

 as context can hold in do many things， but we'll just go with this for now。



![](img/5fb0c3c3ba80d52477b28d97b06dd36d_52.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_53.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_54.png)

Now just like before， once we are done with the window itself， we want to delete it。

 so let's do that at the end of the main function。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_56.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_57.png)

If you run the program now， you'll maybe be able to spot a window。

 pop up and instantly disappear into oblivion。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_59.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_60.png)

That happens because once the main function finishes scrap。

