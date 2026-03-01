# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P63：63_03_04_演示：使用枚举作为类型.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/a8a2250bfddfb4e009a48c68263e713b_0.png)

Inums in rust are a custom data type。 That's what they are。

 And they can hold all kinds of different information。 In this case。

 we are looking at wine regions and we have several different wine regions that are variants of the wine regions inum type So what are we going to do here we're going to use it explicitly as a type which we haven't done before。

 So we defined it here from line 10 to line2 and we have several different onesre in order the curly underlines because that means that we're now using all of the variants and that's that's fine for now。

 So let's take a look at what we're going to do here with the main function。

 So first we are going to use it withstructs so。Both of these are going to use thestructs。

 but you can see here that we're passing in a name and then we're using a region。

 So what are some of the things that inums allows us to do。

 So if we go back and look at the winestruct over here。

You can see that we have two fields first is the name field which is going to accept a string and then we are going to accept a region which requires using a wine region type so what does that mean instead of like relying on passing in something like if we were to comment this out if we were saying this is a string as well and that would require you to type in all kinds of different strings like Napa Valley and you know that's prone error prone and might get you into typos you you might spell it like that and all kinds of different pro with strings。

Now that is why inums are pretty useful because it allows us to be very explicit as to what what type of data or description of thestruct of the field were going to have and in this case we are saying anything that comes from the wine regions is valid。

 so how does that look like if we go back to our main function over here， sorry for the scrolling。

It means that we can be very idiomatic in rust。 it is a very idiomatic way of saying hey。

 this is the wine struck， this is the name and the region is a Bordeaux so that makes sense and this other wine is going to be a Barrolo from Italy and the wine region is one from Tuscany so this variant will let me very nicely describe what we have so if we run this。

Let's see we're going to have the output right here on the bottom。

 W1 is a chatau marro from Bocado and wine2 is a barrolo from Tuscany perfect。

 So that is very nice I really like this feature for us where we can use types withinstructs but there's one more way we can do things here。

 we can make it a requirement for function。 so we can say， hey。

 I'm going to call a function and what we're going accept is a I mean this is a very simple function that is mostly not doing much。

 but is going to accept a w which is a wine region and that is going to come from the wine regions and numerator the inum wine regions。

 So lets let's call it out and see what we can what we can get。

 So instead of printing all of this out。 let's actually。call。

Call our function here supported regions。 And we can we can actually say 1，1 region。

 or we can say something like supported regions， and we can。We can say wine。Wine regions。

 and we can save say， for example， that Rioha， yeah， that's fine and see what happens。

 So is what is the problem with doing it that way。 Well， it's not a problem。

 It's just that I have extra piece in here and I need to save it so you can definitely pass it like these。

 Now this is kind of like silly because if I'm using wine regions doubleco riioha that is you know not very meaningful。

 but it just shows you that you can actually pass these parameter because it accepts the types。

 So now if I run it we'll say hey， Bdeaux is not supported but Rioha is supported。

 So you can you can do a little bit of mix a match with the actual match a keyword right here and I make it make it work really。

 really nicely So so that's it for using using inums as types。

 we saw how we can add it as part of abstractstruct and make it really nice and really descriptive at the time where we're。

Decribing these data structures， and we can use match。

 we can actually require it in inside functions。

![](img/a8a2250bfddfb4e009a48c68263e713b_2.png)