# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p16 16_01_08_管理输出、日志、错误与恐慌.zh_en -BV1Hy411q7Zm_p16-

![](img/6d9bfc3e5dc2f9ae67fef7a37d5aebe3_0.png)

So far our tool， our command line tool in breast is assuming that everything will go well and it will cause actually lots of problems if things don't quite work。

 we can see there's a couple of things here， this one in this expect。

 this will cause a panic and this fail to execute command and will show up similarly if I keep going around here。

 this Json serialization will also cause a panic if there's problems with serializing。

Continuing down。Actually， there's a Nn wrap here。 So this one。

 if block devices doesn't exist in the output， it will also cause a panic right here in the unrap and if I scroll all the way down here will again have another another panic with device not found message So lots of panics and as I mentioned。

 panics are okay。 if you' just want to have some demo code or some example but not so much with production grade code。

 I mean， you can still use panics imp production grade code and we want to absolutely 100% panic and stop execution of everything with a completely unrecoverable error that's fine。

 but is not very common and certainly something that is not super common here not that is not common here。

 but it's not something that we want to do here。 we want to continue we want to deal with this errors provides some message output right now if。

Do cargo run with a block device that doesn't exist？

We get we get a lot of things that were are not necessarily useful， like thread main， panicked。

 fail to execute command， OS code， I mean there there's a lot of stuff here that is not very useful for a user。

 So let's start in making it making it a little bit better I'm going to remove this invalidic command I'm going to clear run again because there's a narrow one。

At the very end， if I run these device now found also causes a panic so these are the two situations that we want to make a little bit better。

 so let's start fixing them up so the way we're going to do this is first by stop the like this last message this last panic here we don't want to do that I think it is perfectly acceptable to return an empty Json here。

 we're going to have to pass in or return a value from third JN So instead of panic in we are going to say we're going to say here I want to remove this and when I use the third JsonN library。

And no， we're not going to return a null。 We're going to call this macro and return。

An empty object there in Jason。 So now that we do these instead of like saying the device now found。

 which may or may not be true， we're going to be friendly for any other tool that might consume these libraries。

 I'm going to reset that run SDB 33。And now the output that we will be getting is an empty object。

 There's nothing found Sb3。 So this implies this result implies that there's nothing found。

 So there's no need to panic。 So this is already much friendlier。

 if you' are using using this tool in a CD system where you don't necessarily need to parse errors。

 but you want to actually have something to deal with。

 So now some code that relies on these result and say well。

 I'm going to look at all the block devices， but because this returned an empty object there's no devices that's implicitly saying nothing is nothing。

 nothing was able to be found after running that command。 Allright。

 so that's one thing that we've fixed one panic that we fixed。 let's remove these。

Remove these file Exper and scroll and deal now with this run command， the wrong command。

Definitely can cause some problems。 So if I go back and make this and in nonex nonexisting command and I clear this and I run。

 it will cause issues that we have to deal with。 we're not going to change the return value here。

 it's still a string。 we're going to leave that assay string and what I want to do is when this fails。

 when this output fails right here。 What I want to do is。Capture。

The output of that failure command capture the error if it fails。

 printed out to the terminal so that we can have that right here。

 but continue execution so that the function so that we don't need to necessarily deal with a cascading or a bubbling up of errors rather from the run command to the run LBk block function to the main function passing errors and changing these definitions all over the place because we have having to return an inum that were or is a value or an error。

 so let's get working the way we're going to do this is by creating a match on the output so I'm going remove the expect I'm going to get rid of the expect and that's going to go out and now。

I'm going to start getting all kinds of problems here because this is going to be。

This is going to be a problem because the expect is not there。 So I'm going to now say。

The output is going to be there。 And then I am going to， I am going to actually。

 let me comment this out to get it out of the way， but leave it there as a reference。

 This is something that I tend to use when I'm working on code。 I just comment out the code。

 So I have it there as a reference while I start writing。 So I'm going to do a match。

On the output and this is certainly something that we can can we can do here。

 So this suggestion from compilepit looks almost exactly to what I want to do。So I'm going to。

 I'm going to accept that suggestion。 I'm gonna to make some， some changes。

 So let's let's take a look here。 So here we have let's standard out equals a string U TF 8 lossy。

 So this line is okay。And we're going to say SDD out to string is fine。

 and the air condition is no not going to necessarily going to use these。 And we're going to print。

 We want to print exactly what is going on。 So I'm going to say print line。Or actually。

 we can say E print line。 And I'm going to say there was an error in what is exactly the error。

 So I'm going to save these。 And also at the very end， I'm going to make an empty string。

And going to return that if that happens。 Okay， so what we have here。

What we have here is an error condition and that we're missing。There you go。

 So we're missing a bracket right there。 So now we can remove this comment。

 Let's go through a couple of the changes that went in here to try to figure out what were the actual changes now。

 the editor is not complaining。 Everything looks okay to me。 So we kept the return value。

 which is a strain。The arguments are these ones and then we're saying hey。

 run this command and when you're done let let's poke around what we got。

 if we're getting correct execution of these no errors。

 then do the par parsing but making it UTF8 string and and then make that string and return that because there's no semi semicolon here。

 this is going to get return otherwise if it's an error capture the actual error。

Pnt that to the terminal that's going to go right here and return an empty string。

 So lets let's run this again and see what happens with run Sb 33 okay so we've made a little bit of progress we got a we got our our string printed out here or error like no such file or directory OSs error 2 that's fine。

 But then we got into another panic。 So what what is going on well we are getting into trouble here because because we have the output is now an empty string it is not valid Jason So when block devices。

 let's see this should be a line 24 So this line right here will get into trouble because there's there's no valid Jason there。

 So what we can do here is action。do an if condition， if output。Es empty。And then we can。

 we can definitely return an empty Jason and then move on。 So now let's clear this again。

 cargo run S D B 33。And we're getting closer to kind of like what I would expect。

 we're getting a printout of the actual error， and when you do these。

 you can actually start going a step further where you can send certain things to standard error and certain things to standard out So that way when you're capturing output from a command line tool like this one。

 you won't get into trouble。One last thing that is not necessarily like super， super nice to。

 to have here with print statements or print print line statements， but it's still useful。

 And I't want to add it anyway。 I'm gonna add here a。

Command failed and I'm going to add the actual command here。

 we can actually do these and include that include that in the print lane and I' going to add a semi there。

 and now when I run it I'm going to have a little bit more context what's going on。

 So there we go it tells me that the command failed。

 And so now I have a little bit more context right so this is the command that failed。

 the error was this one and the output is going to be an empty object。

 So there you go there's a couple of things that we can do here for dealing with errors and not just implicitly expecting that everything just going to work and or using panic calls everywhere for code that is supposed to to work very robustly especially for a production environment。



![](img/6d9bfc3e5dc2f9ae67fef7a37d5aebe3_2.png)