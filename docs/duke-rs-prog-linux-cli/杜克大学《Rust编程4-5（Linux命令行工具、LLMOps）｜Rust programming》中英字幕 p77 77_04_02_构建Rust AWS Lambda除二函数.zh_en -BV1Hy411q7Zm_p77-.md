# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p77 77_04_02_构建Rust AWS Lambda除二函数.zh_en -BV1Hy411q7Zm_p77-

![](img/55642423ac8c2bd72cab283dde2d0389_0.png)

All right， here we have a serverless step function orchestration with a couple different Lada functions。

 And I'm doing this with a rust。 I'm going to go ahead and divide。This function by two。

 So I'm going to go ahead and build a function that takes a payload and divides by two。

 kind of a simple function here。 Let's go ahead and get it working from scratch here。 So first up。

 let's go ahead and say cargo Lambda new， and we'll call divide。



![](img/55642423ac8c2bd72cab283dde2d0389_2.png)

Bye2。Great， we're going say no， no， get this thing cooking。

 now that I'm going to go ahead and get into there。

 And then what I'm going to do is I'm going to C P。A make file that will help me out here。

And then all I need to do is get into the code here and just make a few tweaks。 So first up。

 what I typically do when I'm building a new lambda function is set my intention。

 So let's go ahead and do that。 We'll say divide by two takes a。Total and returns calculation。

It returns half of it as。Calculation。Calculation。Cculation， okay。Right， perfect。 so let's get hit。

 let's go ahead and delete this here， so the request is actually going to be a total which is a number rest figure that out for me。

Then for the response， we're going to do， we're going to tweak these fields and we're going to make this calculation。

 So let's go ahead and do calculation perfect。 And then this is our main function here。

 Not much to do， actually， because all we have to do is tweak the payload here。

 So we're going to go ahead and call this one。Total divide by 2。 And then for command。

 we're going to change that to calculation， and we're basically done。

 All I have to do is pass calculation in here。Perfect。Now。

 to test this out is going to be pretty easy。 I'm going to go and do a split screen。

 Always a good idea to do a Li。 So let's go ahead and do a make Li。Oh。

 we have an issue here with a li。 Let's go ahead and fix that， replace it with calculation。 Okay。

 so we don't need both。 We just need calculation done。Soft。As they say。

 and we can actually format it as well。And then do L perfect。 Now， let's go ahead and watch it。

 So we'll say make watch。And this is going to run the watch command inside this make file。

 which is that。 Now， for the invoke， I'm going to tweak this so that it is。Gonna be。E。Total。

And then it's going to be 10。And we just get rid of the rest of this。Perfect， save it。

Move this over a little bit。 And we just say， make invoke， make invoke。

Now it's going to go through here and wait until this compiles。There we go。 No problem。 Now。

 it's going to be trivial。 Let's just go ahead and kill this to get the rest done。

 which is let's go ahead and build and deploy pretty easy。 We can just say， make， build and。

Make deploy。All right build it for arm 64， which is the cheap version of compute。

Go ahead and deploy it。Perfect， and then。Once this is done， we can even do remote invoke。

 We can even start tweaking that right now， because we can say。Divide by 2。Divide by2。 and we just。

 in fact， just copy this。Let's see if this works。And if we're done。Make invoke。Make Eos invoke。Done。

 so trivial to from scratch， but a new lambmbda function using rust。



![](img/55642423ac8c2bd72cab283dde2d0389_4.png)