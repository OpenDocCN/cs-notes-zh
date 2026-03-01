# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p09 09_01_06_管理输出、日志、错误与异常.zh_en -BV1Hy411q7Zm_p9-

So far， a small command line tool doesn't do any error handling。

 We have our main function here and is running blindly or trusting a lot that run underscore LS block will work without problems。

 but there are certain situations where we might get into trouble。 If we go back to our utilities。

 We'll see that we're calling Ls block dash J and we're passing certain things here。

 that that might be fine。 Let's simulate a problem where Ls block is not installed in a system。

 I'm going to do this by passing here something that doesn't exist。

 I'm going to add our letter and then I'm going to open up the terminal。

 So because I did the setup that pi develop。 I still have my ability of running plug pi。

 which is still there。 So I'm going to clear that and I'm going。



![](img/3c9175124757508ab9b6fc44987710e1_1.png)

pass something like we've passed before block pi。 let's say SDD1。

 So I'm getting an exception at traceback an exception is raised in this case is file。

 not found error which you can see here at the very bottom and the error is like no such file or directory L L S P or L L block。

 Now that is kind of like what we should expect if L block wasn't installed。

 Now for a user having to look at these might be very intimidating。

 not very useful if we're seeing stuff like parts of the frameworks we tend to say， well。

 the tool is spelling it's got on the terminal。 So not good。

 let's try to work a little bit with this output and try to make it a little bit better。

 So the first thing we need to do。 Well I'm going to close this first thing we need to do is we're going to deal with the。

Exception， I'm going to go to mainda pi， and I'll show you a couple of things that we can do so we can do a try accept here。

And we're going to do accept now you have to， you have to be careful here because users or developers sometimes tend to do just accept exception and then do something like this。

And this is not very useful， right， Because if we go。

If we go back to the terminal and we run this then we'll say we got an error and I'm going actually remove remove these two examples from here and I'm going to say that and if I do plot pi SD the1 is like error like what's the error。

 we don't know right we caught absolutely everything the universe of exceptions of error is possible and we're just saying error so that's not very good so。

Let's try to be a little bit more helpful when these situations come up。

 So what we're going to do is we're going to explicitly catch file， not found error。

 And the reason why we're going to do that is because we want to pass in the actual problem that we think it's to convey something useful to the users。

 I'm going to say。File not found there。And we're going to say， and we'm going to go step by step。

 every， every change is going to make this slightly better。 And by the end。

 we're going to come up with something really nice and really useful。 So except on the phone error。

 we can say error。It is possible that Ls block is not around。 Okay。

 so if we toggle the terminal and clear this and run it again and like here。

 it is possible that L block is not around。 Okay， so this is more useful。

And we are dealing with a specific， with a specific exception here， which is found found error。

 We think that's the problem。 How about we include。As an extra， we include the actual。

The actual message of that exception。 So we can say to do that we can do except file found error as as these variables。

 So we'll assign that to error and we're going to do here a F string。And what we can do here。

 an F string allows us to put variables inside the string。And then we're going to say colon。

 and then we're going to say， we're to make sure this is a string。 and we're going to say this。

 And now what we can do is if we run these。Well get the actual extra extra message from。

 So we we think it is possible that else block is not around。

 but in this case it's not that is not installed right we have a typo So if we didn't know that we have a typo and we we thought like oh else block is not installed let let's check else block it is installed。

 How is it that this is telling me that else block is not around Well。

 bypassing the exception message now we're able to tell us like oh Alfredo had a typo here。

 So this is not quite correct。 So this is very good。

 this is very useful and we're making it better right So let's take this even a step further。

And we're going to use a feature from click the framework to try to go a step beyond and make it even nicer。

So what we're going to do here is we're going to use。

We're going to use click has a utility called E and click that echo is essentially the same thing as printing with Python。

 but it will allow us to do so safely around many different platforms。

 including Windows and prevent potential potential problems。

 Now that's not that interesting except that we're going to use something else from click that is called the styling。

 So I'm going to say click。That style。 And you're gonna see， you're gonna pretty。

 pretty easily be able to tell what I'm going to do。 And you can， you can get a hint there by。

 by the pop up that just showed and will tell us exactly what's going on here。

 So what we're going to do here is going to say error。It is possible that L block is not installed。

 And when I do here， I'm going to passing a foreground on F G。 I'm going to say red。

We'm going to save that。Daies away。And then what I'm going to do at the very bottom is I'm going to get rid of this whole thing because he's repeated。

Right， I'm going to print。I'm gonna say Col Col sounds good there。

 and we're gonna print the actual standard error。 So what is that going to do。

 I'm going to click here。 What is that going to do。

 This is going to be a red message and then we're going to print the exception right here。

 the exception message okay so let's try it out block pi S the1 and then we are getting a much much nicer more visual visually nicer error message that is even nicer for the user So great this is getting us very。

 very close， I think I want to do one last thing to this error handling and that is going to be using double boss。

 remember we have this flag over here if we do block pi dash help you'll see that there's this dash Vose So how about we use that flag in order。

to actually print the whole trace back back to the user。 So what we can do here。

 vervose is going to be a boolean it a true or false。

 So if we say we can say here at the very bottom here we can say if verbose。

We can conditionalize these， we can say race。So by doing these。

 we'll just rerase the exception and will essentially we will get the exception trace back back to the terminal。

So let's try that again。And I'm going to clear。I'm to say。Block pi S D1， that word， that's fine。

 but we're not passing the verbosity flags， right so I'm going say dash be here and then look at that。

 we are getting our full trace back。 let's scroll very slowly all the way to the top or almost all the way to the top and we're getting we're getting that we're getting that there。

 the message， the nice message there。 but user might be like I'm passingvo bevos。

 the vervose flag and I'm getting all this wall of text。 This good。 I'm getting the exception。

 This is useful because now I'm able to control the output。Now， you may want to have。

You may want to have these at the very end and there are ways that you could possibly have that。

At the very end， but this is useful because now depending on how you're passing the flag you you're getting the trace back or not。

 so there you go those are several things that you can do here to enhance the error reporting and conditionalize even more detailed error reporting with Python and using click。



![](img/3c9175124757508ab9b6fc44987710e1_3.png)