# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p131 42_03_05_使用Rust解析日志文件.zh_en -BV11y411z7Dn_p131-

![](img/f5d2f128d62cf3aab66871b7dd14e6fb_0.png)

I have a project here that I want to show you which will allow me to essentially parse a log file now I'm not going to write this from scratch but I want to show you this is the main that arrests I didn't take that time to actually add a Lib arrest or other module so I'm going to leave that like that and what I'm going show you is like I'm going to scroll all the way down this is the main domain function right here and we're taking as always just a single a single argument which is going to be a path and that path is going to be a log file。

And this is going to parse a log file now we've seen already structure login and this comes into play right here。

When you want to have like a ultra fast。Implementation that will parse a log file so that you can do analysis of course you can do grab and a and find and all of these Uni tools。

 but whenever you want to do something specialized a a ho that is super fast comparable to those Uni tools then you can use rust 100% and let let me show you a little bit about the logics I'm going to scroll all the way up here and I'm going to read with the read buffer so this is going to take a path and we're going to do specifically when I count for errors and every hour of the every hour of the log file actually let me show you the log file。

If I do clear and I say tail bar log install log， which is something that comes in my system like I have an Apple computer。

 but you will see a couple of things First the date， the timestamp。

 that's the time 730 almost the name of the computer I guess I'm guessing this is the demon and a PD perhaps and some sort of like message and I'm interested like and this is a business business logic。

 I'm interested in anything that has error So in this case create and persist dashh finished error null I mean that's pretty terrible pretty terrible message there let's let's look at。

Let's look at more let's look at more stuff in here。 We can say grab air in bar log install。

 And there's， you know， plenty， plenty of stuff。 A lot of this is just very unreadable。 Well。

 this is all full of new lines。 We can actually do better than that。 Let's actually。

And I know this is not very useful， but we can try to wrap error these and then we'll have better formatly all right so fail to evaluate local authentication and we have like the error so like right there that's our error and that's what we're looking for So every single line might might or might not half an error so what aret we trying to do let me close these or we're trying to do we're going to have a regular expression regular expressions are horrible theyre hard to understand we are trying to parse and this would be useful if you had like some sort of a comment on the date and the hour and you can see here this is hour minutes second and this is like an extra extra thing I think it's for time zone。

And we're going to specifically look for this word。 This is hardcoded， This is not good。

 but it is highly specialized and very fast and still useful。 So why not spend some time with it。

 Now the cool thing about this is that depending on if it's compressed or not we're going to still read from it regardless So here we have an implementation where we're using match and match allows us to say。

 hey， if this is Gsped compressed then decompressor GC file and create a new a new buffer with a buffer reader。

 So decompressor that is getting decompressed right here we'll get ready no problem otherwise just create a new new buffer with with a file and then we'll read the lines progressively whenever we're going to use match again and whenever there's a line if it'。

😊，line we're going to consume it。 No problem or was we're going say， hey， this is a problem。

 That line is going to get assigned right here and that is going to be used right there。

 So we're going to say， hey， let's just start extracting this is where the regular expression comes in。

 We're gonna start extracting I'm going gonna say well what what the timest。

 this is the timestamp was the date and this is all based on the capturing on the rex。

 So the regular expression is going to be separated in captures and we're going to say， well。

 this is the date。 this is the hour this is the format。

 Now here's the interesting thing is that we're going to say for every hour right for every hour。

 like it doesn't matter。 the timestamp for every hour I want to know how many errors werere seen So basically we're in an error rate per hour So we're going to have a message that says。

 hey I'm seeings this is the error account if the current hours so it's going to traverse。

The log file is going to have many entries so if the current hour doesn't match the data hour that I'm currently parsing that means that it changed now it's time to do some reporting otherwise set it to zero so that the counter reset for the hour and at the very end show me what is the total error entries well actually this is capturing the total and error entries but at the very end tell me what the total error account for the current log is alright so that was a mouthful let's go back to the terminal let me clear。

And say cargo run bar log install log。 So I'm going to do that and there's a lot right So you can see here our 17 so 5 pm。

 I had 85 errors and then everything goes back to once and zeros 41 right here at 8 pm on August 25th。

 So that was pretty high 41 again， you can see that this is fairly consistent。

 you see a pattern hour number two hour number 20 let's see if we get on our see our hour two on the 29th 43 errors on the 30th。

 So you start seeing sort of like a pattern and here 9021 errors total for that path。

 Now I did say install that log but there is in bar log there is let's see if there's an install log。

 Well， there's no install log。It's compressed， but we could try。

We could try and see if this compression will work。

 yeah it won't work for the system log because that has a different type of formatting。

 but you can see this is where the problems come。For。For different formats， if we say tail bar log。

 Wifi log， you will see that you know it's no longer the timestamp no longer matches。

 so this is not going to work very well so。What are some of the advantages？Very fast。

 We're just being able to do very fast processing here of all of those logs。 Now， could you。

 could you perhaps do something like these with regular unique tools， maybe。You could try to do this。

 but you probably would be looking at a batchsh script and that would be difficult to maintain and it wouldn't be as fast as doing this with rust I think rust will have benefits deploying a batchsh script to other systems has all kinds of different problems by itself rusty will be a little bit more straightforward so highly recommended if you need something highly specialized to deal with a lot of logic and have a business business logic that you need to that you need to abide for by or abide by and like in this case you know error account and I want every hour you know imagine if you want this in Json output like you can 100% do that no problem and this is just what 74 lines 75 lines of rust this is not bad and the only external cr that we're using is F to which is implements。

A GC decoder perhaps you say well I don't care about compressed stuff compressed files I can just want to plain text files then this wouldn't even be needed So there you go that is how you implement。

A tool that can read andpartse log files with rust。



![](img/f5d2f128d62cf3aab66871b7dd14e6fb_2.png)