# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p41 41_02_02_在Rust中实现基础日志.zh_en -BV1Hy411q7Zm_p41-

![](img/1e0b10120f882e0c122278a582c41221_0.png)

Basic logging can be achieved in rust with a couple of libraries。 I've added those libraries。

 those crates here in my cargo that file， you can see log and end logger both are added。

 and these two work in conjunction to provide logging capabilities to our tool。

 So this is cargo that file and you can see here that this is this is right there。

 and then now we're going to go to main that R So I'm going to change here to main that R and start implementing that logging right now we if I scroll down here。

 we will see that we've been using print print line macro to start producing some output and it's all over the place。

 So the problem with printline is that。That it doesn't allow you to tweak the vervasity。

 So if you want certain messages to be at a certain level。

 this is not going to be possible right you might have options to debug。

 but you don't want to have like an if if else everywhere。

 So that's one of the many features that implementing login will will give you。

 So the first thing that we're gonna to do I'm going to scroll all the way to the top is to add like the capabilities of or some of the things that we're going to use for implementing login。

 So the first one is going to be level filter and that's going to allow me to set the right type of level for login。

And then I'm not going to use simple logger， I'm going to use something called M logger and a builder。

 So M logger provides me the ability to construct the formatting and everything that we want in log I think that there has to be a nice way that someone perhaps will come up with a way that unifies both there's also simple logging。

 but that we're going to use log and M logger for this application。

s although it might seem cumbersome to add to creates you will see how this is going to work very well for us。

 All right， so I'm going to save that and I'm going to scroll all the way down to our main and in our main we are going to create we' start creating our builder so that we can create our logging facility here。

 So I'm going to say a mutable。Object called builder， and we're going to create it with builder new。

And then we're going to say builder。 I'm going to say filter level。

 and what we're going to say here is we're going to set the level， the level of these。

 we're going say it at not info but debug and debug is going to allow us to see all the messages at least at the debug level。

 So builder in it。 and then we are， we are good to go。

 So we're going to be set there for for what we want to do。 and this is not filter。

 this is filter level。 This is why I was getting an error there。 Alright， so first。

 let's just make sure that if we toggle the terminal。 So let's check if everything works correctly。

 and I'm going to do cargo run info V1。 So everything's fine。

 let's quickly check if help works fine and does work correctly So I'm going to close these。

 we're still printing。Print line everywhere。 And let's actually start by doing a little bit of adding a little bit of like log statement so we can do something like say for example。

 here we could do log debug and this is going to be a macro。

 I'm going to say debug message login is enabled and we're going to add a semicolon there and now we're going to toggle the terminal again。

 we're going to not run help， but info VD1 and you can see here that we start seeing。

That our messages are there。 So we get in the timestamp between the debug level。

 It's blue and block r。 R2 is right there。 And this is the actual message。

 So that is how we enable simple logging and not only that we can start tweaking。 So， for example。

 we say level filter is not debug but info and we can try the terminal again。

 and we can run we won't see that message。 Do you see that here in the output。

 There's no there's no debug like it was here before， And the reason why is because we've change。

 We've toggle that。 So you can start tweaking around what you want there。

 and you can start you can start populating。You can start populating the the。

The messages that you have here， if options debug， greenline， so we can say， for example， here。

 log info。And we can say debug mode enabled all of these can be changed and and then you start seeing you start seeing like more of that capabilities of producing producing more of those messages。

 So let's try try one more time with the terminal and lets let's make sure that the debug level works。

 So if we say dash t dash D coming from that So let's see if that works。

 now we get both we get info debug mode enabled and debug message logging is enabled。

 Now I should probably do better and not mix and confuse everyone by adding debug messages in an info message。

 but you get the idea that it is not that complicated to start adding more and start using logging capabilities in your rust command line tool。



![](img/1e0b10120f882e0c122278a582c41221_2.png)