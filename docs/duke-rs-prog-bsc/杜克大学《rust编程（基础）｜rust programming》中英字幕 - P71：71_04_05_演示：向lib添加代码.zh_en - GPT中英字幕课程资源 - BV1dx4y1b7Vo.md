# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P71：71_04_05_演示：向lib添加代码.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

Next， we are going to go ahead and look back again to our re split project here and we're going to select we're going to copy paste these read standard in and move it over to our library or Lib that rest in our other CI U project so that's here I'm going to paste it in and we should like almost right out of the bat get certain problems specifically Buff reader needs to be imported in so to satisfy that I'm going to use some imports here with use and I'm going to say I want both Buff reader and Buffread actually if I do just that I'll get an error why don't we explore for a second here what is there if I only use。



![](img/31f6d5895dd0b9944d5f27f3a9ed0523_1.png)

Buff buff reader。 So let's hover over the red line。

 I'm going to get no method named read line found for struck Buff reader in the current scope。

 items from traits and only be used if the trait is in scope。 What does that mean。

That means that in some situations in rust， you have to make some imports。

 you have to pull certain modules， certain items to be in scope for the current module in this case lived at R this is fine this is all okay but the cool thing is that we're getting these nice error that is telling us exactly what we need to do so going to get this back as we had before we had to import Buff read。

 so this is a fairly common read from standard in and we need to we need to make sure that we have everything in order and actually from the previous project that is was one of the lines。

Next， I'm going to get rid of the Expr here so that we can concentrate into exactly what is it that we're dealing with in this read standard in function that is actually trying to do some action so aside from the function definition right here。

 it's not taking any arguments， it is going to return a string。So that's that's very， very good。

 We have a string that we're going to return and you can actually see right here pin return line that trim to string。

 Al right， so moving on， line number five， we're going to define that。

Our standard in is going to be from the standard library。

 we're going to use STd then Io and then STD in What does like if you've never play it around with command line tools on the terminal the standard in is a way where you can actually feed in a command line tool with some input using a pipe let's take a very quick look at how to do that in the terminal So in the terminal we can do I'm going to clear this we can do something like echo and some text and that would echo some text but what would be standard in if I pipe these to something else so say for example。

 we can do G to try to filter certain things out or actually let's just do cut because it's the same tool as resplit that I was trying to implement in rust so I'm going to use cut and I'm going to use I'm going to say that the limiter is going to be whitespace。

And the field I want is the first one。 So what does this mean This is going to be the standard in that is going to go into the input to cut and cut the tool is going to accept standard in that means is going to accept this as input And if I run this will get some and why because the delimer is the space。

 the white space which is right here and the first field is sum in the second field is going to be text。

 So in the nutshe or or in a very very， very quick way that is what standard standard in is。

 and that's kind of we're trying to do。 So I close that back to our little function now we need to have a mutable define a mutable variable that it is going to read from the standard in and then we're going later be using it to modify it。

 So what's the deal here， we are going to create a new。

A new instance of a B reader I'm going to say we're going to read from Standard in and we're going to use lock。

 the lock is able to allow to read from standard in until it goes it goes out of scope so pretty useful and you can see here it's a very standard way of reading from standard in and we're actually doing the same thing here。

Next， we're going to define a new variable， a mutable variable called line and when I say that's going to be a new string。

 so why is that because the contents of this is going to go into this variable and you can see here reader that read line we're going to pass our mutable line which is this string that we created。

And if it fails， we're going say， hey， we fail to read the input line as you know。

 dot expect is a way of dealing with an error that we possibly think that could go wrong and that would cause a panic you could certainly deal with many different ways in this case but in this case we just want to say no we want to coexpect and that that's fine in this situation and finally we're going to trim that line and we're going to return a string trimming allows us to get rid of any white space that is being past and two string is going to ensure that we are returning actually this thing right here if we were to remove that we were get into trouble because the compiler would tell us that we were expecting a string but we found a string slice as you remember this is a string slice or。

Sting as well sometimes they refer to a string， but in this case a string slides to differentiate。

 so that is what happens here and let's get things back into work in order and that is how we have our LibRS。

 nothing in MaineRS and we're starting to build out our Cite utilitiess library projects。

 So I think this is good enough and we'll take a look at how we can make these a little bit better。



![](img/31f6d5895dd0b9944d5f27f3a9ed0523_3.png)