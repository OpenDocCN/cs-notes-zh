# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P62：6_模块3 3 1 第3版.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/ba33b04b0f9018463c0e4dac07ec6228_0.png)

Module 3， threads and go topic 3。1 communication。So so far。

 we've been talking about creating go routines a little bit of synchronization。

 so waiting on go routines to exit。 but go routines also communicate sometimes。

 So generally go routines work together to perform a bigger task。

 So these go routines are not completely independent typically So typically you're making a bigger program that has sort of semi- independentdependent pieces。

 Each go routine does one of these independent these semi- independentent pieces。

 but they are not completely independent。 if they are completely independent。

 they'd be entirely different programs right you wouldn't even call them the same program right you just have a different program。

 but they' are usually doing a smaller piece of a bigger task。 I mean。

 just as an example of something where you might use go routines， So you're making a web server。😊。

Web server， it's very common to make them multithreaded because because what happens is this web server it might be handling you don't even know how many people are going connect to the web server at a time right So for each person that connects a web server。

 there's an interaction。 you know each person， meaning each browser that connects。

 you got to communicate with it。 you know， receive its message respond to this message and so on。

 There's a basic a conversation that the server has with each different each different browser that connects to it。

So it's nice to make it multithreaded because what can happen is maybe there's 1 thousand people。

1 thousand different browsers connected to this web server at the same time。

 looking at different pages， different pieces of the page So it's nice since they're all doing the same basic type of interaction right they're all talking HTTP HTP message back and forth。

It makes sense to have a multithreaded program。 every time a new connections made。

 a new browser connects。 you create a new thread for that to handle that connection to handle the communication back and forth between that browser and then a new browser connects and you make another thread to handle that So it's nice a convenient way to keep the state separate because the state of the communication with one browser can be completely separate or largely separate than a state of communication with another browser So you want to be able to separate them。

 It's a different threads remember that they are not completely independent So remember that like with this web browser idea all these thousand connections that are made these thousand different threads that are running。

 They're all serving the same set of pages I mean say this is UC's web server So all UC's web pages that are serving。

 So they're sharing data basically the UC webp page data。

 they're sharing that and say one browser might post some data to a web page and then another browser should be able to view that so there's interactions between these threads since they're all sharing。

😊，Webpage data。So this is sort of a typical scenario where these go routines。

 they're not completely independent， they work together periodically to perform some bigger tasks。

 they have to trade information， so they need to send data and receive data in order to collaborate。

So I'll give you just a sort of a toy example。 So rather than the big web server example。

 I'm gonna work with something small just to sort of get the point across。

 So say you got you want got this problem。 you want to find the product of four integers。

 and you decide I want to do this with two go routines。 I'm gonna have two go routines。

 multiply two of the integers。 sorry， one go routine， multiply two integers。

 The other go routine multiply the other two integers。

 Then both of those two go routines will send their results back to the main go routine and the main main go routine will multiply their results and the final result will be the product of all four integers。

 So in this case， I've really got three go routines。 The main go routine。

 plus I'm going make two more go routines that are going do subpro multiply multiply the other two and the main go routine combines them。

😊，So in order to do this， you're going to need to send data specifically integers from the main routine to the two subrouts right so these two new go routines that you created。

 you got to give them the two numbers that you want them to multiply right so data has to go from the main routine main go routine to the subrouts subgo routines。

😡，And then the results of these go routines of these subgo routines have to come back to the B routine。

 right， Because mainine has to get those pieces of data and multiply them together to get the final result。

 So you can see the data transfer that's going on between these go routines。

 And this pretty straightforward， this data communication that we're talking about is sort of the most straightforward kind where the data communication is going on at the beginning of the executing execution of go routine and at the end。

 meaning。😊，With these subroutines， these sub go routines。

 they get data right the start the initial data， the integers they want to multiply。

 and then they send results back at the end。 So this is sort of the simplest type of communication。

 But note that the communication doesn't just have to happen at the start in the end of a go routine。

 They can happen right in the middle。 know so in the middle of one of these go routines。

 It might decide to sense of data back to the main routine。 in a more complicated example。 Right now。

 we're just dealing with the sort of simple version right at the beginning。

 you're sending the sub go routines data and the end you get some back。

 You need communication to be able to do something like what I'm saying here。

So communication between go routines is done using channels channels are used to transfer data between go routines。

And channels are typed， so you declare when you create a channel， you create it with a certain type。

 so maybe this channel handles integers， this one handles strings。

 this one channels a structure of a certain type and so on。

 So they' are typed and they transfer type data。

![](img/ba33b04b0f9018463c0e4dac07ec6228_2.png)

So you use make to create a channel， so an example here I'm making a channel called C。

I say C equals make Cha int， so that just creates a channel of type int。

 which transfers into your information。Now， once you've got this channel C。

 you can send and receive data using this arrow operator。

 So when I say arrow it's literally a less than and a dash。

 which looks sort of like an arrow and so you use this arrow operator to send data on the channel and to receive data from the channel。

 So on both ends， you send and receive using this operator。 So an example here。

Send data on a channel See I' got my channel C I just made， I want to send the energy of3。

 so I write C， arrow3，arrow， and so the three is if you follow the arrow direction goes into the C。

 So this thing on the right is going into the channel C。

So that's how you would send data on a channel and you can receive data from a channel。

 you can see that here。So in this case， the arrow is actually leaving the channel right So x equals colon equal in this case。

 x equals arrow C。 So the data comes out of the channel C， the arrow sends it into the X。

 So that's how you read it。 So you can send data on a channel and receive data from a channel using this same arrow operator。

 So here is a little example of that code that I just explained。😊。

Where I want to do this multiplication of four numbers。And to do it。

 I'm going to make these two go routines， each go routine is going to just multiply a pair of numbers。

And I'm going to start those two， so the main routine will start those two have the multiply pairs。

 then the main routine will take their results and multiply those together and print it。

So let's see let's start with the function prod right for product and basically that just takes two integers。

 V1 V2 and it computes a product。 Now the third thing that it takes is the channel that we want to communicate on right so it takes that as an argument and then what it does is it takes V it computes V1 times V2 computes the product and then sends it onto the channel。

So now we look at the main。The main we create the channel。 see。

 we then it it starts to two go routine。 So go prod。

 go prod passing the different hard coded numbers in there。 That doesn't matter。

 but hard coded one and2 to the first go routine and a three and4 to the second。

 noticeice that they're both getting the same channel in this case。

 They're both gonna communicate on the same channel。So it starts to go routines then。

The next two instructions just receive the results from those two go routines on the channel。

 So A equals arrow C and B equals arrow C。 So A gets whatever comes on the channel。

 the first thing that comes on the channel and B gets the second thing that comes on the channel。

And then I just print then the main go team just prints the product eight times B。

So this is an example， a of simple example of how you use channels to communicate now one thing before I go on is I said that channels are used to communicate to send data back and forth between go routines。

😊，And that's true。 And we're using it here。 but there's another way to send data between go routines。

 certainly when you create the go routine， when you create the go routine。

 So here where I call I say goprod onea2 come C goProd3 come4 come C I am sending those two go routines。

 the data which are the arguments to the function So like goprod one come2 come C。

 I'm sending that go routine through those arguments， the one and the two and the C。

 the channel So that's another way that you send data to a go routine and that's just works when you start it when you pass arguments to its function。

 those arguments are passed to the go routine so I'm sending data say with the goprod 1 comm 2 come C I'm sending one and two and C to the new go routine I'm creating and I'm not using a channel so that's another way to send data and that's sort of common。

 but that's just initial anytime after the the starting of the go routine。

 if you want to send data back and forth， you have to use a channel like we do here。

But we receive the results on this channel。Thank you。



![](img/ba33b04b0f9018463c0e4dac07ec6228_4.png)

Module 3， threads and go， topic 3。2 blocking on channels。So by default。

 a channel is called unbuffffered when you create a channel。

 it's unbuffffered and unbuffffered channels cannot hold data in transit。

 so the default is unbuffffered。 So when you like when we when we call make and we say you know make and pass it。

 say chain int and we don't pass in any other arguments。

 then we're making a channel that holds integers， but it's unbuffffered。

 so it can't hold data in transit。So the implications of that are that。

You knowSince we don't want to lose data， ascending the transmission， ascending has to block。

 the sending instruction has to block until the data is received on the receiving end。

And the receiving the receive instruction has to block until the data is sent Okay so here's what I mean by this say I got two tests test one test two。

Test one is going to send three onto this channel。And test two is going to read whatever comes on the channel and put it into variable X。

 and you can see that there。So since a task one hits its send first， it reaches send。

 it tries to send three on the channel。😡，It will block。

 It will sit there until task2 reaches its receive instruction。 So one hour later。

 or however long later， you know， task task one will sit there for an hour or however long it takes until task2 reaches that that read instruction。

 the receiving instruction。 And then once it does。😡。

Then then the data can be transmitted from test1 to test 2， and task one can then continue。

 But task1 doesn't want data to be lost in transit because remember this this channel。

 it can't hold any data， right， So if task 1 were to continue and test2 weren't there to receive the data。

 then the data would go away， And that can't happen。 So task1。

 if it reaches it send sending instruction first， it has to block and wait for test2 to receive。

 and I didn't show this example here， but same thing happens if if test2 hits its receive first。

 if the ordering with switch。 So let's say test 2 hit to receive first。

 There's nothing to receive right， it just blocks， test2 will block there until an hour later say。

Test 2 finally sends three under the channel。 when that happens， then test2 can continue。

 but either way， sending these two instructions send and receive。

 they are blocking instructions So if it's an unbffered channel。

 the send will block until the receipt happens until the receive instruction happens in the other thread and the receive will happen until the send instruction。

 the re will block until the send instruction happens So either way。

 and it has to do this because there's no buffering or by default。 we'll talk about that in a second。

 but by default， there's no buffering。 So you know you have to wait so that you don't lose the data。

So note that when you use a channel in this way， the channel is allowing you to communicate allowing to send data between two different threads。

 two different go routines， but it's also doing synchronization because task one has to wait for task2 to receive or test2 has to wait for task one to send so it is also doing synchronization just like the weight remember we talked about weight groups I said。

 oh， I want my main routine to wait for this go routine to complete first and I made this weight group and so this is doing a similar thing。

 It's another way to do the same thing because task2。

 it has to wait for task one to get to reach a send instruction before task twos receive can continue so thiss also waiting going on here So the communication with channels is also synchronous and synchronization is built in。

😊。

![](img/ba33b04b0f9018463c0e4dac07ec6228_6.png)

So。What that also means is that you can you can use this channel communication for just the synchronization and throw away the results。

 the received result。 So here's the example I got it here。

 T1 test 2 test1 sends the number three onto the channel test2 notice it what it's got it's got the arrow and then the C。

 which means to receive something from channel C， but it's not assigning it to any variables。

 It's not saying x equals arrow C。 just says arrow C。 So in this case。

 test2 is receiving something off the channel。 but it's not using the data。

 It's basically throwing away the data that it receives。 So in a situation like this。

 since you're wasting the data， all you're really doing is synchronizing the two tasks。

 So task2 has to wait for task1 to do the send。 So this is like a weight like a weight with the weight group。

 This is like another way to implement a weight because test2。

 even though it's throwing away the data that it receives it still has to wait for task1 to do the send so。

😊，You're waiting for an event just like you would do with a weight group。

 So it' it's something about the channel communication that is also synchronization built into the communication constructs。

Thank you。Module 3， threads and Go， topic 3。3 buffer channels。

So the channels that we talked about so far are the default channels and they have no capacity to hold data in transit。

 but channels can have some capacity so channels can contain a limited number of objects in transit if you want now the default size。

 default capacity for a channel is zero so it's unbffered。

 but you can make what are called buffered channels which actually have some capacity to hold data in transit so the capacity of a channel is the number of objects it can hold in transit。

And the way you define this is an optional argument to the make function when when you create the channel。

 you you can set its capacity。 So in this example， I say C equals make chainant comma 3。

 I give it that second argument 3， which tells me that the buffer is size 3， Now note that。😊。

Default size is0。 so default when you don't give that second argument is as if you made the second argument equal to0 to say。

 look， I can't hold anything in transit， but in this case I'm saying， okay，3， I got a buffer size 3。

Now， when you have a channel with a certain amount of capacity， the blocking。

 the send receives block under different conditions。Not really different， but this seems different。

 so what I mean is sending only blocks if the buffer is full。

So what that means is say I make a channel size of capacity three。

I can do three centss without blocking， so I can do three centss with no receipts so there's say go routine one is sending the go routine two。

Let's say go routine 2 has not done any receives。 It no， it doesn't do a receive for a long time。

 Go routine1 can do three sends and still not block instead because what happens is when it does its first send。

 even though the receiver is not there to receive it。

 the buffer since it has capacity 3 can hold it temporarily and allow the go routine1 to continue its execution and this can happen up to three times up to the capacity of the buffer now eventually once I get to that fourth send。

 if that receiver hasn't done receive， then if I were to I couldn't write the fourth thing into the buffer it only has capacity3。

 So at that point a blocks so once so sending only blocks if the buffer is full。

 but you have some write some sending that you can do without actually having to block on the side of the writing go routine。

Which is good right because blocking is generally a bad thing for the most part is a bad thing because blocking reduces your concurrency right if you block。

 that means you can't execute， which means you might be wasting processor resources so you don't generally want to block。

 you would like to be able to do asend and then whether or not the receiver is there。

 you just continue on your merry way and keep executing So having a channel capacity allows that to happen to some extent now it's limited because memory finite。

 the buffer can only have a finite size， but you can continue for more time without blocking and so it might can help you sometimes。

Also receiving same thing happens on the receiving。Receiving only blocks if the buffer is empty。

 so if the buffer is full， it has three objects in it。

 you can do three receives without any sense because you can receive those three things that are in the buffer now on the fourth receive。

 once the buffer is actually empty， then that receive will have to block okay。

So so this is what it means to give a channel a capacity， you make it a buffer channel。

 you can give it a size and the size means that the channel is basically storing data in transit so the sender and receiver don't have to block as often because they can use the buffer as a holding space。

So to give a little example。I got my channel with capacity once， I got two， two tasks， two threads。

 T1， T2 or to go routines。In between， there is a channel and it's just one， it's capacity one。

 so it's one space， right？And you look at T1， it's doing the sending， T2 is doing the receiving。

T1 is writing an integer in there C into the channel。

 and then T2 is going to read two things out of the channel。Now， now。

 first note that those since you're that can't happen， right。

 you can't send one thing and receive two。 So what happens is。

 So what happens exactly depends on which executes first what what， you know。

 which send or receive executes first。 But the first receive。Has to block until the send occurs。

 So if T2 is executing faster it runs it hits its first receive before T1 has issued the send。

 then T2 is going to block because the buffer is empty okay。But once the buffer gets filled。

 so once T1 executes and fills that buffer， then the first receive can continue。

Now the second receive in this scenario blocks forever Now I'm assuming that T1。

 it doesn't do any more rights Okay so this would be an error if T1 just writes one thing into the buffer and T2 tries to read two things。

 the second one has to block right so this would be an error right here in fact。

 it would probably throw an error as soon soon as you run it。But so in this case， this is a problem。

 T1 is just going to block forever because it's always it's waiting on T2 will block is waiting on T1。

Now we can see a similar thing happening in the other direction。

 this time T1 is actually writing two things，3 and 4 is writing into the channel。

 T2 is going to receive。The the second send is going block until the receive is done。

 So the first send， it， it'll block， it'll the first send won't block。

 It'll just put something into the buffer。 And eventually。

 the receive will receive that out of the buffer。 The second send。so the receiver has happened。

 then the buffer is empty， so the second send can write something into the buffer and then continue。

But if the receive has not happened， then the second send is going to block because the first send has filled up the buffer and this buffer is only size one。

 so the second send will have to block until the receive happens。So why use buffering。

 the main reason to use buffering？Is so the sender and the receiver don't need to operate at exactly the same speed。

😡。

![](img/ba33b04b0f9018463c0e4dac07ec6228_8.png)

So。What I mean by that is that if you don't have a buffer， if you use an unbuffffered channel。

 then the sender and the receiver have to be in lock step， meaning the sender。

 the send has to block until the receive happens， the receive blocks until the send happens。

 so they have to be in lockstep， which reduces the amount of concurrency that you can have。

Buffering will allow you to do like in this case， say you got an empty buffer。 the producer。 Okay。

 so I'm defining this， this is like a sort of a classic problem producer consumer。

 It's a concurrent concurrent example where you got two different threads。

 There's one that you refer to as a producer， one you refer to as a consumer now。😊。

The producer is basically generating data。 We don't know how it's generating data。

 It could be generating。 Maybe it's reading data from sensors。

 reading temperatures from sensors and sending them to the consumer to be processed。

 something like that。 but it's generating data on a regular basis。

 like maybe actually a common thing is maybe it's doing maybe your T1 is connected to a microphone。

 and your sampling the sound。 So periodically， you have to record a sample story sample。

 And so the producer maybe is just talking to the microphone， grabbing sample periodically。

 And then it sends them to the consumer and the consumer is doing some kind of audio processing task。

 It takes a samples and Who knows。 It does a fast forward you transform something like this。

 So but the general idea is you got a producer that is producing data from some source over and over and over again over a long period of time。

 And the consumer is consuming data over and over again over long period of time and doing something with it。

Now， a buffer is useful in this situation because let's say sometimes the producer is a little fast to produce its data。

 right so it maybe the consumer is consuming a certain rate。

 but the producer is a little faster at producing。In that situation， the producer。

 if you had no buffer， the producer would have to block。

 if it tries to produce something before the consumer is ready to receive it。

 then the producer blocks， until the consumer reaches its receive and then they can continue。

 So the producer has to get slowed down to match the speed of the consumer and vice versa。

 if you're consuming too fast。 faster than the producer， then the consumer has to get blocked。

 It receive has to get blocked to slow down to the rate of the producer So the rate。

 if these producer and consumer one's a little faster than the other。

 the rate is forced to be slowed down when you don't have any buffer。😊，Now， if you have a buffer。

 then a speed mismatch or at least a temporary speed mismatch between the producer and a consumer is acceptable。

 because what happened is if the producer is a little bit too fast。

 then it'll just fill up the buffer。 if the consumer is a little bit too fast。

 it'll just draw data from the buffer。 Now this， since the buffer is finite size。

 This can't happen forever。 if the producer is forever too fast。

 then it will fill up the buffer and then it'll still have to block。

 But when you have a scenario where the producer and the consumer。

 they on average there're at the same speed。 but sometimes they speed up and slow down。

 and this certainly happens in a lot of scenarios where they not exactly lockstep。

 sometimes produces a little fast if sometimes a little slower and so on。

 then a buffer is really helpful， because then this buffer。

 as long as you don't fill up the buffer can allow you to continue executing without blocking。

 continue sending and receiving without having a block because you' got this this buffer in between。

 But still， on average， the speeds have to match or else the buffer will overflow or become empty。😊。

Thank you。