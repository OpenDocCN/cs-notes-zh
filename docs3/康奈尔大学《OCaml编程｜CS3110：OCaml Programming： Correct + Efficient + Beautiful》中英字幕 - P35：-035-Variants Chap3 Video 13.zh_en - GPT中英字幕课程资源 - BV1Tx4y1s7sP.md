# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P35：-035-Variants Chap3 Video 13.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Last week we learned about records and Ts， which are two ways built into OCMel of creating your own new data types。

This week we're going to look at variants， which are an exciting new way to build data types。

 it's going to start off looking pretty familiar。😡。

Perhaps you've seen types in other languages that let you enumerate different constants that could be part of a type。

 like an enum it's sometimes called。OM has something similar to that with variance where we can say type in the name of the type。

 let's say primary color。And give some constants that are then the values of that type。

 so we're basically enumerating what they are， so maybe a primary color would be red or green or blue。

 for example。And now we could have values of that type， let R of type。Primary color B red。

And you'll notice that if I hover over it， it is a primary color and of course I didn't need to put in that type annotation。

 O Caml could have inferred that for me。R is a primary color。So that's the simplest kind of variant。

But there are definitely more interesting variants as well。

So let's try to create a variant for shapes。We're going to represent shapes in the Cartesian plane。

And to help me with that， I will recall the type that we have for points， let's make it float。

 star floatlo today。So this is a float， this is a point in the Cartesian play with an X and a Y coordinate。

Let's create a type for shapes。There's a bunch of shapes in the world， how about we create circles？

And rectangles。Now circles and rectangles， of course， in addition to the shape that they have。

 could be located somewhere in the plane。So let's represent a circle with the coordinates for its center point。

As well as the measure of its radius。So that means we need some additional information along with just this name here circle。

We can do that with variant by saying of。When I say of after circle here。

 I'm saying that it's not just a circle， it also consists of other data that need to be carried along with that fact that it's a circle。

And what is that data Well， we said we wanted a center point and a radius let me use a record type for that so center of let's have a center point。

So we'll have a field name center whose type is point。And a field named Radius， whose type is float。

Now I can have such circles。Let see one。Be a circle。That carries along with it at center。

 let's say that it's at the origin， so 0。0 0。0 could be the coordinate of that center point。Now。

 of course， I need to give the name of the field there because this is a record。

And I also need a radius， so the radius， let's say it's just the unit circles。

 so it has a radius of one。There we go Now C1 is of type shape。Actually you know what。

 I don't want to make this shape， so let me make it singular。There we go。ok。What about rectangles？

There's a bunch of ways we could represent rectangles too。

 let's decide to represent them with just two points。

 their lower left coordinate and their upper right coordinate。

So the rectangle needs to carry along some more data as well， Ill make of a record again。

 lower left of type point。And upper right of platform。

Now I could have for what this data is carrying here。

 I could have instead of saying a record there done point， star point。

 as we know with records and tus， the difference is just by position versus by name。

For design purposes here， I find it easier to keep track of which point is which by labeling those fields with names lower left and upper right。

 if I just made it a tuple like this， I would personally always be forgetting like which is the lower left which is the upper right or did I really do upper left and lower right。

 so I find that this makes the code more self-documenting。

Let's create a rectangle so our rectangle could be。天angle。It's lower left coordinate。Could be。Oh。

 let's have it be at。Negative  one。Negative  one。And it's upper right。Could be at。W呢。1。

Its falling off the screen a little bit just because I have my font set size set pretty high so that you can see it when you're watching these videos。



![](img/7c821b86abb8be20d504243b43406040_1.png)

![](img/7c821b86abb8be20d504243b43406040_2.png)