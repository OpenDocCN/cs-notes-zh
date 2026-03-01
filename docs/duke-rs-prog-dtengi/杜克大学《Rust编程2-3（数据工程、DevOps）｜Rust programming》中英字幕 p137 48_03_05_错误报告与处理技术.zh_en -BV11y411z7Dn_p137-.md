# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p137 48_03_05_错误报告与处理技术.zh_en -BV11y411z7Dn_p137-

![](img/5f438d30788ea91ba1a728bd8eadf7fc_0.png)

Dealing with errors when we're wrapping other external commands or other system commands is crucial to have like a solid。

 robust strategy。 One thing that you want to have absolutely all of the time is having a way to understand。

What happens when there is a failure So a couple of things that I recommend let's start with capturing the actual command that was run sometimes in this case probably not an extremely good one。

 but sometimes when we are doing commands with many flags so if I scroll down here we're just using the Df executable to get only these output but if we were passing several arguments and even more so if we're allowing a user or or we'll allow him to programmatically add more flags and more options to change how this is produced that might cause an error and when that happens we don't only want to know what is the actual error。

 but we want to know what was passed in。So the actual command that is being executed so if I scroll back up that actual command is is very important now that is one but also of course capturing the output of what was the error right so we've talked before about the path and having the correct path and techniques that you can do for making sure that the path is correct so if I scroll down here and I put an invalid。

Let me put an invalid path here。 So I'm going to say。Slash invalid。Right to force to force an error。

 And if I go to terminal。And I clear that and I say cariggo run but let actually trigger these with info。

There we go。 So this is this is very useful because when I'm running and cargo run dash dash means and I don't think I've mentioned this before is that we're separating the arguments of the executable that rust is creating with cargo run so cargo run has its own flags and this double dash right here would allow me to passing arguments just for our little commandle tool called RDF all right。

 so once that builds we have a couple things here we have。Command failed invalid IF。

 like so this is telling me what the actual command was。 perfect。

 So if I had more arguments and more flags， those would appear right here。 So I would have like。

 if I'm debugging this， I would have like a very good solid way on where to inspect that and and where to look at。

 Al right， So the other thing is that the actual error shows up here。So this is very good。

 but then we have a mix of things right we have something that printed to the terminal。

 we have log output and we have the actual output from R2 right so if you remember if I close these and I I fixed this in path and I save it。

Toggle the terminal。 Run the command again。 What I should be getting is a production of adjacent。

That is very nice formatted with everything that I'm looking for right so slash dev slash right there。

 the tool that I have here is made so that I can pass in a specific mopoint and get that information so let's try with that slash only。

So I can say slash like these and you will see that I am going to be getting just that double one right there。

 but let's try something that is about。And then I'm going get a null so these are situations that you need to account for and you have to have some robustness built in that will allow you to understand where where these things where where these outputs might be produced from so let's go back to the code and let's start not cleaning up but actually doing a little bit more a little producing a little bit more nice output when things are failing so let's start with the command failed I don't like to have these separation so one thing that we can do here is we can this is fine to say command failed and what was the actual command but one thing that you can do is implement a file login strategy here these command link tool has it optional and I'm going to show you where that happens is。

A。A flag to enable the log file。 So if we pass log dash log dash file。

 that will enable that flip a switch and it will enable log into a file。

 you can make this 100% enable all of the time。 And when that happens。

 you can actually set a log file that you will will log to a specific location that will be out of the way。

 So a user won't see it populating its screen。 So if we if we toggle the terminal again and then say instead of running that if I say dash dash help。

That is the enabling log into a file if we run our embalic command again。B。

 not an em They will let's see， let's see what we can do here if we enable log log file this I will get a no if I'm do a less now we have an RDF log file。

 I think that should be empty。

![](img/5f438d30788ea91ba1a728bd8eadf7fc_2.png)