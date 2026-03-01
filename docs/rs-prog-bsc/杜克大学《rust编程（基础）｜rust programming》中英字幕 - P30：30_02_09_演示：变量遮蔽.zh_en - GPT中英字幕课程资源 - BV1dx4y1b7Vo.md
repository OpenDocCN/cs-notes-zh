# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P30：30_02_09_演示：变量遮蔽.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/fb1d5c3598256c1fe305a124b9cd4063_0.png)

Shadowing variables or variable assignment using shadowing is something that is common in other programming languages。

 and bras definitely allows you to do that。What is shadowing is the ability to define a variable like in this case height which we've seen before and then reassign it to something else to some other value。

 Now this can also be done by reusing the previous height value or variable defined right here。

 So all of this is possible so you can have from here to here and definitely works。

 Now we're getting a red curly underline What's the deal here What is one of the problems。

 We've seen this before。 Are you able to catch what is going on here。 It is a very simple problem。

 We're modifying something here that perhaps we shouldn't be modifying。

 So we're going to run it here and there we go we're assigning something to an immutable variable Of course I actually forgot to make it mutable So why don't we go ahead and make it mutable。

 so I'm going to say mute。AndThen suddenly things are working Okay。

 well that that works So we said you know the height is 190 now we're going to reassign that make this shadowing possible by reusing the variable and subtracting 20 and now we're going to do some else if and else conditionals Now there's something else here that。

Might look slightly odd if you're coming from programminging languages like Python that doesn't necessarily allow this in this case。

We have an expression that is matching the parable assignments。 We here have like a lead result。

And we're doing an if condition and we're saying if height is bigger than 180 then we're doing tall and then otherwise we're doing average。

 otherwise we're doing short so instead of printing we're assigning so like an expression is returning a value depending on the conditionals that we're defining here with the else else if and if conditions。

 so what does that mean notice something with these string over here。

The the thing that is missing actually here is that there's no semicolon。

 we had semicolon there semicolon here， but not here。

 that means that if these condition matches then tall will be assigned to result over here same with average if that's the height and same with short so now if we run it we will check the result value and as expected it is short so' clear that out and make these r was change so it is 170 so I'm going to make that make that quick change and then we'll get tall of course as expected right here and that's perfectly fine。

Okay， so that might be you know slightly odd if you're not used to you see expressions to be assigned to variables。

 but that is exactly how they work in rust now let's do a little bit more exploring by let me copy pastes very quickly and get some other things that you can do and this way is a way of inlining that if else condition so。

Here we're saying health if height is less than 180 good else is unknown and then we're just printing what the health is and then we're also able to shadow to a different type now we haven't seen types in detail yet。

 but this is something that definitely you can actually do in rust and is definitely allow to do that。

We are doing here health health。 Now in in this case， we were doing true our falses。

 which is definitely different than what good and unknown was。

 these are strings and these are boolean。 So wise is rust allowing us to do that。 well。

 we are redefining it by using lead。 actually， if I go ahead and remove lead and save that。

 we'll get this error from the compiler that says that。It was expecting a string and found a bullion。

 now， why is that well， because'm I'm changing the type and I can't really do that unless I do these now。

You should have a very good reason why you are actually doing shadowing and changing types on the fly one of the benefits of using rust is that it's a strongly typed language you have to actually define your well not necessarily define your variables or the type of your variables but those can get infer but I could definitely be strict about it。

 but if I'm changing them on the fly well I have to have like a very good reason why these types are changing and reassigning them in this way sometimes with loops that something that is under control and we haven't seen loops yet。

 but it's something to keep in mind just be very mindful that the benefit of rust is that it's a strongly type language and the variables have types and changing the types on the fly like these might not be necessarily a very good idea。



![](img/fb1d5c3598256c1fe305a124b9cd4063_2.png)