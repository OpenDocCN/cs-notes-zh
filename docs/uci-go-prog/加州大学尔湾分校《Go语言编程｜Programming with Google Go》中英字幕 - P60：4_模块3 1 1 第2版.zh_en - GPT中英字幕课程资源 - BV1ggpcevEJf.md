# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P60：4_模块3 1 1 第2版.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/fdca336cdbfcf066055ba93678e1f8f4_0.png)

Module3， threads and go， topic 1。1 go routines。So in the previous modules。

 we've been talking about concurrency and parallelism and how processes work and threads work。

 how they execute concurrently at least， and maybe in parallel if you have extra hardware。

But we haven't really talked about how you actually implement that and certainly not in go。

 but how you implement that in software。In order to get these multiple threads。

 we actually we're specifically focusing on threads in order to create these threads。Of execution。

 you have to use certain programming constructs that are built into the go language and this is one of the advantages of go that it has a lot of these constructs built right in and they're easy to use so say you want to create a go routine right which is a thread that can run concurrently with the other go routines。

Now， one go routine is always created automatically to execute the main。

 So even if you don't do anything special， you run a main。

 it will create a go routine and execute the main inside that go routine。

 Other go routines are created using the go keyword。 So so as an example down here on the left。

 we have on the left we have an example where there's just the one go routine main。 Okay。

 so this is some segment of main， right， equals1。 you call fo equals2。 that's just main。

 that's one go routine， the main go routine executing all three of those instruction。

 the fact the fos a function call。 Now， on the right is the version where we execute create a new go routine just to execute that function F。

 So you can see on the right， there's a equals1。 that's execute in the main go routine。

 Then we say go fo that creates a new go routine， which will execute the code in fo。😊。

And then we say a equals two a equals two again is still in the main go routine。

 so if you call go Fu， there are now two go routines。

 the main go routine and this new newly created this's called subrout sub go routine that's created。

So。And notice it on the right。 so on the left， the main will block when it comes to fo when I say block the main will so there's a equals one。

 then fo then equals2 A equals2 can't execute on the left until fo is complete so fo it's not blocking。

 but fo has to completely execute before equal2 can happen that's on the left on the right where you have the extra go routine that you've created you say equals one in the main then go fo。

 it creates this new thread or a new go routine to execute fo and then a equals2 can execute while fo is going on or before fo is even started。

 we don we don't know the timing， it depends on the scheduler on the runtime go runtime scheduling how that's going to be scheduled but a equals2 does not it can execute immediately。

 It doesn't have to wait for food to complete or anything like that because F is being executed in in a concurrent go routine。

So。I just showed you how to start a go routine。 It's pretty simple。

 you say go and then give the name of the function that you want to execute or define the function you want to execute。

 and the go routine will execute the code associated with that function。

So a go routine generally exits when its code is complete okay so whenever it's done with this whatever function is's executing。

 it's done， it returns from that， then the go routine just exits。



![](img/fdca336cdbfcf066055ba93678e1f8f4_2.png)

Now when the main go routines complete all other go routines are forced to exit。

 so what that means is you start with the main， you can make several go routines from the main but if even if these other go routines are not finished with their code。

 if the main go routine ends， then all the other go routines will be forced to end and will forced to exit and this is important to understand to think about when you're writing your routines because what will happen is。

The go routine that you create may not complete its execution because the main completes first and so you might get this behavior where you say。

 look I wrote this code and this go routine supposed to execute and it doesn't seem like it's executing and that might be because the main is completing before the go routine ever got to finish its own code so that's something to watch out for。

Thank you。Module 3， threads and go， topic 1。2， exiting go routines。

So we already describe how go routines will exit when they complete their code。

 but also go routines will be forced to exit if the main go routine exits early then all the go routines that are created they all are forced to exit so they might exit early before they do their job before they finish the job So Ill give a little example of piece of code here and by the way in these code segments I'm generally clipping out the importing the packages right so I have to in order to use this program I have a printf right and I'm using the FMT package so I haven't put the part in there where I import that but you assume that that's there I just want to get right to to the go to the go routines so in this main it's pretty simple。

😊，It first thing it does is creates a new go routine。

 which should just exit just through a printf rather and print a new routine。

And then after that or we don't know the order， but at some other point in the main go routine format printf main routine so you expect to see two things printed on the screen main routine and new routine and you wouldn't necessarily know what order these two are going to get printed in right because when the go routine is created we don't know how the scheduler is going to schedule the main routine and the go routine maybe it schedules the go routine first the new go routine first maybe it's schedules the main go routine first。

 we can't really tell but at a glance you would expect it to print main routine and print new routine at some point in some order。

But when I execute this， only main routine is printed。So why does this happen。

 it's because the main go routine is finishing before the go routine。

 the other the new go routine starts and this happens consistently。Theoretically。

 we don't know how the schedule is gonna to work。 the go runtime scheduler。

 We don't know is's going to let the go main the main go routine run first or the new go routine run first。

 we don't know。 So theoretically， if you ran this over and over you could get different ordering right you would think。

 well， sometimes the main goes first。 So it does main routine and then it quits Sometimes it does the the new go routine。

 then it prints a new routine and main routine maybe actually。

 what happens is when I run this anyway。 every time it just prints main routine and quits。

 So what I presume from this is what I assume from this rather， is that the scheduler。

 the go runtime scheduler is given preference to the main routine。

 So it's always letting the main routine go first before the new go routine。

 I don't know that for a fact。 but it seems like that's how it's implemented。

 But even if that's how it's implemented， we have no definite knowledge of that meaning。

Maybe it's implemented that way right now， but then the next version to go。

 they might change the schedule is so it does something different。

 Okay so that's not something that that ordering we can't rely on。

 We have to assume that we have no idea what order the scheduler is gonna work and what order is gonna execute these go routines in so definitely but definitely though what's happening here is not what I wanted it just print out main routine never print out new routine So so I got to get this this main so it doesn't exit so early I don't need I don't want main to exit so early。

 I want main to somehow wait for the other go routine to exit before it so that I can get the new routine to be printed out right So how should I do this。

So first， I'm going to show you this one way， which is really a hack。

 but I'm going to show it to you anyway。 Okay， just so you know what not to do， but it works。

 but it works sometimes， but it's not a safe thing to do。 So here's what I do。

What I do is I just added this line that I highlighted in red time do sleep。

 So and I give it 1000 milliseconds。 So what I'm doing is I'm and notice that that time dot sleep。

 It executes in the main go routine， not in the new go routine that I create in the main go routine。

 So I create the new go routine calling go。 Then I put the main go routine to sleep for a little while。

100 milliseconds。 And then I have the main go routine print main routine Now what that does is in that time that the main go routine is sleeping the go runtime scheduler isn't stupid。

 It's not gonna just let the machine sit like that when it knows it has another go routine available because remember a big benefit of doing concurrent programming is that when one routine。

 one go routine or one thread is waiting is blocked and waiting for something。

 then the scheduler can just move in another one。 So it doesn't have to waste time。 It can say， look。

 I've got another available go routine， Let me schedule that。

 So that's exactly what's happening here。😊，When you put the main go routine to sleep。

 the main can't run so the scheduler， the go runtime scheduler schedules in the new go routine that it created that I created just before。

 it prints out new routine and then main routine print out。

 So what I get printed now is new routine main routine just like that with no space because I didn't put a space or character or anything。

 but that's what I get。 So this is my hacky attempt to get the go routine。

 the main go routine to stay alive long enough for the new go routine to actually complete this execution。

And it works， it works pretty consistently on my machine， but this is not what you should do。

 but this worked， you can see how this worked。WhatSo doing what I did。

 adding a delay like that to wait for a go routine is bad， bad。

 bad reason why is because you're making assumptions about the timing and your timing assumptions may be wrong。



![](img/fdca336cdbfcf066055ba93678e1f8f4_4.png)

So in this case， the big assumption I'm making is that the delay of 100 milliseconds。

 which I injected in there and the main go routine。

 I assumed that that will be enough to ensure that the new go routine has time to execute。

 So I assume look if I assume that certain behavior of the scheduler too， I said， look。

 if Im going if if I force the main to delay for 100 milliseconds， the go runtime schedule。

 of course， it's going to schedule this other go routine that I've created right I assume that I don't know that I don't know how they've implemented that。

 but I assume that。😊，And so and so I assume that the go runtime scheduler is going to schedule a particular go run goroout that I had in my mind。

 Also， I'm assuming something about the operating system too。

 because for all I know the operating system which is running above the go runtime。

 it could take that 100 milliseconds and move in another thread entirely。

 It might just so right now I've got if you remember there's a thread an OS an operating system thread that all the go code is running in all the go threads are running within this one operating system thread the operating system might just say look。

 I'm going to take that thread and swap put it out a context w it and bring in an entirely different thread。

 maybe it'll bring in PowerPoins or something which is running on this machine So it might use that100 milliseconds in a way that I don't anticipate。

😊，Now， it doesn't。 And there are reasons why it doesn't。

 But I'm making certain assumptions about how the operating system scheduler works and about how the go runtime scheduler works。

 And these assumptions are not safe to make I have to because these can change in different version of the operating system。

 So relying on timing like this is not safe。 The timing is not deterministic。

 meaning every time you run the program， the timing might be different and you have to assume that So if you don't what will happen is at some point you get these really bad intermittent errors where most of the time it'll work。

 but sometimes your timing assumption will be violated and sometimes the error will happen and these are the worst these are one of the worst types of errors because then you get these intermittent errors。

 which only happen occasionally， so you run it and you say oh， I found a bug。

 let me run it again to reproduce it so I can debug it and you can't you run it again again and again。

 the bug doesn't happen again。 those are terrible types of errors to have to debug。

 So this is not what you want to do。 You don't want to rely on timing。

I have a long story which I could talk about where I rely on timing as an undergrad and failed badly in a big assignment。

 but I won't bring that up。 It's kind of interesting， but it's sort of about track。 Still。

 you can't rely on the timing。 So you need formal synchronization constructs and we'll talk about those。

 Thank you。