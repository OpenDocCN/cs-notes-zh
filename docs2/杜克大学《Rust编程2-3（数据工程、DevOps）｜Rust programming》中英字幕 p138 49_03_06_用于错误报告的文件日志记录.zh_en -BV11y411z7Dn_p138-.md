# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p138 49_03_06_用于错误报告的文件日志记录.zh_en -BV11y411z7Dn_p138-

If we go to Lib thatRS， we have error which will definitely be printed out。

 but we could have debug information right like if you want to run a command several different times you could have so we could actually go here to。



![](img/b4f5f9b240e6a277ba8e711a5fb3478d_1.png)

Log and import debug。 And I'm not gonna import the other ones。 I'm just going use debug。

 So we could actually say， for example， one that would be useful。

 It would be debug raw command and and put put it in there， right。

 so we can say what's the raw command。 And actually， we don't need to do it this way。 We can say。

We can say it this way， and we can add our semi colon there。 So why would this be useful。

 Remember that this command is going to get split。 It's going to get split right here。

 So if we were able to， if we wanted to make sure that the splitting is done correct。

 we could add an R Dbu here， could say。Raw command。Raw command split rather right command split。

 we could say arcs like these。 and hopefully that will print correctly if the vector is allowing us to do that。

 So that is good。 And then if we're forcing if we're forcing these to be be a log file go to a log file will have those captured in a log file。

 and also these ones， right， so I'm going to have that debug and I am going to go here and say once that prints。

 I want to make sure。This is going to process the output right， and that's going to split。

 We could also add an narrow one here。 we could say oh this is this is not very well formatted。

 we can say debug， we can say skip in line。Not only that。Skipping headerline looks correct。

 So what am I doing there， am I in debug because I want to make sure that I'm capturing these situation。

 So more informational stuff。We can see in our debug here。ASping line that is empty。Right。

 and because there's no length there and I'm adding more information。

 more awareness instead of having to debug this line by line。 Finally， I want to go to the run Df。

 I'm going to say that's the command that' the output If to output is empty， we can say。Again。

 but we don't necessarily need to say error， but sure， you know， let's just try it out。

 No but from command and we can go here and see where else we can add more logging information。

 Let's see pathlan， there's nothing。 we were getting a null， but I think this is this is good enough。

 So now if I go to the terminal and I clear this。 and I run。Our， our little file here。 We will get。

 We should be getting more information here on our RDF that log。 So we will run the command。 we。

 then we split that up， right， And then we got the skipping heater。

 So let's take a look if we can increase， if we can increase the。The vervasities。

 I'm going to say dash dash help here。 and let's add debug。

 and we can say dash dash debug and then info。Okay at these and then we're getting now we're getting these to the we're getting these to the terminal。

 but remember we were using before the log file so you can have that flexibility if you want to mix that I personally prefer a tool that will output exactly what I need like these to the terminal without cluttering because if an our system is consuming that Json that J is going to be broken because of these So I tend to do enable the log file always and just have a system that will actually produce exactly what I need right here all of this output from cargo is is something that doesn't come。

When the tool runs， but that's just like when because I'm building it and running it right after I build it。

 but like the tool will just output these right here。

 unless there's an error in which case it will produce that information as well so there you go that is things that I recommend when dealing with errors dealing with accept on that exceptions but errors from running external commands and how you can make it robust by adding that information to a log file especially when other other tools are going to consume this output。



![](img/b4f5f9b240e6a277ba8e711a5fb3478d_3.png)