# CppCon【中英⚡CppCon 2024】 p14 P15 Modern C++ Development： Limitations and Problems in std：：function and Simila -BV1NHEEzdE92_p14-

![](img/4ea3543ee07bb8b5a33afd36ed9a6c52_0.png)

Welcome everyone。 It's great to see all of you。 If you are new。

 welcome to this vibrant C plus asminity。😊。

![](img/4ea3543ee07bb8b5a33afd36ed9a6c52_2.png)

The fresh perspective， few people brand。Is the one which will evolve the C plus plus going forward。

 So keep this enthusiasm up。

![](img/4ea3543ee07bb8b5a33afd36ed9a6c52_4.png)

And I am looking forward to learn as much as from you and。In the exchange。

 I would like also to teach you something which I have learned over workinging with C plus plus。

So my name is Aman and I have been working with C++ for over 19 years now。

 and I have been developing cross platform applications for Adobe。And during this time。

 I have drawn into deep into the interests of this powerful language。Today。

 I will be talking more about what limitations I ran it to when I started using standard functions and similar constructs。

These construct are very powerful and they are highly useful。

 but they do they do tarry certain overhead， which initially you might not entroer。

 So that's what I will be。Ding through， but don't worry I will just not review the problems。

 I will also share the solution which finally we were able to dev and then get over those。

So with that， let's dive into anti a closer loop。But first。warningarning the code is slideware。

 so it's just so that it fits in the slides， there are certain things which I removed but don't just drop paste but yeah databases that photos on conceptcepts and patterns。

Plus， please stay uned and question whenever you have any question come up and it's better to clear that there itself。

So， this is what。咪。W lookslight so in Adobe we have like a host app and there are multiple service providers which can termm with each other host app is only allowed to termmcate with the service providers and below the service providers there are core modules and cloud services so all the service providers are able to termmcate amongst themselveslf as well as to the cloud services and core modules and these are the two module service module service providers and workingon which is CC libraries and cloud dots。

And。If we see the landscape on which I worked on， this is the trend of products micro grows into so starting from Photoshop in design illustrator on desktop to like new offerings like Frestro and subst and all the video products on mobile also the same code is consumed by Fresco which is our drawing wrap and whatever we have also。

P Photoshop to mobile devices and even on the web。So the strategy most of the time is we use Wam to tra our C plus plus Ch and then use it on the web platforms also。

But I do work on JavaScript also， but not that much as much I vote on C++。Now。

 if you see the service providers。So initially， when we like。

7 to 80 is baed each tour service provider， or each tour module was。

Able to generate trade on threads and vote on that。

 And that actually bit us very badly when we started porting our code to mobile platforms where we are constrained with the resources。

So the strategic step was taken that none of the providers are the tour modules。

Will generate create any thread。 So the host app during the initialization will provide three different task use。

 which the tour module is allowed to use to。Into the task on those。

 So first one is the synchronous task to where we want。 It is a。serialial task you。

 where whatever connce you want to achieve within your data model， you can push all the tasks there。

 and you will be 1 hundred0% sure that they will happen in a serial way。

 And then the background task you is generally a conrent to where you can。

Push launderrun in task or the things which which does not involve that your data model will be disrupt with that and notify notify task view is the way whenever we get any notification。

 for example， from the cloud， we to know that the cloud dot has changed or something has changed and we need to provide the notification to our step that something has changed So that is the task you for that purpose where we push all the notifications and last one is like draw that whenever our initialization is done。

 we let the app know that whether we were successful or there was some issue。So。

 taking that thing into。Mind。So， let's。Tate a little bit how many of you love landers。

And if you love， you must be using it。So， the lamb does。Like， I have just put very。

Simple examples of lambda， just to。Said the context。So these landers are very simple。

 They don't capture the state。 But when we are。Ding to push。Trowode onto another onto the task queue。

 which can executing in a separate threat。 We do need to capture state。

So how we can capture state within our lambda。So we can use the traction mechanism， but。1。

 before going into that， all the chapters， what actually。Happens behind the scenes。

 I will be using this instrumented class where if any move happens。

 I come to know because the I D will change if there is a tropy happening。

 the tropy will C will be appended。 So this will be our。instrumentnstrumented class。

 which will help us understand what is happening behind the scenes。OfWhatever we are capturinguring。

Now， since everyone has used lambdas。Can you guess what will be the output of this road。

Where I have like two instrumented classes， one with IDA and one with IDB。And I capture them。Of。Yeah。

 I capture them by reference， and then I invoke the lambmbda。So what will be the output。

And what will be the size， Any dresses。What is the reference， actually。It's a pointer。Internally。

 so there are two pointers getting capturedd。 So the size will be of the lambda will be。

Size of two word periods。 And if we see the output， it has given me that the。A and B。

 which there is no tropy happening。 There is no move happening。 And that is what we expected。

 And the size is 16， because my machine is like 64 B machine。Now。

 if we change our code a little bit and。We rather than capturing by， we capture by。Value。

 so we change。And we capture by value。Now， what will happen。Any this is。再ぞ。

What the output will be different。 That central percent here。Yeah， size of will be different。

 Will there be the when I'm returning the Ids， will there be a change。

Tppies will be happening and the size will change and perfectly dress there is one tropy happening on a and aroppy on B and the size of lambda has increased to 64 bit which each instrument class has a strength which is 32 B and 32 bytes and 32 2 captures so 64。

So any questions still now。To date the groundwork。For the。Next stuff。So， this is。

What Bar has written in one his book land expressions are anonymous functions that can be defined at the point where they are used and they made your road more transcise and reliable。

And I think it capturees the threats of landers。But。😡，Lmbs are so tall， but。

Can they be used as data member of a class。Sttoed in a container， like Q or vector。喂。

W was they return a closure and the closure type is unique unnamed trust type and size is different based on the captures。

So we transform Lambdas with as a data members or。Now， if that's the T。

We can't even use them in any task base frameworks， as we need some type， which we can control。

 We can't just pass a lambda to the task base。Framer that please attitude this landda。

 We have to wrap it。And for that stood function。Is the。Ovi choice。

 And we will discuss that a little bit also。So， this is what my。A P。

 which I was supposed to work on the task field looks like this is provided by a true module。

There is。

![](img/4ea3543ee07bb8b5a33afd36ed9a6c52_6.png)