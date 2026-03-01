# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p98 10_01_02_设计与实施监控告警.zh_en -BV1Hy411q7Zm_p98-

![](img/7f6cd0bd031b71a2efd88f55105f4483_0.png)

Monitoring and logging is data science for software systems。

 This has been happening much before the term data science became popular in common vocabulary。



![](img/7f6cd0bd031b71a2efd88f55105f4483_2.png)

![](img/7f6cd0bd031b71a2efd88f55105f4483_3.png)

And you can take a look at this how when you deploy a server。

 the source code itself has logging code that's inside of it。 It also has instrumentation code。

 And the importance of this is that that logging code must contain the context for the server that it's in。

 So， for example， if this server is in a specific region。

 Let's say it's on the East Coast of the United States or the West Coast of the United States。

 It would also have some I that would enable it to be tracked centrally。Likewise， metrics like CPU。

 memory， disko all are very important in the context of discovering what happens in a distributed system a lot of times if there are are10 servers。

 for example， it would be impossible to know if there is a problem with a specific server that was a very subtle or non-deterministic issue。

 so maybe periodically the server crashes or theres some kind of a network issue the only way to solve that is by using data science and so what you would do is take the logging instrumentation。

 put it into a centralized dashboard you could search it you could go through and set alerts on it and even get automated insights through machine learning and really this is the heart and soul of modern software engineering is to be very careful about thinking that your system is really a place for data science to occur。



![](img/7f6cd0bd031b71a2efd88f55105f4483_5.png)

![](img/7f6cd0bd031b71a2efd88f55105f4483_6.png)

![](img/7f6cd0bd031b71a2efd88f55105f4483_7.png)

![](img/7f6cd0bd031b71a2efd88f55105f4483_8.png)

![](img/7f6cd0bd031b71a2efd88f55105f4483_9.png)

![](img/7f6cd0bd031b71a2efd88f55105f4483_10.png)

And you must have enough context to debug your system in production。



![](img/7f6cd0bd031b71a2efd88f55105f4483_12.png)