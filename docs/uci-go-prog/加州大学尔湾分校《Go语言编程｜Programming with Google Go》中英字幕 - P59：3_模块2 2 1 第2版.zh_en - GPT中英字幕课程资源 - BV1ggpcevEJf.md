# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P59：3_模块2 2 1 第2版.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/c65c6aa9ab2eeb91777c8834a03a34b9_0.png)

Module 2， concurrency basics， topic 2。1 interleavings。So writing concurrent code is hard。

And part of the reason why it's hard， a big chunk， the reason why it's hard is because it's hard to have a mental model of the state of the program at any particular time。

 So what it mean by that is if you're writing sequential sequential code， regular old code。

 and it crashes on line 10。 Then you know what's been executed before that， You know。

 it must execute line 9，87，6 and so on。 And you know basically what order。

 And so it helps you figure out what the state of the program should be where it crashed and you sort of implicitly depend on that when you debugging。

 you say， well， I know it got to hear， So it must have done that and that right。

 and that helps you 0 in on what the problem is。 with concurrent code。

 it is much harder to get a bead on the state of the machine。 So when it crashes。

 maybe it crashes at line 10 in task 1。But where is it in test 2，3，4，5。

 right it can be in different places。 So the state。

 the overall state of the machine is is not deterministic。 meaning so by that， I mean。

 say you've got to crash， it crash it on line 10 in task 1 every time。

 but every time it can be at a different point in the test 2 or3 or4 So every time you run it even though it crashes at the same line in task 1。

 it may be a different overall system states every time。

 So it makes it confusing to sort of keep in your mind。

 this variable should be that and this variable should be that because maybe this task has done something or maybe it hasn't and you don't know what's been done what hasn't So this is really to me the hardest part。

About programming concurrent writing concurrent code in any language so just to show you what the complexity is here。

 you have what to call these interleavings， the interleaving of the instructions in two different tasks。

 So the order of execution of statements in the task is known。

 So for instance I got task one test2 and each one has three instructions in order1，23。

 and these just random instructions it doesn't matter what they do。 but you know that in task1。

 the instructions are executed in order1，2，3 test2 they're executed in order1，2，3。

 but the order of execution between concurrent tasks is not known is not determined。

 meaning it is's not deterministic， it can be different every time。

 So what that means is these instructions can be interleaved in different ways。

 So I might execute the first instruction for test one， then the first instruction for test2。

 then the second instruction for test1， then test two second instructions so on but that's one possible interleaving of instructions。

 but there are many possible interve。

![](img/c65c6aa9ab2eeb91777c8834a03a34b9_2.png)

And all of them could happen and so every time you run it。

 you might get a different interleaving and so it makes it harder for you to keep for a program to keep in their mind know because you have to consider all these interleavings when you're thinking about the correctness of the system now hopefully not all there are techniques to sort of minimize it。

 but you have to consider many different interleavings in order to reason about how the system behaves。

😡，So here's an example。Of a couple of possible inter leavingavings。 So on the left， the left column。

 So they got two little tables， right one on the top， one the bottom。

 the top is shown one inch leaving。 the bottom sh another。

The left column are the instructions in the task one。

 the right column are the instructions in task 2 Now the top interleaving。

The top one is showing is just alternating between instructions in one task versus the next。

 so task one， instruction one， task two， instruction one， task one， instruction two， task two。

 instruction2， and so on。Now the bottom inter leaving is saying， look it fully executes task1，1。

2 and3， and then it fully executes task2 right 1， two and3， that is possible too。

 and there are many more so there are many inter that are possible and you have to consider all these possibilities at least some subset of these possibilities when you're thinking about does your code work correctly or not？

Now one other thing that I'd like to mention is that these interleaving。

 the interleaving problem is even a little more difficult because the interleaving doesn't happen at the level of the C encode code or or go code right So you write these instructions。

 let's say these are go instructions So the interleaving isn't happening at the go instructions level iss happening at the machine code instructions level。

 So what I mean by that is that first instruction A equals B plus C in go， maybe that's all it is。

 but if I were to look at the machine code for that that might be know several four instructions long。

 I might be doing a load B from memory load C from memory add them together and then do store a it might be four machine code instructions long。

😊，And same thing with each one of these instructions。

 So the interleaving is happening even at the machine code level。 So what that means is。

You're not guaranteed that it finishes instruction one before in task one。

 before it starts instruction one and task2。 So a so take that a equals B plus C in the top end leaving right the first line in task one。

Say that takes four instructions， for machine code instructions。 You might execute the first two。

 and then it stops and goes to task2， right， So you might not even finish the first instruction。

 So these instructions， the interleaving is happening even in between these instructions。

 because it's happening at the machine code level rather than the source code level that we're looking at right here。

 So that makes it even harder to sort of get a handle on all the possibilities。Thank you。

Module 2 concurrency basics， topic 2。2 race conditions。

So a race condition is a problem that can happen as a result of all these possible interleavings that you have to consider。

Race condition is technical a iss usually defined as a program that runs a problem where the outcome of the program depends on the interleaving right now the interleaving remember is not deterministic。

 it's determined by the operating system in the go runtime。

 so the interleaving can change every time you run it。And in a lot of ways， it has a lot of freedom。

 And so so you have basically a nondeterministic inter leaving。

 but you never want a program or almost never do you want a program that whose whose result is nondeterministic。

 you want to be that if you run a program and you give it a set of inputs。

 it always produces the same outputs that's determinism right if a program is nondeterministic。

 you take that program， you run it with a set of inputs。 sometimes it gets one answer。

 sometimes it gets another。 that is almost always a failure。

 that's nondeterminism and you don't want that。 But remember that the into leavingavings are nondeterministic。

 you don't know what the inter leavingaving are。So you have to make sure that your program that its outcome does not depend on these interleavings if it does。

 that's called a race condition。 So what I'm showing here is a little example， just toy。

 we got these two tasks and we're showing two different inter leavings of the two task Now the first task all it does is instruction 1 says x equals1 and instruction 2 says x equals x plus1 okay so real simple。

And on the right hand side， you got task2， and all it does is print X。Now。

 in the first interleaving on top， it's going to print a one because x isthe equal to one at the time when the print happens where in the second inch leaving X is going to print a2。

 X will be printed as two because it's a different interleaving。 This is a race condition。

 The outcome depends on the interleaving and the interle is not deterministic。

 So this thing has not deterministic output， and that's basically broken。Now。

 so this needs to be avoided。 This is one of those complexities that happens because of all these interleavings。

Now， race conditions， there are ways to avoid this type of thing and make sure it doesn't happen。

 and we will talk about that and go。Race conditions occur due to communication。

 communication between tasks or go routines that we're going to talk about。

 So there's communication between these two tasks。 I don't know if you see it。

 but they're communicating on variable X So the one task on the left it's writing to x is assigning x to1 and assigning x to x plus1 to2。

 where the other task on the right is reading from X is' reading from it and then printing it right So they are communicating through this shared variable called X。

And that that's communication。 And that's where race conditions occur。 See。

 if you had no communication between two different tasks。

 you would never have a race condition because the ordering would be completely independent of each other。

 But meaning when I say completely independent， the outcome would be completely independent of the ordering of the interleaving。

 Okay， But when you have some kind of communication going on between。Between the two。

 then it matters which instructions in task one， say which instructions it right to this shared variable。

 which ones happen before task2 reads from the shared variable。

 So communication is sort of the source of race conditions， but communication。

Is very common between these different go routines。So different tasks。

 they generally communicate Now， threads in general， whatever language。

 threads are largely independent okay， they're independent of of one another。

 but not completely independent。 So what does that mean。



![](img/c65c6aa9ab2eeb91777c8834a03a34b9_4.png)

They're largely independent， meaning they mostly don't have to communicate with each other。

 right the whole reason why you've made two different threads or go routines is we're going call them and go。

 The reason why you've made two different threads is because you feel like these two things can be executed concurrently at the same time right without caring like you know which one execute first or second。

 they can just executed at the same time。But they're never completely independent because if you've got multiple threads all in one process they're sharing information。

 right， remember how threads have they share common data right。

 they share the virtual space and all this。's the fact that they are different threads in the same process means that they are sharing。

 so theres it's very common that there's some level of sharing between the threads and the sharing of information is communication。

😡，So for instance。Web server is a really common sort of multi threadreaded application。

So in this picture， the web server， you got in the middle， you got this web server。Now on the right。

 you've got these clients。 These are web web browsers okay and they're connecting to the web server over the network and they're I'm showing three。

 but there can be any number of them。 Then on the left。

 I've got the web page data right so this web server。

 say it's a UCI's web page is UCI's web server It's that orange data is all know all the data on all the pages that we have and that's going to be together with the web server and some some disk or something right。

Now， as these clients come in as they make connections。 so one browser comes to the website。

 it wants to look at one page。 Another browser connects。 it wants to look at a different page。

 different subucI page。 Another client comes in and wants to look at a different one。

 right So this web server program， it makes a lot of sense for it to make a thread for every client that comes in。

Because each one of these communications， like this communication with with one particular client。

 it's likely to use to do different things。 this client。

 maybe it wants to look at this web page where the next client wants to use another web page all within UCI。

 but different subpages So it makes a lot of sense to do them as multiple threads because these clients are all coming at the same time So it's the type of thing where you have to handle all these clients all concurrently you need to handle I mean you don't want to have a web page that handles one browser at a time right you got to handle them all concurrenly。

 So it makes a lot of sense to make this a multithreaded application。

 You got one thread for each client。😊，Now， these threads are largely independent。

 but they do share data sometimes you can have two clients come in and look at the same web page。

 right， They might both be looking at the top of the web page。 Also， you can have。

 notice these arrows between these blocks are two way。 So， for instance， you can have the。

 you can have a web page with a client。Sends data basically post data to the web page。

 We don't want to get into a webp page too much。 but the client may post data to a web page。

 actually changing the web page。 Like the most obvious place where you see this is sometimes you see a web page where it has a counter like a visit counter。

 right That data is changed every time a client connects。

 the counter goes up one right So that counter value say there's another client who comes into that same page。

 He's got to see the updated counter value， right So in this way。

 one client is writing to the web page， increasing the counter value。

 And the next client is reading from that same page。

 reading the new counter value and then writing back to it， increasing the counter value again。

 So the point though， is that there is some level of communication between these clients。

 they're not completely independent， they can be looking at the same subp。

 looking at the same files and data and so on。 So periodically they have to communicate with each other。

 So now it shouldn't happen too often。 If there's too much communication between two threads。

 you probably don't have them in separate threads。 If they're communicating all the time。

 then you should probably just make them one go routine don't separate them。

But if they have if they're separate mostly， but every once in a while having communication。

 then two go routines makes a lot of sense because they can execute concurrently most of the time。

Now， another example I have is this image processing example。

This so image processing tasks are often what they call embarrassingly parallel。 So image processing。

 say you got some big image。 you got some images。I don't know， a megixel， okay。

 it's got a million pixels in it。And you want to do some processing。

 You want to do a blur or something like this。 Okay maybe you want to blur the pixels。

 So with a blur， basically， it'ss a pretty localized operation。 You look at a pixel。

 You look at the surrounding pixels you average out the values。 But this same task。

 you got to do it on every single pixel。 So this type of thing。

 It makes a lot of sense to have multiple threads。 You got one thread dealing with some pixels。

 Another thread dealing with the next set of pixels。 Another thread dealing with the next set。

 I'm only showing two threads right here。 I actually， this is in an extreme。 This is what a GPU does。

 A graphics processing unit。 This is exactly what a GPU does。 You might have 1000 cores on this GPU。

 and it'll take an image with a million pixels。 and they'll just divide up all the pixels between the different cores that all running on different threads on each core。

😊，So this is a common thing where it's easily parallelzable。

 know one thread can work on one set of pixels， one can work on another。

 but not completely parallelzable because take like a blur。 a blur。

 you look at you're analyzing a pixel， you got to analyze the neighboring pixels and average their values So you are not completely independent of the neighbor if there's another thread working on your neighbor pixel。

 those two have to share information this guy has to know the pixel value on the neighbor。

 this guy has to know pixel value on the neighbor。 So there is some communication between these threads。

 they got to share whatever their pixel values of the neighbors have to share So even though image processing is you can largely parallelze it and shop it up amongst different threads。

 there's always some level communication between the threads and you have to be able to support that And so remember that this communication。

 if you don't support it correctly， it can be the source of race conditions where if one happens first before the other one its some weird into leaving。

 you get different results So this is part of what makes concurrent programming very。iff。Thank you。

