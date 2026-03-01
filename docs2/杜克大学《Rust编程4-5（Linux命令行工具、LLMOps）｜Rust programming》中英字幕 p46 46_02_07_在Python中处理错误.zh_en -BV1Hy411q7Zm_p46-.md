# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p46 46_02_07_在Python中处理错误.zh_en -BV1Hy411q7Zm_p46-

Dealing with errors in Python is usually done in a try accept way。

 Let me open up the terminal so that you can see something that might be like it's an exception。

 I'm forcing an exception on Ls plug in my system。 So our plug pi Vda1 should cause a big error。

 So there we go we still have our login messages right there now we do have this big big exception。

 So what it is behind the scenes and I know exactly what it is because I made the change。

 I'm forcing the change is that I'm adding invalid invalid J。

 So if I go to the Expr and I go to utility that pi I know that that is coming from let's take a quick look if we get the actual line here。

 So utility that Pi line 33 in run Ls block so line 33。



![](img/c5cea6103232ad5e285777c26aa08de0_1.png)

Is right here。 So this Jason。 So one way， one way that is very common in Python。

 and actually for people that are just trying out Python， that will do something like this。Except。

 bear accept and say， you know， print。There was， there was an error。

And then they eat up the exception and then and then they try to figure out how to make make it work。

 But is this is problematic because then devices is not going to be defined， actually。

 I can show you very quickly， if I run this again and I'm gonna close the final explore。

 we have more room， you will see that devices in reference before assignments。

 we're getting into all kinds of different trouble。 This is not not a good way。

 even if we were to say except Jason。De code error。And we then we define devices as。

 I believe this one's an empty list and we do that。Then well。

 we were we're not import caseson deco there。 so we can， we can try to。Try to actually say exception。

 try to be a little bit more specific and then run this again。 there we go。

 So let's make this a little bit bigger。 let me clear these。

 run it again and we get now these So there was an error What was the error what we don't know and then we get a none I mean this is this is all kinds of bad and is' very poor error handling。

 the reason I'm showing you this is because I wanted to show you what incomplete or a nonusful way of dealing with errors is just like what I just did here。

 which is accept exception。 Now trying and catching is not bad there's ways that we can actually do this better and the logging facility has the ability to log those error So we have here or log in and so our logging facilities and we can actually do this with a thing called。

Log that exception。 we can say we weren't able to process the J output。Right from LS block， yeah。

 sure， and so we can do these。And you might say， well， whats what's the difference， well。

 let's take a look at what happens when we run this in the terminals。 I'm going to say block pi Vda1。

And。These。These sts back。I is actually login， it's coming from the login if we do if we take a look at block by that log。

 the same thing will happen， you will see that the traceback was actually captured here。

 so you start seeing these facilities where yes you're doing a try accept。

 but you are able to capture exactly is what is going on。

 instead of just printing and eating up anything because once once you say something like trying catching the exception。

Then then you don't know what the exception is， right， some folks do accept exception as error。

 and then they do print。Then they do a nest string， they say error。

 that's the error and and then they're good to go and then they say well this is the error yes。

 but this is the way of porting over the error exception to a string and doing that actually we can try it out。

 toggle the terminal back again run block p Bda1 and this is the error right here so。This is。

 this is slightly useful， but not entirely not entirely so because what we want sometimes is actually the whole exception。

 So this is one way of dealing with errors that you can make it make a good and actually we can we can do we can be explicit。

 Of course，100% being explicit counts and it's a very good way so we can say we can。

From J decoder import J decocode error， and then we can be as specific here and we can say accept。

Jason decocode error and then we don't even need to do a error because we can actually just not print it out and log the exception and then set the devices to an empty list Now like if someone this has happened to me when I do reviews in pull request in production environments in production great code that someone says like wait wait a second like you're catching JasonO Decode error and then you're putting a message what's the error you're not logging and yes。

100% I'm logging and I'm telling you exactly what it is because log that exception will actually take care of that when we toggle the terminal it it is right there So the message is right there。

 there's no need to do any more processing unless you want to like you can 100% try to always make these things a little bit better and try to to be more useful but dealing with errors in this way is1 x。

Excellent， excellent way of trying to trying to do more things。

 And you can actually add more log messages here。 You can see like log error。 we had。

 we had issues with。The output， and we can say log that error output。Was。And we can do it。

 We can do it this way。 So we're， we're actually。We're actually， let me get rid of that， that quote。

 And then we can run this again and toggle the terminal and。Run block5 Vda1 and output was this one。

 So if you see well， I have the new line there， but the problem is that I added in an F right here。

 so you can still be very useful adding more sprinkling more useful information when there is issues and you can even have this step further by just adding all of these stsbacks and exceptions to file and not necessarily to to standard error if you want to kind of like keep it clean in the terminal and have all of those extra information。

 the debug information or error information rather in the file system So there you go。

 that is a very solid way where you can add an error handling strategy to your Python application with logging。



![](img/c5cea6103232ad5e285777c26aa08de0_3.png)