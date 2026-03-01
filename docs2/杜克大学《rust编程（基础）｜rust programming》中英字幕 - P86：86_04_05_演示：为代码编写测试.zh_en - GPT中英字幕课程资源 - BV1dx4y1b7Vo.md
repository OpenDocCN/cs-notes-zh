# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P86：86_04_05_演示：为代码编写测试.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/dab87750c5362dd0d4eb52417645f06c_0.png)

We have here our colors module that I've prepopulated with some extra things that we haven't been seen before。

 so we have the functions that we colorize a string to have red green。

 blue and bold and the implementation is pretty straightforward we're passing in a string and we're getting an output that gets colorized。

 these are antiscape codes so what happens here is that it will make the string that goes right there coming from S which is that argument and it will make it a colorized output on the terminal so that's what we're working with and we have red green blue bold and we have a reset one。

The reset one is what we're gonna focus in for these test that we're gonna write。

 and the reason why is because the reset allows us to pass in something that has been previously colorized。

 like say for example， blue and it will remove thescape codes and will have no formatting at all。

 So it's a very good use case。 but let's see how these functions are being used。

 And this is actually what you will be experimenting with when you're working with code。

 Most probably you won't be writing everything from scratch。

 will be thrown into a problem like this where you might be tasked with looking at a module like colors that are and say。

 hey， these needs some test coverage。 There are no tests for these and how are you gonna go ahead and do that。

 All right， so we have these in them called color。 we have red green。

 blue and bold and we have destruct， which is public and has what the color is， what the original。

String is and colorized which the string the string doesn't change。

 What gets added is these colorized output。 so this statess the original one and this states as the colorized one。

 So given more flexibility for someone that wants to play with both and we're going to extend color string by using a paint function that is going to depending on the color is going to do certain transformations and you can see that colorized field that is going to in case if it's red。

 it's going to update these colorized field or value here for the field colorized is' going to use our function red。

 So we're doing lots of things there and we're using match， which is great。

 and finally there's this other method here called reset that basically resets the string to just have that use that reset function that we were seen before。

Alright， so how do we go about brain test so first off we're going to start by creating a test directory and in that test directory let's create a new file and let's call it test underscore colors that arrest。

And in these test that underscore colors that， we're going to first import or bring into scope that thing that we want to test in that thing is coming from colors。

 So in this case， when I say use CI u。And we are going to make it from colors。

 And then we're going to use， let's go back to our module。 when I use， we're going to test。

 we're going to test a color string。 So let's do bring in color string。Wwhich is this one right here。

 Sos that's very good that that's exactly what we want。 Let's triple。

 make sure that colors is very well defined Libar arrays It is right there。

 That is why that works because if we if we comment that out right if we save that are test that underscore colorss is going to get red because this is not going to work right there。

 So let's fix this save that make sure that Libar array is fine go back to test underscore colors and we're bringing color string into scope。

Alright， so when we bring that into scope we the first thing we want to do。

 well is actually write a test and the first thing I want to do is give this attribute which is the test one and we'm going to start writing tests for color strings so。

This looks kind of okay， but we're not going to quite accept that yet。

 we're going to figure out what we want to test first， so let's go to colors。

And what I want to test is that if I have a color string and I define it like that that I'm going to。

Have， I'm going to use an enum。 And then I'm going to call paint defining by that is going to verify that the color。

 depending on the color is going to。 So。 So let's start with red and let's have that verified。

 So'm going to say。呃方engch。Test red coloring。And we are going to bring into this create thisstruct。

 So let's say color underscore string。 that looks。That looks almost right。

 So let's go ahead and save that。 And now we can run it。 So， but before we run it， let's。

 let's go a little bit through the things that we're trying to do here。

 So we're constructing the color string struck。 We're saying we're going to use。Red， actually。

 that looks。I don't like it when we have to do it when we have these modules or the scope comes in like that。

 So we're gonna say how about we bring it like that， Actually this is not red。

 this is color and then when we come in here we say color is the inum and we say red So looks it reads a little bit better than what we were getting suggested by copil it right there So what we have here is thestruct that looks correct to me and then we're going to say painted it and we're going to get these verified like that。

 So how about we run the test and we see what happens。

So we' remove the explorer right here and we're going to get our first running test saying hey。

 this looks correct， this looks fine。 you actually were able to verify so that looks pretty okay to me I can see now that there's an implementation detail that doesn't look correct to me the idea with colorized field was not to have to be adding that to the constructor so perhaps adding a new function or a new method that is the constructor for color string would be helpful here so that you would be able to set these things up for us but that's good and what we've done is we construct what we won a test then we call the paint method and then we make an assertion so the assertion is coming from this macro a underscore EQ and then the exclamation sign for a macro this means that it's a certain equal。

Let's actually mess it up a little bit and save that and run the test again and see what happens。

So we get a failure and if we scroll a little bit all the way to the top。

 we'll see that we're gonna to have a left side and then a right side Now here I remove I remove the bracket that's why that's missing right there and were essentially going to a verification failure verification there So we'm going remove that。

 I'm going to add that bracket again and save it and run the test again and we're going to be okay so that is essentially how we write our first test we identify the test case we tried to figure out what we need to do and we've added we've brought in scope these things that are coming from our project from our library from colors and the colors module in this case colors string and the color in them and then we're construct and construct and then we're making。

Some changes to it and then we are making some assertions about the expectation so this is what we have this is what we have and this is what we expect So there you go that is how you add a test to a vanilla Rus project that didn't have any tests and we were able to make that happen with that attribute right there that tells cargo that this is actually a test and it should be running this。



![](img/dab87750c5362dd0d4eb52417645f06c_2.png)