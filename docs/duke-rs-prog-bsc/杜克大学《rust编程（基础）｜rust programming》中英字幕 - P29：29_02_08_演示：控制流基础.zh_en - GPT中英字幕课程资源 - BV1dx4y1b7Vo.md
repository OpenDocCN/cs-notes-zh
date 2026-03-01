# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P29：29_02_08_演示：控制流基础.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/9a0998f52b68d7bdb65aa1621ba318d2_0.png)

Now let's work with the basics of control flow in rust， as always。

 we'll have a main function and we'll do some simple execution here with Vs code you'll see that rust analyzer allows me to have these run or debug control here。

 Now what do we have here， well we've assigned the variable and then we are doing simple if or else you can see here that we have the curly brackets。

 we've mentioned curly brackets before those theote the scope。

 So this means that all of that will be scope to the main function。

 but what' the deal with these curly bracket here and this other curly bracket。

 Well those are also required when we are doing these if or else those also can be in line like can be in the same line。

 but were formatting。According to just regular formatting with rust code。 Alright。

 so let's take a quick look at what we have here and let's just run it。

 Now if you've been paying attention， this will not compile and we won't be able to run Do you catch that。

 Do you know why。We are missing a very important character here， and that is the semi my colon。 Now。

 the compiler is pretty friendly。 Let me open up here。

And what we're getting is a very good error reporting。

 we said it says that it expected a semi colon but found that keyword F tells me what the what the file is and what the。

What the line and the column like this is line number two and column 23。And it tells me right here。

 it's like， hey， you should add a semi column so let's go ahead and make that change。

And save that and try to run it again Good， so we are able to run it and no problem。

 Now let's take a look at what we have we have proceeding and then tall so let's just go clear that and we have here a let proceed equals true let's say a Boolean assignment there for that variable and because that evaluates to true if proceed。

 it'll say hey this is proceeding or wise nope not proceeding so you could actually say it like that and then change it and then run it again。

And you will get not proceeding as expected。Now that's the first portion。

 but you can also have all kinds of operators like greater than in this case we're defining height。

 we're saying height is 190 and if the height is more than 180 we'll say， well， that's tall。

 else if which we're not using above well say well if the height is more than 170 we say average。

 otherwise we'll say short which is I mean this are just made up the assumptions of a height。

 but it's all good now， the difference from above is that we have this else if condition right that were not using because we're just using a plane else。

And so the way this is going to work is we're going to evaluate this first。

Or why we going to evaluate that and if none of those matches we'll get this block right here。

So we can actually change these and say。Change that logic as well。 And we can run it。 And， you know。

 we'll get different results here。 We're getting average right there。 So there you go。

 It's very straightforward to have some basic control flow in rust with it's actually pretty similar to other programming languages。

 And this is a very straightforward way to handle logic without getting into over really complex statements。



![](img/9a0998f52b68d7bdb65aa1621ba318d2_2.png)