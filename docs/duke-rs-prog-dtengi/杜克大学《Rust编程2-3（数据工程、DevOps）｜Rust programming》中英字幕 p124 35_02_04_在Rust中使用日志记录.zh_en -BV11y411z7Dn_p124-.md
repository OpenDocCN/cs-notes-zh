# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p124 35_02_04_在Rust中使用日志记录.zh_en -BV11y411z7Dn_p124-

![](img/344742b24e5d8aa4382ad65dd27cda31_0.png)

Now that we've added or created the login necessary for our application to start producing output。

 we can start adding more to it。 we actually have a few print statements in LibarRS。

 we will see that whenever there's things happening here。Reacting will be printed to standardL。

 This is not useful because you can control the levels and we'll see levels about levels later on。

 but here you want to avoid having all these print statement。

 So how do you how do you do this well before starting here with the removal or the change for those what I want to do is add useful information right here at the bottom like the starting the reactor service is a nice message to have this is a warning is not a useful one so let's start adding useful stuff I'm going to go back to main R I'm going to close these one for now and in the main function what I'm going to do is scroll here to the bottom to find that address now this is hard code right here and nothing is telling me about that address So instead of doing it that way what I'm going to do is I'm going to initialize a couple there。

Here at the very top。 I'm going to say lead address。

And I'm going to say that address is going to be 127 that 0 that0 that 1。

 and let port going to be port 8080。And then I'm going to be using that， yeah。

 sure buying address is going to be both the address of the port。So that that's fine。

 And then what I'm going to be doing is instead of the warning here。

 I'm going to remove that that a debug Now， I don't think I added the debug at the very top。

 but we can add it later if if we need to sub bind into the address。That's fine。

 And then we're gonna go all the way to the top so to make sure the debug is used。

 so I'm going scroll the way to the top and instead of one， I'm going say debug right here。

 so that's going to be good now all the way to the bottom All right so we we have our debug binding to address and now let's just update these one So instead of that that is hard coded。

 we're gonna to say bind address I'm going to say that and then that is good。

 So you can once you have logging you can start using this pattern to start populating everything that you need at very specific levels。

 we haven't seen yet how to control the logging levels of these HttP API but this is a useful way of in setting the scene so that you can you can actually start adding those login levels later so when you need to start saying well I don't care about debug。

Ination， this is not useful to me。 then this one print。 and then you can go and move forward。

 Alright， so that we have that one。 Now we can add tracing。 if I go scroll the way to the top。

 we can add a little bit of this。 let's say info。 all the way to the top on Lib S。

 I'm going to say tracing。 I'm going to say debug is debug is fine。Or actually。

 let's just put info here。 couldn't make my mind there for a second All right。 So use tracing info。

 that's fine。 And I'm getting this， I'm getting this is this is grayed out。

 but no problem tracing info。 and I'm going to start replacing the print line。

 So instead of a print line here， when I say info。And we're going to start adding that。

 And'm going to say info right here as well。 So there you go。 like。

 I don't think I have more print lines。And those are the two that I had。

 So now those will be logged to standard out。 Alright。

 so now I'm going to go and toggle the terminal。 I'm going control C to stop it。

 and we'm going gonna cargo run to start again。 but it's not showing the information And why is that well because we have the level at info So let's change that can we have two paths here。

 we change it to debug there or we change these to info。 So this control C again。

 start cargo run again and now we'll have our binding to address1 to7 that's zero that's0 the1 port 8080 So actually actually very very useful。

 So if we start hitting our API well see that you can we're doing things here。

 this that was printed before to standard out now is printed on with actual tracing and log in。

 So this is exactly the technique that you want to use when you start adding log。



![](img/344742b24e5d8aa4382ad65dd27cda31_2.png)

Into your application。