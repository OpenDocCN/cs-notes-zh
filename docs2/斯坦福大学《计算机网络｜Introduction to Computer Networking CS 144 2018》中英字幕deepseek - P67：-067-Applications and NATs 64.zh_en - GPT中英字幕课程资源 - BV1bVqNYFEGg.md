# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P67：-067-Applications and NATs 64.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

是。So welcome to unit5 so in unit5 we're going to talk about applications in some ways all of the internet what it's about is being able to drive these applications it's kind of what makes the whole thing useful and interesting and such a dynamic engine change So in this unit we're going to talk about three applications in particular that really cornerstones of the modern internet。

The first is DNS， the domain name system， which we've seen mentioned a couple of times before。

 but we're going to go into it in depth。 So DNS uses UDP as its transport protocol。

 It's a simple client server exchange。 you can ask for names and get information about those。

The second application we're going to go into is ACDP or the World web， so ACDP operates over TCP。

 so a different transfer protocol， but again it's a client server exchange。

 so we're going to see how a ACTP request look like and some changes that have happened in the past a couple years or so with more recent versions of ACP that are emerging based on Google speedy。

Finally， we're going to look at bitTn， BiTn's interesting application because of what fraction of internet traffic today is over bitTrrn。

 and it's an application that uses TCP as its reliable transport。

 the other hand it's not a client server model， it uses peerto peerer model of swarms that exchange pieces of large files and somehow altogether manage transfer data at a tremendous rate。

ButWe're going to start with NAts network address translation devices。

 you've seen them before in Uni1 and in what we're going to be describing in the first few videos。

 we're going to look at not only how they've allowed growth of the edges of the internet but how they allow multiple endpoints to hide sort essentially look behind a single IP address started as really solving two problems one was making it easy for a network to appear behind one IP address so that if you're allocated one IP address by a provider。

 you can then provide a number of private IP addresses that sit behind it。

 probably your own homewi-fi router works this way。

 The second thing is that because they're translating addresses primarily in the direction that goes from the edge towards the core。

 they don't naturally accept incoming connections so they provide a sort of rudimentary security feature which is that it makes it hard for connection to be opened up to an edge device and therefore to。

However， the consequence of this is there has significant implications and ramifications for applications。

 basically it makes it a lot harder for any kind of application that wants to initiate communication with an edge device。

 so there have been all sorts of things that we're going to learn about in this unit about not only how a that's built but what some of the implications are and some of the things that people have done to try and get RAO。

If you build an internet application today， you have to work on NAs， you have to know how they work。

 and they're going to be a big headache， so I think it's really important you learn how they work down in detail。

 all different kinds of NAts and why they're complicated to handle。

So hopefully by the end of this unit， you'll be able to really build your new fantastic application that will take the internet on its next steps。

