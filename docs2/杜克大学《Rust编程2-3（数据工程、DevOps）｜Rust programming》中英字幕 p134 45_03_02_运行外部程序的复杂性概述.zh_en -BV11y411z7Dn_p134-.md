# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p134 45_03_02_运行外部程序的复杂性概述.zh_en -BV11y411z7Dn_p134-

![](img/3ef405d74d5fcc0ccbacc302fe622967_0.png)

There are many complexities in running external programs in general。

 I would say whenever you have a programming language like Ru and thisapply certainly for other programming languages as well when you have something that wraps on our thing there is a series of expectations and I'm going to run the DF command here。

 I'm on an Apple computer you will have somewhat different output if you have like a Linux machine or something else and here we have the output of the command here and the idea and what I want to present to you right now is that we can have systems that rely on external command line tools like DF that are reporting on the system。

Now there are crates， there are libraries that are doing this。

 but sometimes those are not enough and you want to have some specialized reason that allows you not allows you but forces you to go through this approach and this is what I want to cover today I want to show you some of the difficulties on doing this in one case for me it that I had to provide compatibility with older systems that had formatting that was somewhat different in this case this is just the app but in my case a few years ago it was with a different command line tool that a system command line tool that I had to rely on and I had to provide a glue。

That would normalize the output regardless if the system was five years ago。

 five years old or brand new。 All right， so that's what I'm going to do today I'm going to focus on output that is similar to this and we're going to take a look at how that is now when you are working with these types of systems and this type of strategy rather than you're wrapping up something like Df again。

 then you will have to make some decisions based on your use case。

 I'm going to close here the terminal and I'm going to show you first I'm want to show you main NRS and it is going to accept a path and optionally optionally because it's going to the photo and empty string。

 So what is it that is going to do it is I'm going to scroll all the way to the bottom here it's going to call to this library and going to produce。

Jason Al。So the library I'm going to go now to live that arrest。

 I'm going to scroll all the way to the top and this is the type of parsing that we're going to be doing now I'm not going to get into details just yet as to how is this going to work。

 however， what I wanted to show you is in part of the complexities and the decisions that you will have to make is what happens when this command。

Gets an error or has something that is incompatible because you will have to do some parsing In this case this wants to provide a J interface。

 adjacent J output it will parse every single entry here and it will provide JN output So what happens when things are not quite working you will have to account for that In my case in the past I was of the opinion and this is parsing the output there's an R function of running the command。

And that is this function right here So in in this function right here you have two possible outcomes either you're going to get a correct a correct result from running the command or you're going to get into an error so you have to make it' almost like a business logic business decision where you're going to have to say is an error that breaks my program and doesn't allow anything else to continue the right thing to do or is it unacceptable to me in the password in the system that I was working this was completely unacceptable so I had to continue and the way you make that work is by allowing other colors into specifically this function that is the run command that run external command。

To be able to deal with the fact that perhaps the output will be empty。 And if the output is empty。

 they just won't do anything。 However， if the output is broken or if there's an interruption。

 then things can get tricky。 Now， that was correct for me at the time。

 But your strategy might be different， you might want to say， you know what。If there's an error here。

 this can continue and we have to break execution。So those are some of the things that you have to take into account and one last thing that I want to show you is the parsing The parsing is definitely something that might make things complicated。

 I am relying blindly on these output and I show you initially this is kind of like the Linux output I show you initially the output from my MacOS system if I toggle the terminal you know these looks very different。

 there are many more columns so parsing techniques have to take into account for differences in systems and you might want to if you're going to let that tool run in different systems you have to guard against the possibility of completely broken parsing that might put these values in the wrong fields that and that could end up being catastrophic and here like I told you this is consuming each part and coercing to a string。

So that it captures that information。 Now， in this case， I only want to focus on the Linux output。

 but there are definitely other strategies that you can take into account when you're pars for different systems。

 So those are some of the difficulties that you may face and some of the decisions that you will have to make once you start calling out to other executables in your system。



![](img/3ef405d74d5fcc0ccbacc302fe622967_2.png)

![](img/3ef405d74d5fcc0ccbacc302fe622967_3.png)