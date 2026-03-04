# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P37：-037-Pattern Matching with Variants Part 2 Chap3 Video 15.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've seen how to write code with shapes to take the center of a shape using pattern matching。

Let's improve that code just a little bit now and explore adding new shapes。

When I did the pattern matching here to determine the center of a rectangle。

 I had to first pattern match to see whether it was a rectangle and if so get out the lower left and upper right coordinates from that record。

 and then I had to further pattern match against the points that I had got out of the record to get their individual coordinates。

 their X and Y coordinates。I'm allowed to do much more sophisticated kinds of patterns here。

 you can nest patterns inside of other patterns， just like you can nest expressions inside of other expressions。

So up here for lower left。I could have written a pattern match right here in place and said I want to immediately pattern match against that lower left and say get out the lower left coordinate。

 the X coordinate， and the Y coordinate。I could do the same thing with the upper right here。

So that could be Y， let's see x， upper right， y upper right。

Now it would probably help if I put a little extra spacing in here and now because I have the font size so big。

 I'm going to drop the stem another line。Now I've done that pattern match all at once there as part of this upper level pattern match。

 I don't need to do this extra work。😡，Of all of that code in the middle there。

So this can really help clean up your code by doing this kind of deep pattern matching by having patterns nested inside of other patterns like this。

Let's add another shape。Of course circles and rectangles aren't the only kind of shapes in the world。

 let's have a very trivial kind of shape， say which is just a point。

 so it's not even a 2D shape is just 1D。And that will carry along the information of just the coordinates of that point。

So I've added a new constructor here named Capital Point and it carries along this additional data of。

Let's create a point here。As an example， 31。All right， now when we go back to our center function。

 we see a lot of quickly underlines what's going on there。



![](img/16795db8e50242d3d0dc827c55df315e_1.png)

This pattern matching is not exhaustive， here's an example of a case that is not matched。

 point underscore。

![](img/16795db8e50242d3d0dc827c55df315e_3.png)

So what it's saying is。There is a constructor that's missing from this pattern match。

 you haven't said what to do in the case that the shape S that's passed into function center is a point。

And that shape would carry along with it some additional information。

 it would carry the coordinate that the point is at， the lower case point as it were。

And that's what the underscore is referring to there， so the underscore is saying。

 hey this is the example of a pattern that would be able to go here。

 there's some other data carried by that point construct。So we need to add that in。

So what would that point be， well， it could be a point P and then we could pattern match against P with the let expression to get the coordinates out。

 but as we've just seen， we could instead say that it's the X and Y coordinates there if we wanted。

And we could return， what's the center of a point， I guess it's just the point itself。

 we could return x and Y。That would work just fine。We wouldn't need to do it that way。

 of course that whole point itself is the return value we want so if we said point P。

You could just use P there as the return value as well。

One thing we could not do though is use an underscore here。

Because that would pattern match and throw away the data inside the point constructor。

So now we would no longer know what to return the best we could like fail with。I don't know。

 what are we going to return there， nothing makes sense。Likewise， you could not leave off。

The data that that constructor is supposed to carry and I return something else。

 maybe P1 as a dummy value right you're going to get an error there。

 this constructor point expects one argument but it's applied here to zero arguments so we really do need to say something here about what that point is that's carried along with the capital point constructor。



![](img/16795db8e50242d3d0dc827c55df315e_5.png)