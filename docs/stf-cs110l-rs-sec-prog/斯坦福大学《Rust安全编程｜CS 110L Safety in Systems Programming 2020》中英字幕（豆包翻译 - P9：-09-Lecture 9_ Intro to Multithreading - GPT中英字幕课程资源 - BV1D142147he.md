# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P9：-09-Lecture 9_ Intro to Multithreading - GPT中英字幕课程资源 - BV1D142147he

Welcome， everyone。 This is week five now。 So congratulations on making it to the halfway point of the quarter。

 although I guess technically the halfway point is somewhere in between today and Thursday。

 So some quick logistics。😊。

![](img/273e4e7ec71e372474f26e7df8760fdc_1.png)

We sent out a weekly survey on Slack that is the only component of the weekly exercises for this week。

 so if you could fill those out by Wednesday night。

 we would really appreciate that that'll help us make sure that we're doing a good job and make any improvements that we can。

We also released the first project， as you should have seen。

In this project we're implementing what we called the D debugger， which is two puns in one。

 see if you can figure out both of them， you can work with a partner and there's a thread on Slack if you don't have a partner in mind already and are looking for somebody。

If you have any suggestions， let us know this project is pretty system Z。

 So you're going to go pretty low level。 We've tried to make this very clear in the handout so that you don't need to refresh on any 107 material and hopefully you。

Well， it's a 110 project， so I guess you do have to refresh on 110 material。

 but we tried to explain all of the 107 stuff that you would need。

 so if you feel uncomfortable with dealing with registers and raw memory addresses。

 that should be okay， but if you run into any challenges or have any questions。

 please do let us know because we would love to help you and we don't want this to take a whole lot of time。

If you， I guess the 110 assignment was due yesterday right。

 so if you complete a trace this uses the same foundation as trace。

 but it will be even more fun and you'll be able to do much more with it you'll get to see the power of the P trace this call and you'll also come to understand why P tracece is banned on a lot of computers。

 it's a single system call that has a whole lot of functionality packed inside of it。

So the project is due next， next Tuesday， so you have two weeks from today to complete it。

 but as a recommendation， I would say try to finish milestone4 by this Sunday。

 milestones one through three are kind of substantial milestone four should be pretty quick so if you can complete the first four milestones by this Sunday。

 you'll be in a really good place in terms of scheduling。

So we went through the weekly surveys and we know that people are feeling pretty stressed right now。

 especially if you're taking 110， 110 is starting to heat up with the multiprocessing assignments。

 and we just wanted to take a a look back as well as a look to the future and just reflect on like how far we've come and how much we've really accomplished here。

 we talked about a brand new model for managing memory safety that is really quite difficult to work with。

 it's an important model to learn because you end up using it even in C and C++ this is that the compiler enforces it here but very difficult to get used to nonetheless。

Dealing with option and result was quite challenging。

 you had to learn a whole new alternative to inheritance instead we've been using traits。

 you spend a long time working on generic types and implementing your own generic types。

You learned how to use heat allocated memory and to use reference counted pointers so if you want to。

Share if you want to have multiple things pointing to a single piece of memory。

 how do we deal with that safely？And throughout this whole process。

 I know everyone's deal with a lot of compiler errors， hopefully you've learned from the process。

 but this has certainly been challenging and then last week we spent some time talking about how to safely use multiprocessing constructs like fork and signal and pipe。

And this is really quite a lot to learn in just four weeks。

 so I want you all to know that we're really proud of you and you're doing an amazing job and we hope that you can look back and be proud of yourself as well。

Just a quick preview for what the class looks like going forwards。For the next two weeks。

 we're going to be focusing on multi threading。 Multi thread is， is really。

Why we're teaching this class in RuUST is one of Rust's core advantages。

 and we hope that throughout the next two weeks， you will see all the hard work that you put into the first four weeks really pay off。

After that， we're going to talk about a different model of doing concurrent programming called asynchronous programming or nonblocking IO。

 and this is a model that is not touched on too much in 110。

 but you really need to know because it shows up everywhere now。In week8。

 we're going to talk about network services and how to design safe and robust network services。

 and then week9 will take a look back， reflect on what we've learned and see how it applies to other languages that you might encounter in systems programming like C++ or maybe like go。

In the last week， we are looking into getting some guest lectures set up and hopefully we'll also do some case studies of real rest projects and how they use things that we've been talking about this quarter。

Sound good to everyone。Makes sense， awesome。Alright， so for today。

 I want to I rest the discussion of Chrome a little bit。

 And so I want to take a little step back and wrap up what we were talking about towards the end。

 And we're also going introduce multithreading in rest。 if we have some time。

 we'll introduce locks in Mut。 But I want to try to slow down the pace a little bit today。

 for for the people who are in 110110 is lagging behind schedule a little bit。

 And we're actually ahead of schedule a little bit。

 and to make sure that we don't get ahead of ourselves。 I'm going take the pace a little bit slower。

 So if you haven't any questions at all， please feel free to interrupt to me。

 you can just unmute yourself and ask a question because today is the day for making sure that we are all on the same page。

 and we're all happy and well in understanding this。😊。



![](img/273e4e7ec71e372474f26e7df8760fdc_3.png)

So let's first talk about Google Chrome and pick up our discussion from last Thursday。

 so we talked about how when you're designing a browser。

 most of the time you would want to use multithreading Multithreading has a lot of advantages in a lot of different areas and the reason that Chrome uses multiproces is really for security and stability it uses multiple processes to provide isolation in a way that you don't really get with multithreading by design。



![](img/273e4e7ec71e372474f26e7df8760fdc_5.png)

And we said that modern browsers are extraordinarily complicated。

 there's so many things that you can do with them， and because of all that complexity。

 it makes it very， very， very， very hard to implement a correct browser that doesn't have bugs。

And the Chrome team acknowledges this and their argument was basically。

 let's admit that we can't write a correct browser， we can't write a browser without bugs。

 our browser is never going to be perfectly secure。Under the assumption that there will be bugs。

 let's try to contain the bugs to as small of an area as possible。

If there's a security vulnerability， okay， that's fine。

 we have knowledged that this is going to happen， but let's see if we can contain that security vulnerability so that it doesn't compromise the entire computer。

 it just compromises a very small part of the browser。

And how do they build these isolation mechanisms。 This is why they use multi processing。

 They use processes that have restricted access to the file system and to other processes on the machine so that if you。

Compromise the code that is running， that's fine， you compromise that process。

 but that process didn't really have many permissions to do many things in the first place。

And so I showed this diagram of like how this actually manifests in Chrome and Chrome has a master browser process。

 the main process。That and this is where most privileged operations have happen。

 So there's a thread in here， this sort of like， I really love these diagrams because they're so cute and yet they're actually quite accurate。

 If you read this article here， it is very， very accessible。

 but it doesn't really dumb down the concepts at all。 And it is correct。

 It hasn't oversimplified anything。 Theres these little squiggly things are threads。😊。

There are multiple threads inside of this master browser process。

 and they do things like managed network communication。

I mentioned that we want to isolate these small processes and every tab that is running is going to have a render process。

 this one is the least privileged one。 So this is where you're running JavaScript。

 this is where you're parsing HTML and CSS。This is where a lot of the risks of vulnerabilities happen。

 and so it's the least privileged process， you can't actually make network requests in this process because if you were to compromise this process and you could make network requests。

 then say that you're on some like high security corporate network。

You go to some shady website and now all of a sudden some process or some some JavaScript code can hijack the process。

And if it hijacks the process now it can start sending arbitrary network requests to other machines on your network。

And you can imagine that like if you know of a bug in Chrome。And you know of a bug in Windows。

 for example。You can break out of the Chrome sandbox process and start sending malformed network requests to other Windows machines so that you can compromise the Windows kernel and take over the computer and something similar happened。

 not the Chrome part， but the Windows part， I don't know if you guys heard of Wannary。

 Wannary was a ransomware software that among many institutions it took down the NIH in the UK which is their like hospital system。

Their hospital network and it just encrypts all of the files on the machine and you have to pay Bitcoin in order to get your files back and you can imagine encrypting all of the files in a hospital network is a really really bad thing and we would like for that to not spread through arbitrary web pages that you visit if they break out of Chrome and then infect other machines on your network。

So these render processes actually can't make network requests。And you're like， huh， well。

 that's weird， like then how does JavaScript make network requests because JavaScript needs to be able to communicate on a network that seems like a very important part of a browser。

Well， we make the JavaScript code run inside of this sandboxed process。

And we have a thread inside of this browser process that makes network requests on behalf of these less privileged processes。

So if you have JavaScript code that wants to make a network request， that's fine。

 you can run that in this render process， but then the render process is going to have to ask the browser process。

 this privileged process to make the request for it。And then when the request completes。

 the browser process will hand the result back to the render process。

So this kind of like handoff happens everywhere inside of Google Chrome。

 that's a result of this isolation， you break things into components。

But those things were tied together right that's why we were using multihth threadreading before is because they kind of go hand in hand。

 so when you break them into components， you need to establish communication mechanisms for those things to continue to work。

 We broke JavaScript and network requests into separate processes。

 and so we need a way for these processes to communicate to establish what it is they're trying to do and to exchange information。

Does this make sense to people？That's a great question。

 why is it any more secure to hand a network request to the browser process rather than just doing it in the render process？

Is that your question？So。When you're giving a network request to the browser process。

You're just handing it information。 You're not asking it to execute any code。

 And that is the real concern here with。With vulnerabilities is because we're allowing jascript to execute arbitrary code。

 it's possible that。Somebody may discover a bug。Like there's there's millions of lines of code that run ja and run Webassembly and deal with all of these features that are listed on the previous slide。

 and there's a very high chance that somebody might discover a bug that allows them to take control of the process。

 There's much less code that deals with making the network requests。

 So what we've done is we've taken what we call what is it called。

Your attack surface is what it's called What are the ways like。

 what are the things you expose to a malicious user that they could potentially use to break into your system if they find a weak spot。

 we've taken our attack surface and we've partitioned it。 So most of the attack surface。

 Most of the functionality that we expose is inside of the renderer process。

And there's just a small amount， the networking stuff that's inside of the browser process。

So somebody could still exploit the browser， the networking part inside of the browser process。

 but it's a much smaller attack surface， there's much less code and much less functionality that's exposed。

And then the reason that it's more secure to do the networking stuff in the browser process rather than the render process is because the browser process。

 say the render process asks the browser process， hey， can you make this network request for me？

The browser process is able to verify that that's an OK request to make。Like say you loaded Google。

com or say you loaded Gmail and it knows that Gmail is running inside of this render process and then this render process says。

 hey， I want to make a network request to Gmail。com The browser process can check that and it can say。

 okay， that looks fine， that checks out and it can make the request on its behalf and then relay the response back。

But say you have a vendor process that is on shadyspotify。com and shadyspotify。com。

Tell us the browser process， hey， I want to send a network request to a machine on my local network。

And the browser process is like yourshady Spotify。com。

 why are you trying to send network requests to local machines on this computer's network？

That doesn't really make sense why you want to do that。

 And so it has a set of rules that it forces to make sure that you're not making arbitrary network requests if we made the network requests inside of the browser process。

It can make network requests like there's not enough granularity on what kinds of network requests it can make and who it can communicate with。

 and that's why we need some controls imposed at a higher level on what this render process can do。

Does that make sense， great question。Okay， so and again。

 like the benefit of doing this is if one of your tabs gets compromised or crashes。

 it doesn't affect the other tabs that are running or the whole browser itself。

So how does this communication actually work and I mentioned on so we talked about how these processes are sandboxed and the render processes。

 which are the less privileged processes don't have access to the network or to the file system and so on and so forth。

嗯。And， and these processes may have multiple threads running inside of them。

 Do people know about iframes。 So iframes are allowed you to embed one website in another website。

 And Ar， can you think of any examples off the top of your head of of like when you might see oh。

 so this is very common in ads。 If you put ads on a website what you are doing is you are embedding content from a different website。

 which is the ad providers website inside of your website。And so very commonly， like what is a。

 a reputable kind of security ish website that has ads， I mean， thankfully。

Most high security websites don't include ads。But like Facebook or something。

 Facebook has ads right Yeah， Facebook has ads， but they are their own ad network。

 so they're not embedding content from a different website into their website。 but anyways。

 let's just imagine that you have some secure website that embeds an ad from some other external ad provider。

So all of that is one tab and that will all be managed inside of this one process with a thread to render the ad and a thread to render the main page。

 and they can communicate with each other if they need to。嗯。

And so you're saying iframes are in their own processes。 No no iframes are in their own thread。

 So the tab is a single process， but if you have multiple iframes， multiple embedded content things。

 then you'll have multiple threads that manage rendering of those separate parts and they can communicate with each other if they need to the JavaScript APIs provide ways for frames to communicate safely with each other。

 so that even if you embed an ad， it can't read what is on the main page or screw up what' on the main page if that makes sense。

 but there are still communication mechanisms。And then how do these processes communicate。

 I mentioned last class that they almost exclusively use pipes they don't really use signals here。

 I mentioned that signals are difficult to handle and in this particular case when we're trying to do very。

 very rich communication， signals don't help very much even if they were easy to handle because signals don't contain information。

It's just like you got this signal， but there's no associated information attached。 I mean。

 the browser would want to alert one of these render threads that， oh， hey。

 I made a network request for you， and it finished。But it's not enough to just say， oh， it finished。

 you would want to provide it with the response like the result of the network request。

 and since you can't really embed messages inside of signals， they're not all that helpful。

So Chrome's communication almost exclusively happens over pipes。

And you'll see these like IPC channels that are labeled here。A channel is just an abstraction。

 it's an idea of like a pipe basically that you can put things in one end and get it out the other and you can also it's a bidirectional pipe you can put things in one end and it'll go to the other end and you put things in the other end and it will go to the other end if that makes sense so really they are just establishing pipes here in between the two processes。

And they have a library in place so that you can imagine that this would be pretty cumbersome if you were trying to exchange like。

 oh， hey， make this network request for me。 Okay， and then the browser process says， oh， by the way。

 the user just pressed K on the keyboard or enter on the keyboard。

 and then the render process is like oh， make this network request too。

 And then the browser says hey， the response for your first network request just came in and here is the result。

 And then the browser says， oh， hey， here's the second request for this this network or here's the second response here is the result。

 You can imagine that like there's there's quite a lot of information that would need to be exchanged over these pipes。

 And your experience with pipes is like。Typing words。

 typing text into a pipe and then like having it get sorted。

 it feels like there's a very large gap between exchanging text over a pipe that is all uniform and trying to exchange very。

 very rich objects over a pipe such as the response to a network request。

 but really there isn't a huge gap between there Chrome simply has a library。

Which allows you to serialize a struct。To text and send it through a pipe。

 and then on the receiving end it part the other part of this library will receive text that came over a pipe and decialize it into a struct。

And obviously part of that is it will say which what kind of struct it is。

But if you imagine just taking a struct and writing out text that says it's this kind of struct。

 here are the values， and you convert that to a string and you write it to a pipe。

 then at the receiving end， you can read that text。

 you can parse it and you can assemble the other struct， This is called message passing。

So you're exchanging messages over a pipe and the messages can be arbitrary you can send like any kind of struct over this channel over this pipe and on the sending end。

 the channel library will take care of serialializing that struct into text and writing it to the pipe and then on the receiving end。

 it will decseialalize it and give you back a struct so that when you're implementing these processes at a high level。

All you need to think about is oh， I want to send this message to this other process。

 you don't have to think about， oh， I need to to use like this particular file descriptor and I need to like send the XYZ text and like deal with the parsing and whatnot because it's all managed in one of these Chrome libraries。

Does this make sense to people？This message passing model comes up a lot and it's actually going to come up again in multithreading next week。

 we'll talk about how this message passing model helps us because it allows you to exchange information even when you're not sharing memory It's a very。

 very simple idea。 you're just sending a message to somebody else and they they get the message and they go。

 okay， I can do something with this。But all events like clicks， keystrokes， whatever。

 they're all sent through the pipes。They're all sent us messages through these pipes。嗯。

How am I doing it on time。Okay。Briefly。So this is how Chrome worked for 10 years and it worked pretty well。

But people started to argue that， you know what this actually isn't good enough。

 We need to do better than this。 So what is all of this work by us， Like。

 this is actually quite complicated。 It's a lot of work。 What have we gotten from this。

 How does this help us。What kind of threats did we have before that we don't have now that can't happen now？

Yeah， you can't have one tab， compromise a different tab， what else？Yeah， yeah。

 So we have tab tab security。 Ju， did you have another thing。Exactly。

 in addition to having tab to tab security， you also have some tab to host security or tab to computer security。

 it's isolating what the tab can do from the rest of your machine so that a compromised tab can't send signals to arbitrary processes on your machine。

 it can't read from the file system， it can't send arbitrary network requests so on and so forth。

So we get isolation between tabs and also isolation between tabs and the host。What is this not by us？

So what can still go wrong here？Exactly， so if you have stuff inside of a tab。

It's in one process and obviously can still communicate。

 and I mentioned earlier that if you're embedding content from different domains inside of a tab。

 that's running or it used to run inside of a single process。

So there's no isolation between resources within a tab and that's important because say that you go to shadyspotify。

com or evil。com as I've written here， and in some teeny tiny one pixelixel iframe on the side of the screen that you can't even notice。

 it just so happens that shadypotify。com has embedded Cha。com or Bankofamerica。

com or some bank website。These two frames are running in the same tab。

 So according to the previous model， they should both be in the same process。And if shadyspotify。

com or evil。com is able to get a render process exploit such that they're able to break out of the JavaScript sandbox and run arbitrary code inside of the render process。

Wwhich is the threat that Chrome acknowledged is going to always be there。

 Then it can see all of the memory within its process。

 and it can also change all of the memory within its process。

 So that means it can see all of the memory that is being used to render Cha。 co or Bankofamerica。

 co or what have you。 And if it wants to read your credentials or like send more net requests to this frame it's able to do that。

And it's not supposed to happen the browsers have， it's called the same origin policy。

 they have s policies that say that if you have embedded content from two different websites。

 they can talk to each other， they can send messages to each other。

 but they can't really see each other's data beyond what is explicitly allowed， you can't embedChase。

com in some website and then be able to see what's inside of that frame。

 that's not supposed to be allowed。But if you're able to break out of the render process。

 or I'm sorry， if you're able to break out of thebox JavaScript sandbox into the render process。

 then you could do something like that and Chrome said that this is a big issue。

So there was an enormous project called the site isolation Project， and it said， you know what。

 we're already using separate processes for separate tabs。

 but we need to use separate processes within a tab as well。And it was extremely hard。

 You can imagine how difficult it was to get to where they were in the first place and how that involved creating a lot of library and low level code to build on top of。

 and this rearchitected all of that。 It ended up changing a lot of the core parts of Chrome。

And people were talking about this in 2015， but it accelerated in 2018 it became especially important because of two vulnerabilities called specter and meltdown and Specter and meltdown were hardware vulnerabilities。

 there were bugs in particularly Intel but also AMD processors that allowed you to read arbitrary memory inside of a process。

 even if you weren't supposed to be able to read that memory so crucially in 110 we talk about how kernel memory is mapped into the top half of every process that's not true anymore because of this。

It was the case that even though you weren't supposed to be able to read kernel memory because it was mapped into your process's virtual address space and there was this hardware bug。

 it ended up that you could read whatever you wanted to inside of kernel memory and that was really bad。

And so。The same thing happened with JavaScript code。

 JavaScript code is running inside of interpreter， it's not supposed to be able to read anything outside of the interpreter。

 but if you can read arbitrary process memory through this hardware bug。

 then you can read the render processes memory and that's pretty bad because if you have this kind of setup here with embedded resources。

 then code from this frame if these are all running in the same process JavaScript code from evil。

com can read contents from your bank。And so there's a really interesting paper on like how they went through this and the challenges that they ran into。

 there's a pretty good video as well if you want to read more about it。

But that is something that the Chrome team spend a lot of time on because they recognize that you know what。

 we're not going to be able to eliminate all rendered process bugs and we really need to get good isolation and so this is a tradeoff that we're willing to make。

Does this make sense to people？Thumbs up， thumbs down。Right。So you might be thinking like wow。

 this is a lot of processes。 This is like a lot of isolation。 Did this fix the problem。

 And the answer is no。 So sandbox escapes still happen every single year， but they are very。

 very difficult and they cost a lot of money and time to find。

But you'll see there were two exploits that were mentioned here。

The first ones the first one involves chaining together six different bugs to first break out of the render process then establish a communication channel that should not be allowed with with a GPU process and then it used a bug in the GPU process to break out of that then to break into the browser process and the second one uses 10 different exploits or 10 different bugs strung together in order to break out of the sandbox so it's still possible but it is very hard and there's a more recent one linked here。

If you're interested in checking these out， you can read afterwards。And then this slide。

 last Tuesday， I mentioned that you shouldn't call Fork directly。

 if you have a program and you want to be able to run different parts of that program concurrently。

 you should just put them in different binaries and then you should use ExVP to launch this other binary。

 it turns out that on Linux distributions。With Chrome in particular， this ends up creating problems。

Because it creates， normally it works fine， but Linux has a background update that will just up。

 it will like rewrite the files of an application even while the file is running or even while the application is running。

And it caused very， very odd。Bugs。Here that you can read about if you're interested。

 this is a really accessible link， so if you want to give it a read， it's pretty neat。



![](img/273e4e7ec71e372474f26e7df8760fdc_7.png)

All right， so with the remaining 20 minutes， let's talk about multi threading pretty quickly。

And I want to recognize that you do not have a lot of exposure to multi threadread yet。

So if you have questions about like， hey， what's going on here。

 let's take a slow and let's talk about it because you can't really understand the limitations and the safety issues of something if you don't understand the something in the first place。



![](img/273e4e7ec71e372474f26e7df8760fdc_9.png)

So let's talk about multi multi threading。 Why would you want to use multi threading， Why is it nice？

Yes， exactly， it allows you to get concurrency， so if you want to have some long running operations。

 you can do that without blocking the rest of your code。Why else？I'd say that's half the reason。

It's pretty fast， yeah。It's lightweight， threads are sometimes called lightweight processes。

Is there another advantage over multiprocesing， multiprocessing also allows you to get concurrency？

Yeah， it's definitely way easier to communicate。Sometimes too easy to communicate。And so。

 so those are some pretty significant advantages of mal threading。 Why is it dangerous？Yeah。

 exactly the same thing that gives it its advantage is also its Achilles seal。

 if they all share memory and you corrupt that memory in one thread。

 you're now corrupting it for all of the threads and they'll all go down together So you have to be very careful and specifically we have to deal with race conditions and with deadlock。

 So we're gonna focus on race conditions for now， we'll talk more about deadlock on Thursday and next week。

 Deadlock happens in rust as well。 Rus makes huge strides in avoiding race conditions but you still need to be very careful about deadlock。

😊，So this is a radiation therapy machine called the Theic。

 I don't know if I'm pronouncing it correctly， but it's called the Theic 25。

 and this was a radiation therapy machine that was used in the 1980s。

And it had two modes of operation， so there was a so it's an imaging machine as well as a radiation therapy machine。

 it's supposed to treat different kinds of cancer。So I had two modes of operation。

 one was called the direct electron beam mode in which it emits a low power electron beam directly at a patient。

And。I don't understand the medicine behind this， but that is supposed to be controlled in such a way that it can target。

Cancerous tissue。The second mode was called the， let's see， what was it called？嗯。

I just wrote it down as X- ray therapy， so there's direct electron beam therapy and there's X- ray therapy and in X- ray therapy。

 it still generates an electron beam， but it places this thing in between the electron beam and the patient and that thing absorbs the electrons and it ends up generating x rays out the bottom and it's a significant attenuator so in order to get a meaningful amount of output power。

 you need to have a huge input power much， much higher than you would normally use。😊，So two modes。

 one you just send an electron beams directly at a patient。

 and the other you put this thing in the middle and then you send a much higher power beam at the patient so that this thinging absorbs a lot of the electron beam and then it emits x rays at the bottom。

So here's a little diagram。This thing in the middle is what absorbs the electron beams and and emits x rays instead。

 And you should never have a case。Where you're generating very high output electron beam without this diffuser in place。

Does this make sense to people？And you can see how this might be a possible hazard。

And so this was released in 1983 and thousands of people were treated using this machine and there were no issues。

And then， I think， starting in 19。85， if I remember correctly， so over the course of four years。

The company started getting reports of people that were treated with this machine and had severe pain when they were getting treatment。

 some people would like jump up and one person jumped up and ran out of the treatment room。

And they started to investigate this， and these people ended up with severe radiation burns and many of them died。

And so。They were like， we need to investigate this。And so every time this happened， the。

 the creators were contacted。 And every time they said。We don't believe you。

We don't believe your report， we've looked over everything and there's no way that this machine could have hit these patients with such a high dose of radiation。

 even if there was operator error。We're saying like it's not even the operative of this machine。

They could do whatever they want， and there's no way that you could have a scenario。

 there's no way you could end up with this scenario where it's outputting a very high beam of radiation with no diffuser in place。

And they even sent technicians and they tried to reproduce the problem and they couldn't reproduce it。

 they'd like changed some things around， but the problems are still there。

So it wasn't until the fifth person died。m until they said， you know what。

 there probably is a real problem here and we really need to figure out out what it is。

And so there was a physicist at a hospital who sat down with a technician。

 they just locked themselves in a room for over a day until they were able to finally reproduce this issue。

This wasn't a lack of testing， I mean this thing was pretty thoroughly tested and they spent a lot trying of time trying to hunt down this bug。

 they looked at the code， they said， you know what。

 there's no way that we could end up with this condition。

 there is code to make sure that that doesn't happen and finally they came up with a way that they could reproduce the issue。

And in this investigation， they came up with a number of causes for this disaster。

One of them is that this is actually a pretty like difficult to reproduce issue it's an edgy edge case that only happens when you have a very specific sequence of keystrokes all within a fast period of time and this never came up in testing because the testing operators weren't fast enough to perform these actions within eight seconds but as people got better at using this machine as technicians got better at using it。

 they got faster and some of them。We're able to select these modes within eight seconds。

There are a number of other reasons， but the crucial one like the fundamental reason that caused this was a raised condition。

 they had two tasks which are threads or processes and the control task did not synchronize with the interface task properly and so if the operator went through these sequences too quickly within eight seconds then they were able to trigger the mode where this thing got moved out of place and then the operator tried to put it back into X-ray mode so this thing should have been moved back into place but it wasn't and a very high high amount of radiation was delivered to patients ultimately be killing them。

It's a pretty tragic story and this is a real world case where like you need to be very careful with race conditions because lives depend on it and you may say。

 oh， I'm not working on on。You know， medical。Cancer therapy devices。

 this probably isn't as important to me， but there's a whole range of areas where you can imagine race conditions severely affecting people's lives if you end up working on like computer vision software and that ends up getting used in a self-driving car。

 that matters a lot， it matters a lot in finance， maybe not for human lives， but certainly for money。

And so there's a whole lot going on here that you need to be very careful about。

So what is a race condition， I think the Wikipedia definition is actually quite good。

 It says a race condition is when the condition or the behavior of software is dependent on the sequence or timing of uncontrollable events。

😊，So if you can get different behavior from different timing of events， for example。

 different thread scheduling or different timing of people pressing buttons on a control interface。

 that is a race condition。And there's many different kinds of race conditions。

 the ones that we focus most on in CS110 and the ones that are most common are called data races。

So data race conditions are when multiple threads access to value。

 and at least one of them is writing。If you have multiple readers， that's fine。

 they're all going to read the same value， but a data race happens when you have multiple threads accessing and the value gets changed in the middle of that now you can read an inconsistent value or a completely corrupt value。

 we don't really know what could happen。This should sound really familiar。

This is what you guys have been dealing with for the whole quarter。

 even though we haven't been talking about multi threadreading。

I think this is pretty interesting because this is a case where Rust's early design paid off in a way that they didn't really expect。

 so Rust set out with three goals， they were trying to say how can you make safe systems program or how can you make systems programming safe。

 that is how can you do systems programming where you can be guaranteed you won't get a Se fault？

Also， how can you do multi threading Well， remember that this is an initiative from Mozilla。

 which started Firefox， this is Mozilla's response to the problem of browsers having so many vulnerabilities。

Browsers have to be multi threadreaded and so they wanted to come up with a way to make multi threadreading easier and safe。

And lastly， how do you do this fast and in the rust blog。

 they talk about how they felt like the first two bullet points here were separate problems that they were going to have to come up with a way to make systems programming safe and they were going to have to come up with a set of features in order to make concurency work well。

 but as it turns out these two problems are kind of the same problem and in what solves one problem also really helps solve another。

You create this ownership model to get safe systems programming。

 and that also ends up helping you avoid data races it actually completely eliminates them you cannot have data race in rust。

嗯。The compiler enforces rules to make sure that you have safe concurrency。

 and so it's not possible to compile a program that doesn't have thread safety。

Which I think is is really interesting。 And it's quite a bold claim。

 So we'll see over the next two weeks how well this claim holds up。Okay。

 so here is a quick example of how you spawn threads in rust。We have a vector of thread handles。

 which starts off as empty。 and then 20 times I'm going to push into that vector， a new thread。

 And then what you spawn a thread is you call thread colon and colon and spawn。

And you'll notice this like funky double pipe。Brackt syntax here， that is a closure function。

So by this point I think you've seen closure functions in CS110， for example。

 when you were running lower bound， a closure function is just an in line function。

 it's a function inside of a function， So all we're doing here is we're defining functions inside of a function。

 we could have put these three lines of code in a separate function and just put the functions name here and that also would have worked fine。

 but for the sake of brevity， we use closure functions and closure functions are very commonly used in rust especially in multithreading。

So we've got this closure function here， which just sleeps for a random amount of time and then prints a message。

And for the sake of time， I won't run it， but this does what you would expect it does。

 it just prints out thread finished running 20 times at different intervals。

This double pipe here allows you to specify the parameters for a closure function。

 So the syntax in C is you have like parentheses and then square brackets and then your function。

 The parentheses specify the parameters。 The square brackets specify the capture clauses like the variables in the outer scope that you want to use and then you have your function。

 Ru only specifies the parentheses。 The capture clause is implied。

 So here this function is not taking any parameters so that's why there's nothing in between the two like vertical bars。

And we're not using any variables here， so there wouldn't really be anything in the capture clause。

 but I'll show you an example later on where you can just use variables from this outer scopepe inside of this function。

 you don't have to explicitly say， oh hey， I'm using this variable from the outer scopepe。

And then you might notice that when you do a join， you have to do this expect and that might feel a little weird because you're like。

 well， I'm just waiting for the thread。Why does that return a result？

 So the reason that join returns a result is if a panic happens inside of a thread。

RestT is designed so that that panic isn't going to take down your entire program。

If one thread panics。The main thread， all the other threads are going to continue running unaffected。

And。Most of the time that may not be what you want like most of the time if a thread panic。

 something is wrong with your program and you should probably quit。

 but in very high uptime situations for example， Arman works on an embedded operating system called talk and it's for embedded devices for hardware really that like needs to stay running and in that case if you have a panic inside of a thread。

 you probably don't want to take down the whole device so long as the device has some amount of remaining functionality it would be better to log the error and alert the developers but to do your best to try to keep running so that's why this exists here and in our cases we're always going to unwrap or call expect here because if a thread panics really like we want to quit there's nothing much that we can do here。

But that's why we have expect here。Makes sense。Any questions so far？Allright。

 so here is the extroverset example from CS110 where it goes through。

 it creates a bunch of threads and each thread runs this function。

 So each thread gets past this value I this loop counter I and then it goes into this array and it selects the Ithe element of this array and prints out hey。

 I'm that person empowered to meet you So really we should see， hey I'm Frankra， hey， I'm John hey。

 I'm Laura and hey I'm Marco， hey I'm Julie， he， I'm Patty。😊，Potentially in different orders。

 but we should see those all printed out。 And if you run this example in C playground。

 you'll see that that's not what happens。 Does anybody remember what happens here and and why。



![](img/273e4e7ec71e372474f26e7df8760fdc_11.png)

Yeah， you you frequently get this last entry printed which should not be printed at all and you also end up with okay。

 so here it was printed like almost all the times Sometimes you end up with duplicates Oh this isn't going great Jerry is dominating the conversation this time Sometimes the same name will get printed twice。

 not just tag along introvert Jerry Does anybody remember why。



![](img/273e4e7ec71e372474f26e7df8760fdc_13.png)

Why this happens like what is broken here？That's exactly right， you're passing a pointer here to I。

 and really you're intending to pass a reference to this variable I to this function。

But at the end of that four loop， that variable goes away， it goes out of scope。

 and then it gets recreated with a different value at the top。

 and C implements this so that every time you iterate it is the same piece of memory。

 but conceptually you're hitting the end of the loop， that variable is going away。

 it's going out of scope and then you're creating a new variable at the top。😊。

So if we were to write this in rust， this is what it looks like。

 it's a direct translation same array， same thing I just spawn six threads。

 I print hello from names of I and then I join and wait for all of those threads and I mentioned that you can just use variables in the parent scope without having a capture clause so you don't need to explicitly say。

 oh hey， by the way I'm using this variable I the rest will figure that out for you。

So if you try compiling this， it doesn't work， the compiler will complain because it will say， hey。

 you're trying to use variable I inside of this thread。

But there's no guarantee that this thread is going to finish before we go on to the next iteration of the for loop。

嗯。It's possible that this reference to I might outlive the variable I here。

 and that's really the problem in this C code is that we're passing a pointer to memory that goes away and gets reused for something else for the next iteration of the loop but the rust compiler will not allow you to compile this program because it will say。

 hey， you're trying to borrow a reference to I for this lambda function。

 but there's no guarantee that this lambda function is going to finish running before I gets delocd for the next iteration of the for loop。

Does this make sense to people？So this is just one of several examples that we'll go through of taking CS110 lecture code that is broken and trying to get it to compile and rustt and it won't compile Rut will not let you compile code that has data races in it so we'll see this more on Thursday and that is all I have for today so thanks for coming stay after if you have any questions and we'll see you on Thursday。



![](img/273e4e7ec71e372474f26e7df8760fdc_15.png)

Mmh哼。😊，Yeah。That's a really good question you'd have to ask yourself。How are these playing out？

And the answer is。It's rough in both camps， so Google Chrome clearly still has vulnerabilities and Google Chrome has a vast majority of market share。

Which means that similar to like Windows， okay， maybe Windows was actually less secure than Linux。

 but the reason that Windows had so many viruses was not because that it was so insecure。

 it was more so because everybody used it and so it was a more valuable target like Linux has vulnerabilities too They're just not as commonly targeted。

So。Chrome still has vulnerabilities。 You could make the argument that， well。

 maybe it's because they're popular and so they're more commonly targeted。

 and that's why they have just as many vulnerabilities as as Firefox。

 I don't actually have the numbers， so I don't know how the numbers compare。

But they both have vulnerabilities， and I think we actually need to combine the approaches from both camps because as you can see。

Chrome has gone to this immense sandboxing effort and they still have vulnerabilities。

 like we still need more， we still need language constructs to make vulnerabilities less likely and to be able to spot them more easily。

And on the other hand， you look at Firefox and Firefox has been making this very expensive and long investment into rust。

 trying to make it so that we can't have the vulnerabilities in the first place。

If you write everything in rust and you don't have data races。

 then we shouldn't be able to have the vulnerabilities where people can escape out of processes and sandboxes and whatnot。

What do you think about that argument， anyone？Excellent。

 that's exactly the argument that I would make。 First of all， there is still unsafe rust。

 if you are using libraries， especially some libraries will will frequently use unsafe rust to。

 to try to work around the restrictions of the borrow checker。 Sometimes rust limit to you too much。

 and you have to be unsafe。 And then you don't have the guarantees anymore。

 Even the types that are meant to like have you do like safe multi threadtting use unsafe rust under the hood。

 like atomic reference countered pointers and mutexes， those use unsafe rust， right。

So like what if there's a bug in the standard library？Are you truly safe if like？

If your code is provably safe， but the code that you use is not。

Like it doesn't quite work out so cleanly。 and the other thing which you also mentioned is that。

Rust is very nice in that it prevents certain classes of bugs and certain classes of vulnerabilities。

 but it doesn't prevent everything。 And I mentioned this like theac 25 example。

 I don't think the theac 25 example was caused by a data race。 It was a race condition。

 but it was a race condition at a higher level。 It was a race condition in the synchronization and communication of these two processes。

 It wasn't like， oh， one process wrote a value or one thread wrote a value and the other was in the middle of reading it。

 I mean， it was a race condition over 8 seconds。 So it doesn't sound like a data race to me。And so。

 you know it's not going to rest is not magic and it's not going to solve everything。

Mozilla has acknowledged this and Firefox is moving to a model where they use more processes。

 but it's a fixed number of processes， it's like four。

 and then they'll load balance the tabs over all of the processes。

 so you still end up with processes that house multiple tabs from distinct origins。

So we need both is my response。I think Firefox needs to do a bit more isolation and。

Chrome is making more investments into language safety。Yeah。It's mostly at a C++ level。

 so we'll talk a little bit about how some of these concepts translate to C++。

 but you can do some of the things that Ru does in C++ C++ will not force you to write safe code。

 but it does provide you with features that you can use to write safe code。

And then what you can do is you can write Lter rules on top of that。That say。

 I don't know if you know what a Lter is。 It's just like a code style checker。

And so it will give you errors if you don't follow whatever the L policy is that is written Use St copy。

 how dare you like Yeah， exactly so so very common practice in C code basiss to havelins that disallow unsafe functions like getas we mentioned on the first day。

 St copy is unsafe so on and so forth。 So they'll use L rules to make sure that developers use these safe constructs that they create in C++。

嗯。Yeah， it's more reactive than proactive because they basically have to go through and say， oh。

 you know what， this has undesired effects， we shouldn't be using this thing and then you have to go and refactor it out of your code basease and write a L rule to make sure nobody ever does that again。

 but from my understanding that's their approach。