# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P11：-11-Lecture 11_ Synchronization - GPT中英字幕课程资源 - BV1D142147he

I think we're just gonna jump right into it especially because I'll be starting with a review of what we were talking about at the end of last lecture so welcome everybody today we're gonna be talking about synchronization in rust with regards to multithreading and we'll start transitioning into some new interesting synchronization primitives that Ryan's going continue talking about on Thursday so first off I want to reiterate what we were talking about at the end of the last lecture which was this link Explorer thing which so you know the idea is know you can try to like hop between Wikipedia pages and try to like start it like some word like I don't know like disentre I don't know why it chose that's pretty random and then like get to revolver right but for our purposes we're going try something a little bit simpler and we're just going see can we just scour the entire Wikipedia page and try to find the link that has say like the largest web page so to speak in terms of like the size of the HTML right so we're going to try。



![](img/57982b92c6ef1168c6b49c56fbf579b3_1.png)

![](img/57982b92c6ef1168c6b49c56fbf579b3_2.png)

do this sequentially and I think I showed you'all last time I'll actually just swap out of the presentation right now and I'll share another screen so I will share my terminal so can everybody see that。



![](img/57982b92c6ef1168c6b49c56fbf579b3_4.png)

![](img/57982b92c6ef1168c6b49c56fbf579b3_5.png)

So I'm actually going to split， and then we will。I'll show you。Actually， let's get out of。

 so I'll show you the sequential version link Explorer， it's very sad。

 So if we just go cargo run right here。😔，This is how it's doing it sequentially it's just going through all of them they're like you know there are a lot of links but you might be wondering like you could probably overlap this so I actually ran this and I think it ran for something like three minutes or something which is not very exciting but if we do it multithreaded so if I go to。

Exploring multi。And then if I just do cargo run， it's able to rip through all of them pretty quickly。

 still not， I guess not like blazingly fast， but there are a lot of links come on。

 So this is this is pretty exciting。 and artificial intelligence as we saw last time is the most important topic and all of computer science。

 So I thought everybody should know that， I guess that's what Wikipedia thinks at least So let's open up。

 Let's actually look into this code a little bit。 I brushed over really quickly last time。

 So I actually want to look into it more and I'm gonna open up main Rs so we can see it right there。

 Let me see if I can actually make this a little bit wider。 Can everybody read that Okay。

 Is that okay。😊。

![](img/57982b92c6ef1168c6b49c56fbf579b3_7.png)

的事。I can drag that to the left there。 So there's this library called request with aW。

 So that's that's exciting right there。 And I do this thing request block and get to get the actual。

 this is kind of like the root page so to speak。 So this is the multithreading page and this is just performing an HtP request。

 we're gonna talk about networking a little bit later。

 when I say HtP request think of it as I'm downloading the web page I'm downloading the Hm of that web page it's just a bunch of text So I go to a server and I say server I please have this string that represents this web page and I get that back and I store it in body And then what I'm doing here is these are some functional rust shenanigans basically but I'm just filtering the body to look for certain tags So I'm looking for a particular link tag right here That's all that code there is doing so。

Well the really exciting part of this though is the fact that we have to use a Mut to protect a shared piece of data。

 so take a look at this right here for a moment， we have a little struck article that's starting at line 18 right there。

And you might be wondering， first of all， why do I need to make a struct to store the URL and the lens so I guess based on what we talked about Mutexes from what we talked about Mutexes what we said about Mutexes last time like why do I need why do you think I might need to group these two things together in one struct？

Can somebody just give a quick answer to that？So what do people think。

 or maybe it might be more helpful if we see how the mutex is constructed right here to remind you of how that works。

 so that's happening on this line right here on line 45。Where does it get used？

Where does it get used， it gets used， so longest article。

 we clone it right here and it gets used over here。When do we obtain the lock on it？

I guess my question is， kind of， you know， in rust。

 could I have used one Mut to protect two separate things？

If they were not already like the same piece of data and why not？What do people think？

Any thoughts maybe it might be helpful to think about， you know， this arc。ItTrapping a piece of data。

And thiss meex like how does this like what does the constructor of the metex look like， right？

Two references to audio you mean in what sense？Exactly。

 it totally it's it's a reference wrapper right， but why is it that I can't have this one me text just protect two separate pieces of data like if if。

 if this is what we know about the interface， like if this is if we know that the constructor looks like this。

ReReally， I'm trying to like get to something about the constructor， I'd say。

So to contrast this with C++ and C++， you would just have two variables and then you would have a third mutex variable and before you use either of those two variables you lock the mutex and then after you're done touching those variables。

 you lock the mutex again， you don't have to put the variables in astruct or a pair or anything。

But Arman is saying that here it's not like that we don't have two separate like URL and longest length variables。

 we put them inside of an article struct and actually we had to do that， why did we have to do that？

Let's say it mainly has to do with the constructor of new。

Precisely that's exactly right The constructor of the Mutex needs to take some data to protect in particular it needs to take one piece of data。

 so if I want to protect two things with the same mutex I need to package them together into the same struct like an article right here and I'd say from a design standpoint this is actually very nice this is called like the monitor style I think of like concurrency where you want to take pieces of related data and group them together we're forced to do that by rest's type system because the Mutex the constructor takes in exactly one piece of data Does that make sense to everybody Are there any questions about that。

I think it's totally fine if there are questions because when I first saw this。

 I was very confused that like the metexes I've seen before。

 they don't take anything in it's just like you know you declare a Mutex and then you lock it and then you unlock it the weird thing here is that when we lock a metex it returns something oftentimes when you lock it like back in C++ when you use to lock a metex right you don't return anything just like it has some side effect but here locking returns a reference to what's inside it returns a reference to this longest article and then now I can but now I know I have exclusive access to that longest article this shared piece of global data or I guess global in terms of that all the threads can see it and update it and now I can perform this check I can say if the length of the current article is greater than that of the longest article I need to update what is the longest article and then finally I just I go through all the requesters in this batch and。

Join so the batching logic it's sort of like I spawn， you know。

 a batch of threads and then I join then I spawn another batch of threads and then I join you might be wondering why do I need to do that Well。

 let's see what happens if I just make the batch size really bad really big right so if I make it 100 right you know hopefully it should be able tostand this right Does anyone have any predictions about what's going happen。



![](img/57982b92c6ef1168c6b49c56fbf579b3_9.png)

Cart cargo， Sam thing。What do you think happens if I just make the batch size too big if I have too many threads at once。

 what could happen？Yeah， so that's really that's a really interesting point I'd say definitely for like CPU bound things that's especially the case right because if you don't have many cores and you're doing something like maybe you saw in CS110 La with the quickword example then the overhead of context switching is gonna you know not let you win by multithreading but here because we're IO bound I'd say like oftentimes just like having more threads in general is better because you can overlap lot more waiting times。

But yeah， any other thoughts for what might happen if we have too many threads？Before we just。Yeah。

 I mean that's a good point。 so oftentimes Devlock happens when you when you have like more than one resource right that's limited in some sense。

 but I guess here we only have this one mutex， right。So let's let's see what happens here。

 So I run it and it's building。 and all right， it's gonna be so fast now because we have more threads and oh no。

 what happened right let's take a look at some of these errors。

 So error it panicked So the threads panicked。 the threads were really sad failed to look up address information。

 No didn more server provided or not known so but before that。

 it was saying something about there being too many open files right， too many open files。

 too many open files right， and it did this。 It got there really quickly So yeah。

 what does that tell people。😊。

![](img/57982b92c6ef1168c6b49c56fbf579b3_11.png)

Can I just like you know make as many threads as I want like make as many requests as I want no。

 right we need to throttle ourselves in some regard。

 I guess so this this probably doesn't make sense to people who haven't seen networking before。

 but when you try to establish a network connection to a server like when you try to telephone a server to try to download some information from it。

 it creates a file descriptor that is linked to that server that you can talk to that server through the file descriptor So if you try to create too many connections to a server at a time or to servers in general。

 if you try to create too many network connections so that you're downloading a lot of things at the same time you actually run out of file descriptors and that's what happened here is the system crashed because it tried to open more connections than the system could handle。



![](img/57982b92c6ef1168c6b49c56fbf579b3_13.png)

Exactly， exactlyly really strained our operating system。

 We ask too much of it really and really the issue here like another thing you should think about those like you also don't want to like overwhelm other servers with requests either like that's also not a very nice thing to do so there are different stages of like limiting that you want to consider for the sake of not you know I guess dedosing different resources that you have but know in terms of like there's some problems with this batching thing and I'm not gonna to focus too much on it because just for the sake of time just so that we can talk about other things but like the main issue is that it's not very flexible。

 it's not very dynamic right another thing is you can easily reuse threads we don't have to spawn and destroy threads you should really be using a thread pool for something that looks like this but you'll have plenty of fun implementing that in assignment6 of CS11。

And you know if like once you finish that you might even want to implement it in rust。

 I think that would be a great exercise it might even be easier So let's think about can we do better than batching right we needed it because we didn't want to overwhelm resources you know a more effective way that you might have seen in CS110 lecture with regards to semaphoes was that you can use semaphos as a way to limit sort of like a number of permission slips right so I need to ask for permission to be able to start downloading an article and this is one way to throttle ourselves right is everybody familiar with this usage of a semaphore Are there any questions about this usage of a Semaphore。

Okay， I think Jerry might have talked about this last week。嗯。

And you'll see this definitely in the CS110 assignments in assignment5。

 and I think you know a good precursor to that is if you I'll post the link Explorer example on the website and you can try to upgrade that using a Semapho or using what we're going to build later today in order to thttle the number of requests and that's essentially the same idea that you'll be doing in assignment five for CS1 time。

So right so in order to implement something like a Semaphore we need to first understand what a condition variable is and totally understand if people are not down with condition variables yet because Jerry just talked about it in lecture but let's quickly go over what it looks like in C++ so this is the implementation of semaphore that Jerry presented in lecture and as you can see in order to so a condition variable I guess just to give a quick overview is very similar to six supend that you might have seen in multiprocessing and the idea is that you acquire a lock of some sort right so in the case of six su spendd you were blocking signals right so you're saying I don't want to respond to any signals just yet right you acquire some sort of lock and then you check a condition right you want a particular condition to become true。

But in order for this condition to become true， you need to let go of that lock because something else is going to update it and you don't want to like lock on it forever else you'll just be deadlocked。

 right？What you do is you obtain a lock， you check a condition， and while that condition is not true。

 you wait and while you're waiting， you're not blocking， you're not consuming CPU resources。

 you essentially think of it as like you're marking your thread is blocked。

 right you're getting moved onto the B queue so you're not wasting time on the CPU。

And then you might get notified right and once you get notified so in the case of signal we're notifying all who are waiting on this condition variable once you get notified。

 you wake up。You reacquire the lock。And then you're able to safely make that check。

 and then you do what you need to do once you pass， like in this case， decrementing the value。

 and then once that lock guard goes out of scope， it will release the lock。

So I just said a lot and I totally expect there to be questions because maybe even if you didn't see this in 110 lecture recently。

 it might have been a while since you saw conditioned variables。

 so please somebody ask a question about conditioned variables。Right， okay。

 so you're asking why do we need to notify all？Yeah。So yeah， so the thing is， if you notify all。

 all of the threads will wake up， but only one will win， only one will obtain， you know， the lock。

That being said， I think there's a there's a subtle race condition if you don't notify all and yeah I guess maybe maybe we can like talk about it after lecture。

 I don't know like if Ryan， if you have like a quick way of like explaining that。

Like why we have to notify all here instead of just notifying one。Yeah。

 so it has to do if you have multiple。If you have multiple threads that are waiting on a semaphore when you go to signal。

 this race condition can't happen if there's only one thread ever waiting on the semaphore。

 but if you can have multiple threads waiting on the semapho。

 there's a really subtle race condition that happens with thread scheduling。

 it's actually on the 110 lab for next week， I think and so if you want to talk about it after class we can spend more time on it。

 but it's not crucial to what we're talking about right here。Yeah， I guess like， you know。

 in general， sometimes I think in certain quarters。

 like when Phil and Chris taught 110 in the fall they're like always notify all because notify one is like weird and buggy and like there are these subtle race conditions and and that's just like what you should do in general。

 but， but yeah， we we could talk about in general yeah。In general。

 you can't go wrong with notify all。 It might be slightly less performant because you might wake up more threads than you than you need to。

 but what are those threads going to do when they wake up The first thing that they do is they reacquire the lock and then they check the condition again to see if it has become true and say that you've incremented this count by one and then you notify all only one thread is going to be able to get that thing that you just put into the semaphore that you've just incremented the sephore with because one of the threads is going to wake up。

 it's going to see that the value is one， it's going to decrement it to zero and then it's going to return from weight If there are other threads that we're also waiting。

 then they're going to wake up they're going to acquire the mutex they're going to look at the value and they'll see that oh hey。

 the value is still zero and so they'll release the lock and go back to sleep So nothing is wrong there it's true that you had some threads that woke up when maybe they didn't need to but functionally everything is going to work。

On the other hand， notify one may be slightly more efficient if you can only have one thread that successfully gets out of weight。

 then maybe it's good to only wake up that one thread to reduce scheduling burden but if you screw up with notify one。

 you can easily create deadlock in a system because say that there are multiple threads that are waiting for some condition and maybe there's only one of those threads that can actually proceed from that condition that's not really the case here with a semaphore but it might be true in other cases。

If you signal the wrong thread。Notifying one doesn't allow you to select which thread wakes up and if you select the wrong thread and it's not able to proceed from the condition。

Then the thread that you did want to wake up is still asleep and then your system may end up deadlocking because it didn't wake up and there's a similar race condition here with semaphore even though you're not really trying to select one thread。

 it could be that you select one thread here is the raise condition。

 you notify a thread to wake up that is currently waiting and then before it actually gets a chance to wake up。

 some other thread calls weight and decrements the semapho to zero successfully。

 it doesn't even have to go to sleep because you just incremented the semaphore。

Then the thread that you signaled to wake up checks the semaphore and it's zero。

 that thread didn't actually get to wake up and you can end up with deadlock it's a really weird race condition。

 it's a lot easier if I actually draw out the threads involved and there states。

 but we can talk about that afterwards if you'd like。Thank you。Yeah。

 are there any other questions about， I guess just like the basics of how a CVv works or maybe is somebody wondering why do we have to acquire the lock before calling wait like that's I think a totally okay thing I to wonder。

Okay， so。Oh。Now we're going talk a little bit about condition variables and rest。

 I'm going to talk about it at a very high level and then we'll actually get very comfortable with it hopefully in a coding example in general it's idiomatic to associate a conditioned variable with a metex by putting it in a pair together so I know we haven't talked about pairs and rust but you want to think of it as like a tuple like if you're familiar with like a tuple and Python it's literally just you can also think of it as like a struct。

with two things inside of it and use dot zero to access the first thing and use dot one to access the second thing。

 you can think of it a pair of syntactic sugar for a struct that just has。

 you know like two things in it and you can access what's on the left and what's on the right。

So oftentimes because， you know， condition and this is another way to think about condition variables。

 you know， like mutes are associated with pieces of data。

 condition variables are associated with metexes， okay。

 and that transitly makes it also associated with that piece of data that the me text is protecting。

Right， so you don't want to have one condition variable that's responsible for multiple mut textes like you don't you don't want to think about like oh。

 I'm like saving so many resources by just using one condition variable for everything。

 that's gonna be so confusing it's gonna make the code really hard to read and it's probably gonna cause deadlock in some like weird subtle way So that's why we just want to associate these two things together by putting them in a pair Does that make sense so far like a high level。

Okay， so continuing forward you have to clone that pair before you move it into a thread and you know if a pair contains two things that are cloneable。

 then we can just clone the entire thing and really so like the pair when I say pair it's like the arc we're cloning the arc is one way to think of it there so we're not cloning the muttex we are cloning a reference to the mutex we talked about this last lecture we talked about how bad it would be if we were to clone mutex is because a muttex is supposed to be a limited resource really we're cloning a handle to a muttex it's like there's one thing pointing to it now there are two things pointing to it and now we have common access to the same resource。

And you pass in the return value of Mutex。lock。 unwrap to CV。 weights or CVv。

weight while so before we just you know in C++ if we go back a slide。

 you would pass in a locked mutex to the condition variable now our Muex is going the results of locking Mutex is going to return a reference to a piece of data。

 but this is a very special reference that indicates that it was returned from a Mutex。

And the reason you need that is that when this reference goes out of scope。

 it needs to unlock the Muex and so you can just pass that reference into CV。t weight， so CV。

t weight can unlock it while it's waiting。I imagine that was probably like a little bit confusing。

 are there any questions about that？About like the difference between that and C++。Exactly， exactly。

 yes， and this reference， this reference is a special reference that gets returned from the Muex。

 you can sort of think of it as a smart pointer， I guess。

 because when that reference goes out of scope， it needs to let go of the lock on the Mutex。Exactly。

嗯。And finally， all right I guess I guess hopefully we'll see today or I don't know if you'll agree with me or not。

 but the Muts and Convaar interfaces and R let you write safer and more legible code like I was surprised by how short the implementation ended up being。

So let's talk about something you know completely or not completely different。

 but you've seen semaphos right and they're really great。

 They can let you mediate access to a limited resource through you know you know passing out a limited number of permission slips and they can also like synchronize you can also use it as like a signaling mechanism to indicate that a piece of data is ready so you saw this in producer and consumer in CS110 lecture where you had a circular buffer and you said I want to read from this buffer。

 but I need to wait until something is ready for me to read in that buffer and we're gonna do an example today that's very similar to this producer consumer model know but semaphores you know they're not that powerful。

 they just let you increment in decrement， that's not super exciting let's do something a little bit more interesting let's make a semi plus plus instead of just semi signal。

 let's do a semi do send So instead of just saying I want you to increment a counter let's say I want to send you a message right I want to。

😊，Something in a queue in your queue of messages to read right and instead of semi dot wait let's do like a sum dot receive and they'll just return something that was in that queue of messages I think this will make more sense if we actually saw it in a picture So let's just look at this real quick I don't know how to like annotate things or can I even annotate let's see does that work。

You have to your iPad。I have these08 on my computer， though， here， I'm just going to escape。My god。

Zoom， no。

![](img/57982b92c6ef1168c6b49c56fbf579b3_15.png)

y。Butai sorry， let's just go back here。

![](img/57982b92c6ef1168c6b49c56fbf579b3_17.png)

Okay， I'm just going to show you in my mouth with my mouse。 Okay。

 so what's going on here is that say you have like a main thread and you have this semi plus plus thing。

And you can clone it so you can share it with all of your child threads right and all of these children threads。

 you can think of them， say they're like workers right and they're going to be trying to perform some computation right And the first thread was successful in doing that。

 So it send some actual result to the main thread So it does dot send comp result and the main thread is able to read that by doing dot receive but thread2 something went wrong。

 maybe there were too many open file descriptors I don't know or sorry no， that was not S to3。

 something went wrong。 there were too many open file descriptors and there's an error。

 So something weird had happened。 Oh no maybe S2 like did everything that was assigned to it So we'll send an I'm done message so the main thread can register that and similarly with thread4 there's another result and thread5 just finished here too So you've got this interface where you can sort of send like these rich messages and the main thread can read them by calling this receive function and were no if there are no messages sent or if the main thread has read。

All of its messages so far， it should block until it receives a new message。

Does this make sense to everybody， are there any questions about this？About this like general setup。

To explain how this is like similar to a semaphore is usually so Arman mentioned that there are two ways that you can use semaphoes and one of them is for communication between two threads and it's for synchronization of communication The analogy I always teach semaphos with it's like a bucket of balls It's a bucket of stuff that you can put stuff in except you can't actually put anything in a semaphore and it's used for communication when you pair it with some form of data storage like a vector or a buffer or something so one thread will put something in the buffer and then they'll signal the semaphore to indicate that something has been put inside of it and then the other thread will wait on the semaphore so that it waits until something has been added to the buffer and then it will read from the buffer so the semapl plus is just combining the data storage and the semaphore into one thing。

Yeah， so I guess can maybe because someone say something about like。

 why might you want something like this or why might this just be better？Yeah， yeah。

 it's less confusing。 it's sort of like it gives you everything kind of in one package right if you use this。

 you don't need to worry about a metex to synchronize access to that queue of messages right you don't need to worry about like manually calling CVt It kind of just waits until it receives something So it sort of like it sort of like obviates the need for other synchronization primitives right we don't need to we don't need to touch shared memory or really implicitly we are using shared memory here still but we don't need to like think about it as much we don't need we don't need to worry about it as much I think one thing last thing I want to mention before we actually implement this is that you know similar to like locks and stuff like that you need to clone before you move it into a thread because we can't just you know move our one and an only thing into a thread we'd have lifetime issues then or like the reason we have to move in the first place is because of those lifetime issues so。

I think that'll make more sense once we see it in context， but before we actually implement this。

 are there any questions？Do they act like a Q。 Yeah， yeah， exactly right。 So if two threads send。

 you know， they'll eventually， like once the main thread receives。

 you can think of send as NQ and receive as Dq。 But like the DQ operation is blocking Like I'm gonna wait until there's something to Dq because if you DQ an empty queue。

 you're gonna get an error and that's gonna be sad right But if you just wait until there's something to receive。

s that's how that works。 It's sort of like when you call wait on a sum before。

 you don't want to wait and you don't want to go into negative numbers。

 Now you need to wait until somebody increments it。 Does that answer your question。For sure yeah。

 I think there's also I guess you said you mentioned condition variable in your question and you're asking like maybe if is there some sort of like queuing that happens in condition variables definitely like yes to that as well right you need to maintain a list of who's waiting for this condition variable so that's that's how that would be implemented。

😊，Exactly，'s it's done by the operating system Opera system manages all of that and also can specify policies for like。

Okay cool for sure， so are there any other questions before we get started in implementing this？Okay。

so。I have the finished example here， but let's start with a mostly fresh example。

 So I'll explain what's here already。 So before we actually implement it。

 let's look at how wed use it right so like let's look at what it would be like to be a client of this interface。

 So we define the sum of plus plus it's going to be generic right So we'll have you know plenty of practice with generics and we'll implement a trait for it right and it's going to contain strings。

😊，And you do S++ in U to initialize a new。

![](img/57982b92c6ef1168c6b49c56fbf579b3_19.png)

Oh wait， sorry， you're still。 Thank you。 Thank you for that。



![](img/57982b92c6ef1168c6b49c56fbf579b3_21.png)

There you go， now you can see it， right？Lovely， great Okay。

 perfect let me see if I can actually close this bottom window Okay great。😊。

So you have this interface where you declare it so you have a particular number of threads。

 you create a clone of it。 This is sort of what you do with a mutex as well right you create a clone of it。

 and then you move everything into the thread the reason you have to move if you don't remember from last week is that you don't know if the thread is gonna outlive this function so you have a lifetime issue if you don't move it in because what if you end up having a reference to something in this function and that reference just like you end up having a dangling reference if that reference is no longer valid and you're still referring to it in your thread then we just do a semi cloneone do send thread you know I just finished So this format bang thing it's just like printlin except it doesn't print to the console it generates a string for you。

Are there any questions about that， Are there any questions about how we use this thing？Alright。

 so let's implemented。 Let's start with Se。Send actually， because that won't require any waiting。

 So what's the first thing I do。 actually， okay， before I even do that。

 let's look at what the sum plus plus thing is you have a Q and Cv。

 So you have this pair I was talking about。 and it's an arc that's holding a pair。 It's a。

 And remember， a pair is just astruct。 where you access the first thing by dot0 and the second thing by dot one。

嗯。And what you do here is you have mutex， it's a muttex of a Vc deek。

 so a deak is a double ended queue。And it's just a Q implementation that we're going to be using。

 it's something that the Ru standard library provides to us， and then we have a con of our。

 a condition variable。And that's that's it there and also we made this generic so we can take in any type T and we can put that type T into our Vec D Are there any questions about that so far。

about the definition and then I think this is something that I didn't mention during the generics lecture。

 but people might be wondering like what's the difference between this T and that T which is a totally fine thing to wonder you can think of this as like over here we're introducing the name T it's like sort of like in like a function declaration like we're introducing the name T here we're actually using it。

😊，Because over here you could also like specify trades， like I could say something like。

 like clone plus， I don't know like format like display dot dot dot。

 but like we're not going to do that。But that's that's the difference between those two Ts Are there any questions about that in particular。

 I know that that was like a common point of confusion that people has that were working on the exercises。

Okay。And then to construct a new sum before， we literally we just say arc U and then we declare a pair using this syntax。

 and we declare a new mutt and then we put in vector or a vector deak inside of it and then we initialize a new condition variable。

So that's how that works so far。So how should we start our implementation of S？

What do you think we should do？So like at a high level， what do we want to do， we want to like。

 you know， you know， in queue。Message。Right。But how do we do that？Okay， great。

 so how do I take the lock？Sure， right， so we actually have。We actually have。A pair right here。

 right so I need to access the lock is the thing in position zero。

So there are different styles for dealing with pairs。

 but just so we don't get bogged down in thinking about that。

 we can just do dot zero for today in the solution code I show something that's like slightly more idiomatic but。

Yeah， but let's just do that for now so we could say like let Q equals。 So what should I say？

Self thoughts， what did we call Q and C， right？Thought what。t0， that's gonna get me my mut textex。

 then what do I do。Thatt lock， yep。那么。unwrap。 Yeah， we have to。 we have to unwrap it。

 It's a very typical rest code， right， We need say lock is gonna return some sort of result。

 and we need to unwrap our results to make sure that everything is okay， Okay， great。

 So that's the cu。😊，And now what do I want to do。Sorry。

 was there a question with someone saying something？Yeah， I mean。

 I suppose if your lock state was like corrupted for some weird reason。

 or if you tried to do happens a double lock right sorry what were you going say， Ryan。

 it happens when what we call the lock gets poisoned。

 so a lock gets poisoned when a thread is holding the lock and the thread panics。

And the reason that that's considered a poison state is because you don't know what that thread did。

 it might have like partially modified some things but not finished modifying everything。

 and so you should assume that the things that the thread touched。

 the things that the lock was protecting are poisoned。

 it could be in an inconsistent state we don't really know because the thread crashed in the middle of changing it。

And so。Rest allows you to not crash your whole entire program in case you actually want to handle that in some way。

 like maybe log an error message。And so that's why it returns you a result in case you still want to keep going。

 but you probably don't want to， you probably want to crash， and that's why we call N。

Does that answer your question， Juliao？Okay。Any any other questions about what we've done here。

 I know this is kind of funky syntax like this dot0 just gets the thing at index0 in our pair there's like other pattern matching syntax but I don't want to like confuse people with that right now you can look at the solution code in the slides if you're interested in what that would look like。

嗯。So we have our queue， great。 What else do we need， So we need， So what do we do when we're sent。

 So now we actually acquired the lock right？ So what do we do now。So we have our queuee。

 what do we want to do with this message？You know like pretend this wasn't multi threaded at all。

 what would we do？You want to incue， you all you want to incute it great。

 so I can say queuee that and or not that push， it's actually called。Ce that push in front。

Is it push Oh， yes， push front。 Thank you。 We don't want to push it， wait。We pop fresh fishback。

I don't think there is a pushback。 What's， okay， let's quickly look at V di rust double ended deck Oh it's deck。

 I've heard people say it's fun because it's called V V deck。 That's so cute。 I love that。 it rhymes。

 So there's a get with capacity。 push， push。 Oh， there is a pushback。 Okay， great。 Okay， perfect。

 Okay， so okay。😊，I think it's I got confused because regular vector， it's just push。

 So that's what great。 Okay， so let's push back。Great， so let's push back the message。Okay。Great。

 now what？Are we done？What's the last thing we need to do？

So now're now we're going to remember that we're in a multi threadreaded world。

 that told us to forget。 Let's remember again， were multi。Exactly， exactly。

 So how do I signal with this condition variable， First of all， how do I get this condition variable。

Exactly， so I can do self。 Q。And CVv dot would be one in this case。And then， and then what do I do？

So like what does signal look like for a condition variable， have the same name that it had in C++。嗯。

Exactly， we want to notify all notify underscorere all。Ex this case。

 is there only one thing waiting on it， which is the like main thread。 Yeah， it's a good point。 Yeah。

 So in this case， the way we've the way we have defined this abstraction will only have one thing waiting on it。

 if it's like a simple， like single consumer thing。

 But let's say maybe we want this to be a little bit more general。

 And maybe there are multiple things that could wait for it， right。

 in the in the diagram I drew though you're totally right。 That was just one thread。Yeah。

 are there any questions about this？So I'm actually going to argue that we don't always want to notify all。

Or not， we don't always want to notify period is actually what I want to argue。嗯。Right。Exactly。

 does that make sense， I think if in the Semapho example， you might have seen something similar。

It's like only if value equals equals one， you notify all。Right， because it'。

 it' is mainly just an efficiency thing， right， So how do I modify the code So I only in queue so that I only notify all once it became newly say。

Full of something or once it came from empty to not empty。All right， well。

 I can definitely wrap this in if statement of some sort。Right， I think。See I think it's called L。

Let me just double check here。文。Oh， soft thought Len， okay， there's yes。Great， okay， yes。

 So you can just call N just like a regular vector。 So if I say if Q。

So kind of like this mirrors the Semapho example really nicely with Q dot L。Eals equals 1。

 and we're going to notify all。Does that make sense to everybody？

Any questions about what I've highlighted here？All right。So let's take a look at receive。

That's exactly right。 Yes。 So yeah， you might be wondering， Oh no。

 we locked something and we didn't unlock。 You never have to explicitly unlock， right。

 This is an example of R A I I the fact that you can。That once this thing goes out of scope。 Oh。

 I highlighted all of it。 Once this thing goes out of scope， right。

 it's going to automatically unlock because this lock dot unwrap is not just going to return to the entire queue。

 It's going return a special reference。 So actually， let's look at Ru's muttex。You text rust。

 let's look at that together if you go， let's see， if you let's look at the return value of lock。Oh。

 it's right here， Okay， great。Turn value of lock is a Mutex guard。 It's a lock result。

 That's why we have to unwrap it。 But it returns a muttex card。 What the heck is a mutex guard。

 right， an RA implementation of a scope lock of a muttex。 when this data structure is dropped。

 The lock will be unlocked。 The data protected by the Mutex can be accessed through this guard by it's D and D mute implementations。

 Okay so that's very advanced。 we haven't talked about D and D mute。

 but I think they're very fascinating topics， these are two traits that lets you。

 this is how smart pointers work really， right， It's like you might be wondering。

 how is it that I have like a box containing something an art containing something and I can just do the dot operator on it。

 right， It's because。😊，These traits let the Dreence， they overload like that star operator。

 they overload the dereence operator and let those references sort of like pass through to the inside data So this Mutex guard is just like another smart pointer except that's why I'm allowed to do things like if we switch back here's why I'm allowed to do things like Q dot pushback so this Q is really a muttex guard but when I do dot pushback this pushback doesn't happen on the Mutex guard it happens on what's on the inside of the Mutex card you can think of the Muex guard as like a box and it's like holding a piece of data and this pushback goes straight through the box into that piece of data。

嗯。But that's， yeah， that's more of like an advanced point about how are these things actually implemented。

 but you know， to your point right like once this is dropped。

 it unlocks the Mutex automatically for you。Are there any questions about that？

I totally expect there to be because we haven't talked about DF or DF mute。

 but if you have more questions about that， I'm happy to talk about that after lecture。啊。

Any other questions？Okay， so in the last four minutes， let's do receive。How's that supposed to work？

So what's common to what we had before， what's the first thing I do when I want to wait on some condition variable？

Exactly， so let's take the lock。 We can literally do the same exact thing that we did before and we'll indent it back。

So we take the lock， that takes the lock， now what do I do？Well， so the dot receive will receive。

 it's just going to do it one by one if you want to get more than one message you got to call it multiple times。

That is how we're defining our abstraction to work。Yeah。

 it may be confusing because we explained this in the context of like one use case。

 which was the main thread receiving a bunch of messages。

 but here we're just really trying to define a general abstraction sort of like a semapho can be used for anything Right。

 so here notice we're calling some dot receive an loop。And we're doing it for the number of threads。

So now I'm going to so I know I haven't really showed you the syntax for CVv dot weight。

 but it looks something like this， so I do self Q I can't spell Q and CVv。1。

And I'm going to do something。 Okay， so I'm going to do this thing called wait while instead of just wait。

 so I don't have to call it in a in a loop。 So it's going to be wait while。

And wait while it takes two arguments。 The first one is the lock。 So it's going to be this Q thing。

 And the second one is a function or closure， right， So I'm going to define this in this closure。

 what it's going to do is it takes in this thing， right， It takes in this Q。

And what I can say is something like this。 right？ I can say， I want。

 So what is the condition I should put here， Can somebody tell me what， what what。

 I want to wait while what。Exactly， and another way to say that is while the Q is empty， right。

 So while Q dot is empty。Exactly， so then that's gonna。

 that's gonna to let me wait while that's true。 Now， what do I want to do after I've waited。Exactly。

 and the way we do that was that you do this thing called pop front P front actually returns an option。

 but I know that this is not going to be none because I waited until it was not empty so I'm just going go ahead and unwrap that。

Final thing here is we need to implement clone， but you'll notice that there's only one thing in this struct and it's an arc and Arc implements clone for everything so I can actually just get rid of this like we don't need to do it manually what should I do instead？

People remember what this is called。Derriiveve， exactly， derive， just like calculus， you know。

 we derive。We we do derive clone right here。 That's all we want right and that will and that derive knows that it can clone because it the only field in this is cloneable。

 It's an arc right So that looks good so far in the last minute， let's see if this compiles。

Cannot borrow Q as mutable。 Okay， a classic rust error。 Let mute Q。 let mute Q。 Great， okay， great。

 And let's see what this does。 I say parentheses around if okay。

 so borrow of moved value Q move occurs because it has this type。 Okay， so it's moved inside there。

 Okay， so how do we get around this。😊，She。So this is kind of a weird issue right here， right？Okay。

 yeah。Let's try that。What if we just gave it a reference to the cute？Oh。

 mismatched types expected a struck Muex card， Oh no。Wait one second。O。嗯。Right， okay， okay。

 So this is， this is actually what's going on。 The C dot weight will return this lock handle to us。

 So really， what I want to do is a very subtle thing。 But what I want to do is something like this。

So I want to lock it here。Right， okay， sorry， that's an egregious line of code， a lot going on there。

😊，So I want to lock it there。And then let's see yeah。

 what's the proper way to indent something like this And then I want to say let let letq equals the result of wait while because wait while I forgot to mention this weight while has the same return type as Mutex so I can say let mute Q equals self doq and cv。

1 do wait while and because what happens is after the weight while finishes。

 it still needs to reacquire that lock and if we recall right requiringquiring a lock return something right so it's going to return this particular thing to us to us right here。

Because cute。 well， so the capture。 So this Q， this is different。

 This is scoped to whatever the return value is。 So yeah， so what this returns。

 that's passed into the capture clause。 Another thing is this， this， just like dot lock。

 this returns results。 we need to unwrap it as well。 So let's just see what that does。And up。Come on。

Great， it worked。So that's and just to show you， you know， it can do different things every time。

 you know， oh wow， thread5 finished first right you can just run this over and over and era the threads。

 It's really fun。 But yeah， okay， so this was definitely I kind of rush through that at the end。

 so I'm happy to stick around and answer questions about what's going on here。

 especially in receive I feel like we didn't have that much time to talk about what was going on there Are there any questions about this or I guess what questions do people have about this。

😊，Also， if you need to go， feel free to go， stay coming and we'll see you on Thursday， yeah。

And I imagine this wait while thing is not the most intuitive thing。Okay。

 so let's go back to what was going wrong。 So actually， let's talk about what's happening now first。

 and we'll go back to what we had before before。Before we could have actually made it work。

 it's just。We ended up losing our reference to the lock right so what this does is this moves the lock into the wait while。

Right， but that's okay because the weight wall is gonna return it back to us。 So let's。

 let's see if I can go back to what we had before。 We had this before。 right， wait， wait there。 Okay。

 right， so we had this before。 Let's run that。And it got， it got angry。 Oh wait， no， because we did。

 this is one of the classic rest ways to fix compiler is just add random amber， right。

 borrow of moved value Q， okay。😊，That's definitely not good。

But I argue one way we can so the issue here is that look at this， right。

 this moves Q into weight while， and then we try to use Q again。That's not okay。

But if I said Q equals， let's see what happens。Oh， mismatched types。

Found enum result up because I did not unwra。 Okay， unwra。 It's a。

 it returns a result just like thought lock。 Okay， let's see what happens now。And that works。

 So actually there's a very small edit distance from what we had to do。

 the does it make sense why the unrap had to be there。

I think Ryan explained this before with like the lock poisoning， right。

 like why does something like dot lock need to return and unwrap？

But but I think the main point of confusion was why couldn't we just do this， right， so if I just。

I commented this out， it's going to become angry with me again， for sure。Borrow of moved value。

So if we look at the weight while implementation， CV rest。Oh， that's not what I want。

 Bs condition variable is what I want。嗯。If we look at weight， wait while is here， oh at the bottom。

What does it take， It takes in a muttex card。 Notice how it takes in a whole mutex card。

 not an Ampersand muttex card， not Ampersand mute Mutex card， but an actual bona fide mutex card。

 It wants to consume the mutex card。Does that make sense？Exactly right。 So it takes in this guard。

 but it gives it back to you。 But the reason it needs to take it in is because it needs to like while it's waiting。

 it needs to like release it， it needs ownership of it actually right。

 But then after it's done waiting， it'll give it right back to you。

 This is actually a pretty common pattern you'll see because sometimes we don't want to make we don't want like multiple muttex card like running around for the same reason that we don't want to clone them right But it's okay to just say like wait while it's like I'm gonna hold on to it for a little bit。

 Okay， and then I'll give it right back to you in the return value because if you look at the return value。

 it's the same exact guard that was passed into it。😊，Does that make sense？

Maybe it's better if we look at the code again， right， so the code。

 it was just consuming this queue and we tried to use it。And that's why I was angry。

 but if I comment it back in， if I just say Q is equal to what it returns，s then it's happy again。So。

 to to。Gave like a bird's eye summary of what's going on。

CV do weight takes a locked lock that's true and rest that's true in C++ you have to lock the lock first and you pass it to CV dot weight it's nice here because the type system ensures that you actually have locked the lock whereas in C++ a lot of times we see students who will pass a Muex to CV dot weight but they didn't lock the mut text first and it actually ends up creating race conditions or worse deadlock in some cases so。

You have to pass it a locked lock， which is why we do this lock on the first line and then we pass it in as a parameter to the second line。

 but you have to pass ownership because if you don't pass ownership then there are two references at the same time to the underlying data and it's possible that you might end up modifying the data using one reference at the same time that it's being read using the other reference。

 so that's why it needs to take ownership of that lock guard of that Muex guard so that it can evaluate the condition。

Reading that variable and so that it can also unlock the lock when it goes to sleep。

When it comes out of sleep， it has to lock the lock again。 And remember。

 I mentioned this thing about lock poisoning。 if， if a thread panicked while holding the lock。

Then when you try to acquire the lock， you'll get a result error out saying that a thread crashed while holding this mutex and you can't trust that anything inside of the Muex is consistent because it may have corrupted the data inside and so that's why you need that unwrap。

 so that when it reacquires the lock and if it's poisoned。

 then it will return you an error saying hey， this data is poisoned。

 we probably shouldn't continue but if you really want to we can。嗯。

We have to take ownership back because otherwise we won't be able to use the data inside the lock again。

 but we would have to read。To reacquire it， which you also could do。

 but a lot of times that creates another race condition so this is the way that you typically will receive ownership back。

And then we can use the queue normally。I mean， I guess we can't even reacquire it if we want because it's it's already acquired by the you can because it will be dropped it goes out of scope at that after that function。

 So if you're not receiving the return value of that function。Then the value it returns。

 which is the lock gets dropped。I see what you're saying。I see。

 so you're saying something like if you just got rid of this， but then you just tried to lock it。

Right， okay， but if you did that， it would it would create this race condition where here you have waited to make sure that the queue is empty。

 And then if you're not still holding the lock， like if you momentarily drop the lock and then reacquire it。

 some other thread could get in there and steal the the thing that you saw inside of the queue so that when you do queue do pop front。

 actually， now the queue is empty because some of the thread got in there and stole what was inside。

 And so when you unwrap you risk crashing。 Yeah， I think this is similar to the race condition that you were talking about with trip。

 right。Yeah， yeah， where like we waited for the sepho to become one。

 but then if you release the lock and reacquire it， the thing might not be there anymore。

 it's a little different because in that case it was an issue with condition variable usage。

 not with mut usage， right。This is about me text usage。

Are there any other questions about just like this example as a whole。

 Let me see if I can minimize this。A close's been covered。So if we just look at it all， I mean。

 I think it's kind of remarkable how brief it is， right？Very brief， but also complex。

 but also complex。 Yeah， that's kind of like the trade off with rest。 like， you know。

 so a couple of lines of code where you're like heck is going on。 Well。

 I think that's true of C plus plus2。 I think it's the fact that it's multithreaded And the difference here is that rest prevents you from making a lot of the same mistakes that C plus plus and C let you make through its type system like because it requires you to get to the data through the lock。

 like there's no other way to get the data other than by having the lock。

It avoids most lock issues And then similarly， because the CV requires you to pass a lock guard。

 a Muex guard instead of instead of a mutex that also ensures that the Muex is already locked。

 which is a common mistake we see people make。 and I think it also prevents you another mistakes on people make is they they don't fully understand what CVs are and why CVs require you to pass a lock。

 And so they get the condition part。 like they'll pass the condition correctly。

 and then they're like， oh， well， weight takes a mutex as the first argument So I'm just going to declare a mutex and pass and it's like what。

 no， that has nothing to do with like you need to pass the muttex that is guarding the data inside of your condition。

 If your condition checks the variable， you need to pass the mutex that guards that variable。

 But because C and C+ plus make no association between locks and data。

It's it's easy to make that mistake where you just pass a random lock or worse。

 you think you're passing the right lock， but actually it isn't the right one and rusts。

Removes all of those issues by enforcing an association between a lock and the data that it protects。

Are there any other questions about that or about like this example in general？Or about like Cvs。是。

Yeah， I I like that's like one good way to put it， right。

 And it's oftentimes like that the pieces of code， like you can sort of think of it as like these like little critical regions like where you have the lock and unlock oftentimes they have to do with accessing data accessing data or modifying this and you saw this in assignment 3 with with blocking signals。

 you would block signals around， know this check， know like numb workers is available or when youre like pulling things off the queue。

 So really like that act of locking even though like the code was a proxy for like。😊。

Protecting like pieces of data， which is and I think it's like a bad proxy for it because it's really hard to reason about because there's sometimes like really subtle ways like maybe there's a decomposed function that touches that piece of data but you didn't know that because it was decomposed and maybe they didn't like properly lock around right or he's like。

 Ryan， do you have anything to say to that。Yeah， I'd say that under the hood it's really the same。

 so I don't know if you've seen have you seen lock guards in Monten yet。

So this is mechanically the same as a lockguard， but it doesn't protect a piece of data。

 a lockguard doesn't the piece of data right， but the way that like。

If you think about this in terms of an imperative program that like does one thing and then another thing and then another thing and another thing。

 it's the same。 You lock a lock。 and eventually you unlock the lock in C plus plus。

 if you're using lock guards， the lock gets locked when you create the lock guard。

It's it's released in the lockguards deor that is basically the same thing as what's happening here when you do something dot lock dot unrap that is returning you a muttex card it's really a lock art and then in that object destructor in the drop trait。

When it goes out of scope， the the lock gets unlocked。 the difference is that。

The data is declared inside of the Mutex in rust， whereas in C+ plus andnc C。

 a muttex is a standalone object that just has like some state locked or unlocked and it doesn't actually contain the values that you're trying to protect and then somewhere else you declare the values that you're trying to protect and it's up to you as a programmer to make sure that if you have some values that are accessed concurrently you make sure that you don't access them concurrently by by using a mut textex so that you get mutual exclusion and so that that those。

Would be concurrent axises， would be dangerous concurrent excesses are serialized。

But that means that you have to documents in comments。 You have to say before touching this variable。

 make sure that you're holding this lock， because otherwise。

Some of your code will acquire the lock before accessing the variable and release it afterwards。

 and that is safe， but if you have some other code somewhere else that doesn't respect the lock and goes straight to the data。

Doesn't matter about all of the work that you did on the Sa code that those couple of unsafe accesses will destroy everything and。

And create race conditions that could potentially crash your system。

So you have to make sure that everywhere you touch that data you acquire the lock and release the lock properly。

 which is pretty difficult to do and especially for large code bases where you're bringing on new developers regularly you have to make sure that these new developers respect your practices of acquiring the lock before touching the data and whatnot and if you have comments saying hey。

 acquire this lock before touching this data， you have to make sure your comments are up to date。

 which is often not the case and I got bit by this a month ago into the Linux code base because it' said acquire this lock for these fields and so I'm like okay I'll acquire those lock for those fields and then I touched some other field which wasn't in that list and it turns out you actually needed the lock for that field too and so this rest approach of saying you can't get to the data unless you acquire the lock like you can't mess up here you have to hold the lock in order to have access to the data。

That approach is nice because it makes it so that you can't have these accidental mistakes。

 you can't have new developers。That don't realize that they need to hold a lock you can't have stale comments it's in the code itself like there's no way to touch that data without holding the lock that I think is the difference Meics are the same but it's the compiler's type system and this like monitor design that Arman was talking about that forces you to make sure that you're using the lock correctly。



![](img/57982b92c6ef1168c6b49c56fbf579b3_23.png)