# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p125 36_02_05_控制日志详细级别.zh_en -BV11y411z7Dn_p125-

![](img/b3283f855acf3af283f0f09bf5473edf_0.png)

We've been adding login to our application to our HtP API here。 Everything's great。

 but so far we've been hardcoding the level of the login and every time we want to change well we need to come and change the source This is not ideal This is far from ideal in a production environment you actually need to have that flexibility to set exactly what you need here in a more flexible way。

 this is not very flexible， this is hardcoded， not good for now。

 So how can you do that in a flexible way。 well environment variables is definitely the way to go So we can actually start exposing or reading into some environment variables so that we can take a look at what's going on。

 So first let's read from the environment， let's pick and choose something that we can read that is for these application so I'm going to say。

Logging。Loin level and here the information from Github compile pilotot is pretty straightforward。

 I'm going to accept this and then make one tiny tiny change。 I'm going to make this lowercase。

 Alright， so what what we have here is we're creating this variable called login level and then we're using the standard library and bar and login level and let's make a tiny change here we're going to call this redactor。

And save that now is I'm prefixing this with the name of the service so that it is specific and there's no overriding of potentially other things that might be using this highly generic logging underscore level and I'm going to call unwrap or going to either I'm going to get the value of this or set default to info and then I'm going to put it to a string。

But so far， this is not necessarily what we need here because that has to go all the way into the width max level。

 so it has to be at this level this inum that we have right here so how can we do that Well。

 we're going to do a match and to do a match we're going to say let max level。

 we're going to actually be very idiomatic here and we're going to say match。

Loin level as string that looks correct to me。 and we to accept these and when we're going to what we're trying to do here is like whenever traces debug info1 or error is said。

 these are going to match to actual levels and we can the resulting max level will be one of these guys right here。

 and if nothing matches， So we say you know， something bogus will default to info。

 which is exactly what we want here。 Now one last thing instead of having level double column info here。

 we can say max level All right， so that looks correct to me now let's start up our application and when I say cargo run and if we do cargo run you can see that the fold level is info。

 I'm going to control C and I'm going to say I want to I want to have a redactor。

Underscore logging level of。How bad we have debug So we do debug and and start running。

 we will start getting our debug messages， which is actually pretty good。 How bad we do tracing。

If we do trace level， which is even more verse， we can we can we'll start getting a lot of。

 we actually let make this a little bit bigger。 we start getting a lot of more information。

 So I think this is pretty good。And way way more flexible than what we had before I'm going to control C out of that。

 we'll get debug messages here， no problem all right。

 so we have lots of flexibility now we can control using control login logging levels from the environment variable for our application we're making it more flexible and more production ready so that we can actually build on these and have that flexibility when we need it in a production environment。



![](img/b3283f855acf3af283f0f09bf5473edf_2.png)