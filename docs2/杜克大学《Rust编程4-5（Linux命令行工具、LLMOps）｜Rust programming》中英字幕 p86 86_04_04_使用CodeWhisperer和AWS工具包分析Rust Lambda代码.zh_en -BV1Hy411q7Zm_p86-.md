# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p86 86_04_04_使用CodeWhisperer和AWS工具包分析Rust Lambda代码.zh_en -BV1Hy411q7Zm_p86-

![](img/32d44765ea683018bc11e477d5ddd972_0.png)

Here we have a rust polars Lambda function that has working code。

 But one of the things I want to do here is dive into how to make it better。

 So one thing we can do is if I go into this Github copit extension here。

 let's go ahead and just disable this globally temporarily。

 You can see here that it highlights that it's been disabled。 Now， if I go over to AWS toolkit here。

 you can see I've got a bunch of other things that I could play around with。

 One of them is actually Lambda。 So we know that this Lambda is called Pols Lambda。 In fact。

 I could even go into there。 and invoke it， which seems like a good starting point to play around with the tool。

 So if if we go here and we say invoke on AWS。😊，All I need to do is put in some brackets here and just type in filter。

And we can put in 5， right， so we can go ahead and invoke this。 Does it work。Perfect， right。

 so I'm able to actually interact with it。 Now， what else can I do Well。

 one of the other things you can do that's pretty cool if we go and close this is I can go to code whisperhis。

 Now， code whisperhi can actually do auto suggestions。

 So if we go into the documentation for code whisper。

 a couple things to point out is that it can scan your code to highlight and define security issues。

 again， as it gets more and more languages there'll be a matrix of when full scanning is available and when the suggestions are fully available and we can actually look at that here。

 So we can see that as this thing is getting more and more developed。

 the highest quality at this point in time is in Java Python Javascript Tscript and C sharpp。

 But there is also code generation support for R， So what's gonna happen is as each month。

 more and more development takes place and more training takes place， we can get more support。😊。



![](img/32d44765ea683018bc11e477d5ddd972_2.png)

We code whisper with these languages like rust also in terms of security scans as well。

 we can see that the security scans can perform on an active file。

 So this is a really awesome integration here that we get for free with code whisperhi when you're building out AWS specific code。

 and so this is really a best practice for dealing with AWS Lambda and rust is to use the tools like CodeWhis to also do security scans。

 code suggestions and even commenting for your code to make it more clear。



![](img/32d44765ea683018bc11e477d5ddd972_4.png)