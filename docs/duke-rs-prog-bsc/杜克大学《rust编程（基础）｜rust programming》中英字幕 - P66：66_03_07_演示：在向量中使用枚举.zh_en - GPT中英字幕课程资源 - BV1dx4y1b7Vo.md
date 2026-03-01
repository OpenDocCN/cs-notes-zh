# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P66：66_03_07_演示：在向量中使用枚举.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/6fa4d3542ee982cccb09c91ac2498fea_0.png)

Let's mix a little bit our inums with vectors weve worked before with inums， we' defined them。

 sometimes they take some data and we are capturing that data as part of the variance in this case。

 we're saying this is a circle that's a square we both going to take a float 64 bits in size and that's the shape。

 So if it's a circle you'll get a number or what a square Now what I said that we're trying to do we are trying to find the total area of either a circle or a square independently。

 So we know we're going to have to deal with a shape and depending on what we're getting。

 we have to calculate。That and what we are going to be doing。 and of course。

 you can come up with other different examples。 but where the way we're going to try to lay this out is we're going to have a vector。

And that vector is going to have one shape that is a circle and another one that is a square。

 this one is going to be 5。0 and this is going to be 3。

0 for a circle that's a radius for a square that could be the length in one of the sides。

 it doesn't matter because if it's a square。Now let's take a look at the implementation here and this is something that we haven't seen before。

 so I'm going to go step by step， so we're going to define the total area。

 we are saying we're actually telling rust hey by the way these variable that I'm defining right here it's going to be of flow of 64 bits just like we have here our variant that are taking some data we are going to take our variable shapes that comes from here which is a vector and then we're going to call that iter that iter is a way to iterate in place and what we can do with that like instead of like creating a normal for loop for that we're going to call map which is a way of simplifying the whole operation So that iter thatt map Now this construct here in that map might look。

Slightly strange。 What we're always the way this is constructed is like with with these characters here and rather it defines every single item that comes from iter。

 So we're saying hey， by the way， the iterator is going to sneak this into us is going to inject this parable and that's going to call be called shape and now with that we are going to use that over here。

 which is a match and now match is going to look at shape and if it's a circle then it's going to this。

 and if it's a square is going to do that。 So that is great because now we are decoupling kind of like whatever we're getting we know that we're going to get either a circle or a square。

 So if we're saying hey， if it's a circle let's do the constant which is a pi which is coming from the。

Library from rust and we're going to multiply pi times radius times radius again。

 Otherwise if it's a length， we are going to provide the square product of length times length Finally what we're going do once this operation is done we are going to call that sum which is going to sum and going to do a sum on all of the elements of the iterator So let's run this I it's a lot of a lot of stuff going on in there So here we have 87。

53 square units and that is kind of like what the find here in the string and that is the total area and we could still you know be adding more shapes in here we could say how about we are on our circle that's perfect and run it and our 87 is now going to grow to 100。

So this is a different way to look at inums and how we can deal with an actual vector of these inums have to wholesome information there about specific variants。

And then finally I think it's pretty useful to look at this construct with map。

 I know we're looking at inums specifically， but using map here and with E to take a look at all of the items that we're having in the vector is a solid way to trying to do even more things and have more flexibility when you're working with inums。

 but not only with inums， but also with vectors。

![](img/6fa4d3542ee982cccb09c91ac2498fea_2.png)