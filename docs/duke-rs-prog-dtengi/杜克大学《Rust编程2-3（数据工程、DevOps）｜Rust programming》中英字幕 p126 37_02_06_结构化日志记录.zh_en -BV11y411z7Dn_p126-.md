# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p126 37_02_06_结构化日志记录.zh_en -BV11y411z7Dn_p126-

![](img/a0946c753dc3a9931424b88ff9282f59_0.png)

Now that we have a lot of login and flexibility with the levels and the type of verpoity that we have with the login for our application here。

 One last thing I want to show you is structured login and structure login is very useful because it allows you to have well structure in your log output and why would you want to have structure in your log output because it makes parsing easy so let me open the terminal here and let me show you if I run this again。

 you have all of this information going on imagine that you want to parse that information externally so going back to monitoring a little bit and you want to have some alerting so if you wanted to programmatically read these well you would start to have to produce either regular expressions or something but this is a fragile approach because this is very prose like binding。

to address this is more of like human readable output。

 but this is not very useful if you want to programmatically read that information similar to builder like starting 20 workers。

 what if someone like starts messing up with a format。

Then you start getting into trouble and that's not very flexible Instead that is why structure logging is here to help out so let me clear that out。

 close that and the way you add structure login is well very straightforward actually so let's go here。

To where we start seeing the binding to address so we can actually have a narrow one。

 I'm going to say info， we're going to use address and we're going to use the percent。

The percent there， the percent character I'm going to say address and similar to what is suggesting coppilo but I'm going to just leave it with percent address and port equals percent percent port and thats that's good enough and I'm going to add the semicolon there so let's see how like I mean I think this is pretty straightforward。

 you' are just adding the variables and defining them and passing them the to the info macro sorry to the info macro there。

 So if I let me say that paggle the terminal， clear that out， run the service again。

You will see that the output now is well structured。

 you have the address equals 127 that's 0 0 to 1 import equals 8080。

 This is a very useful way to start adding more information that can actually be parsed by an external system and you can absolutely go and add more pros to it and you can say listening for request for example that sounds okay to me and if I control C out of here and clear that out and run this again you will see that listening for requests and then address and port will will still be there so this is a very good very useful way to start adding structured login which some systems might want to have when they're parsing the logging output of not only in this case this HtTP API but other systems as well。



![](img/a0946c753dc3a9931424b88ff9282f59_2.png)