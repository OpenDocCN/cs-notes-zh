# P23：Lecture 23： Distributed Decision Making (Con't), Networking and TCP I - RubatoTheEmber - BV1L541117gr

 Okay， let's get started。

![](img/09ec77e1f3ad3b5a81728edbc013fe12_1.png)

 We have a lot of material for today。 Okay， so we're going to talk about distributed systems。

 Then we're going to look at distributed decision making and， have distributed commit protocols。

 We'll look at networking and then time permitting。 We'll get into PCPIP。 Okay， so if we。

 if you recall， we have societal scale information systems。



![](img/09ec77e1f3ad3b5a81728edbc013fe12_3.png)

 So these span the space from these massive clusters of tens of thousands of machines。

 all the way down to MEMS devices like airbag accelerometers。

 We're surrounded continuously by dozens to hundreds of microprocessors。

 So if we were to just guess in this room how many microprocessors there are。

 would probably be off by a factor of three or four。 Right， each person has three or four devices。

 A phone， a tablet， a laptop， a watch， all with microprocessors。

 But the room itself is filled with microprocessors。

 So everything from each of the wireless access points around the room， the lighting controller。

 the AV controller， the wireless mic， the projector， the thing that raises and lowers the screen。

 All of these have microprocessors and they're all interconnected and， running various applications。

 So that's kind of what we're going to dive into today is these distributed systems。

 These distributed applications。 Now it wasn't always like this。



![](img/09ec77e1f3ad3b5a81728edbc013fe12_5.png)

 If we look at sort of the dawn of time， it was large mainframes。

 Might spend $5 million on a mainframe。 And then you'd have dumb terminals connected to it。

 They were called dumb because they literally had no intelligence at all。

 All they could do is receive commands to display things on a screen。

 And when you type the keystroke， that keystroke got sent all the way to the mainframe。

 it was processed in the application。 And then the application basically drew the screen。

 The closest analogy today would be is if you use protocols like remote desktop or， remote display。

 where all you're really using your computer as is a frame buffer。

 And a way of inputting keystrokes and mouse inputs。

 So that kind of model in the 80s when we had personal computers became a client server model。

 And now we have some of the compute done on desktops。

 And those desktops are clients making requests of that mainframe or that server。 So single computer。

 Today， what we have is more of a peer to peer model， where we have distributed systems。

 So that functionality that used to live on that one single giant $5 million mainframe。

 now lives on servers。 Originally those servers were all in the same room， then in the same building。

 Now they can be globally distributed。 So this is again called a peer to peer or widespread kind of collaboration model。

 Okay， so why do we want distributed systems？ Well， that mainframe that costs $5 million。

 let's say it could support 10，000 of those dumb， terminals。 What happens when I buy my 10。

000 in first terminal？ I have to go out and buy another $5 million mainframe to support one additional user。

 All right， and so the sort of unit of growth is very large and doesn't really scale very well。

 The idea with distributed computers is that these smaller computers， these smaller servers。

 or units are much cheaper to produce， maybe a few thousand dollars instead of a few million。

 dollars。 And so I can scale my compute incrementally as I scale my user。 Or if it's a web server。

 as my demand increases， I scale incrementally。 And so there's great economic reasons for distributed computing。

 When we look at client server， users have control over some of the components， right？

 The client could be your phone running an application that's talking to a server somewhere， else。

 But you control your phone。 You can choose not to run that application or to run a computing application。

 And then there's collaboration， right？ Simple as an example， Google Docs， right？

 We can all work on a shared network file system on a document together。

 So the promise of distributed systems is they give us higher availability。 One machine goes down。

 I just simply use another one。 They give us better durability。

 I store my data in many different locations。 They give us more security。 Right？

 Each piece becomes much easier to make secure。 However， the reality has been really disappointing。

 So this is Leslie Lamport。 He's a Turing Award winner and he has made some very fundamental contributions in terms。

 of distributed systems， the notion of distributed time and distributed clocks。

 And we'll come back and see some of his work later on in this lecture。

 But the reality has really been disappointing， right？ So we get worse availability。

 We depend on every machine being up。 So he's famous for this quote in addition to all the other stuff he's famous for。

 where， he said， "A distributed system is one in which the failure of a computer you didn't。

 even know existed can render your own computer unusable。"， And I had this all day today on campus。

 I was kept getting kicked off of Edgiro。 And I think it's because some authentication server is overloaded and so I was getting。

 timeouts to it。 And I don't know where that server is located。

 but I wanted to go there and I wanted to not， do nice things to that server because it was making it really difficult to get my work done。

 But that's what I think。 I don't know。 But in some computer I don't know about that's keeping me from getting on the network and。

 keeping me from getting my work done。 And that's the problem with distributed computing。

 We've all run into that situation， not just here on campus where something breaks and it's。

 because something that we don't know about or have any control over is not working。

 And so we can't get our work done。 It's worse reliability。 So potentially any machine crashes。

 now the system goes down and we can't get work done。

 And it's worse security because I break into any component and then I may be able to， from， there。

 leapfrog into other components and so on and so it's kind of my weakest link becomes。

 my greatest vulnerability in my system。 And it's also much more difficult。

 We spent the beginning part of the semester talking about coordination on a single machine。

 where we had multiple threads that needed to coordinate on some data。

 And we could just use test and set。 But now that data is scattered all over the globe。

 So how do we synchronize that？ So what was easy and a centralized system becomes difficult。

 extremely difficult as we'll， see in a decentralized system。

 We're going to see we need very complicated algorithms in order to deal with it。

 So there's all these other issues， right？ There's trust issues。

 I have to trust third parties that might be storing my data or I'm running my computation。

 There's security issues。 There's privacy issues。 Right？ When you store your photos in Facebook。

 what does Facebook do with your photos？ Right？ Or any other cloud service that you store private data in。

 There's denial of service potential risks。 Right？ And there are lots of variants of problems that we had in a single computer environment。

 that now get amplified when we're in this distributed computing environment。 Right？

 How can we build a distributed application from a bunch of third party components？

 How can we trust it that those third party components are going to behave correctly and。

 perform correctly？ Right？ So sort of a corollary of LAMPORITE's quote is a distributed system is one in which you。

 can't do work because some computer you didn't even know existed is successfully coordinating。

 an attack on my system。 Right？ If you're launching a distributed denial of service attack against me。

 And we're starting to now see distributed denial of service attacks that are just phenomenal。

 A terabit of traffic directed at a server。 Right？ So the server on a planet that can absorb that kind of attack。

 All right。 So maybe we need to step back and think about what are some of our goals？

 What do we want out of a distributed system？ What are some of the requirements？

 So the first one I'd say is well， transparency。 And this is really the ability of the system to mask complexity behind some simple interface。

 So there's lots of different kinds of transparencies。 Right？ So one transparency might be location。

 Right？ So I can't tell where resources are located。 Right？ When I go and I read my bear mail。

 where is my bear mail stored？ I don't know。 Right？ Do I care？ No。 As long as I can read my mail。

 I don't care where it's stored。 There's migration。 Right？

 So the servers that manage the data for bear mail are constantly moving that data around。

 for various load balancing and other reasons。 Do I see that？ Is that visible to me？ Well sometimes。

 right？ Occasionally you might go to log into some system and get told and account migration。

 is in progress。 Like banks seem to love to do this sort of stuff。

 You go to like Go Pay a bill and they're like， "Sorry， go away。 You know。

 we're moving your money somewhere else。"， Right？ But in many cases， it's completely transparent。

 I have no idea where my data is or that migrations are taking place。

 And that is good for the providers of the service。 Right？

 So I can store my data where it's most efficient from a location transparency standpoint。

 And from a migration standpoint， it means if I need to do maintenance， I just simply。

 move those accounts off the server。 I can do some hardware maintenance。

 And then I move those accounts and that data back。 Replication。 Right？ How many copies。

 when I save a document to Google Drive， how many copies are created？ Right？

 It turns out it can be in some cases as many as a dozen copies that get created。 Around the globe。

 Again， to provide durability。 But I don't care how many copies。

 All I care is that when I go to get my document， when I go to load my slides， my slides are， there。

 There's concurrency。 Right？ How many users are simultaneously using Bing Search when you're using？

 Well， maybe that wasn't a good example。 Maybe I should have used Google Search。 Right？

 You don't know。 Right？ Performance appears to be independent of the number of users。 Parallelism。

 So when I do a search query， right， I could implement that by going to one machine and。

 that machine reading through a petabyte of index data to find the terms and return the， pages。

 That would take a very long time。 Instead， that query gets routed to tens of thousands of machines。

 each of which has a， small portion of that global index。 Fault tolerance。 Right？

 So machines fail all the time in the cloud。 And you don't see it happening because transparency hides that from you。

 So transparency and collaboration， they're ways for different processes on different machines。

 to communicate with each other。 But that requires communication。

 So you can immediately ask the question， how do these processes communicate？ Well。

 they communicate using a protocol。 Right？ So a protocol is an agreement on how to communicate。

 It includes two components。 A syntax， which is how you specify the messages， how you structure them。

 It's the format。 The order that messages are delivered。 And then it's the semantics。 Right？

 What a particular communication means。 It's the actions that you take when you get that particular message。

 Right？ Now we can-- or what happens when something like a timer expires。 Okay。

 so we can formally describe a protocol with a state machine。

 And typically we'll use some message transaction diagram to represent it。 Right？

 And so you can think about a protocol。 And then we can also add a。

 language that's really this kind of partitioned state machine that we're keeping in sync between。

 two entities。 We can also add stable storage。 And we'll see that when we get into distributed transactions and distributed permit as a way。

 of ensuring that even if failures occur， these distributed partitioned state machines。

 remain in sync。 All right， so let's-- that's kind of the abstract， the formal definition。

 Let's look at an example drawn from the real world。 So human interaction。

 And the interaction we're going to use is the telephone。 Okay， so I want to call my friend。

 So what do I do？ I pick up my phone or open my phone or pick up the handset。 Right？

 And then I listen for dial tone or I check， do I actually have service？ Right？ In this room？

 And I have service。 Great。 Okay。 So then I died。 What happens？

 I start hearing some ringing and then the other person is going to hear ringing。

 They're going to pick up the phone and they're going to answer。 They're going to say hello。

 And I'm going to say hi。 It's Anthony or hi it's me or whatever。 And then I'm going to say。

 "Hey blah blah blah blah blah。" Pause。 Then they're going to respond， blah blah blah blah blah。

 Pause。 And then say bye。 And then they're going to respond back by and then hang out。

 That's a protocol。 So how do we initiate it？ So the ringing initiated the protocol to the other side。

 And that side responded with the introductory。 The hello。

 And then I responded with a hello and along with some requests。 And then they respond back with。

 "Okay， they'll do that request。"， Now we want to close the connection。

 And so we have this joint sort of buy and buy and then we can hang up。

 So that's an example of a protocol。 You're seeing the syntax here。

 You're not seeing the semantics because you're not really seeing the content。

 Although you can see the initial message， the hello and the closing messages of the buy。

 But maybe there's a request and a response that happens in the middle。 So we go back to computers。

 So we have all these applications that we want to create。 Applications that we can't even imagine。

 So maybe it's communication applications like Skype。 It could be terminal applications like SSH。

 It could be networking applications like the network file system。

 And at the same time that all the computer scientists are innovating and application developers are innovating。

 We also have hardware people， electrical engineers who are innovating on new transport media。

 transmission media。 So we have coaxial cables。 So the thing that Comcast runs or fiber optic。

 the thing that AT&T and Sonic run， that go to your house。

 And then you have applications that are talking on top of it。 So many different applications。

 many different ways of interconnecting computers， networking styles and technologies。

 Wi-Fi and wireless， cellular and so on。 And really it's a question of how do we organize this mess？

 Because if this is what it looks like， then every time we add a new application like， "Oh。

 the web comes along。" We then have to implement support in the web for operating on cable modems and operating on fiber modems and operating on Wi-Fi and operating on wired Ethernet and so on。

 And so we'd end up re-implementing every technology or every application for every new technology that comes along。

 Because it could also be the case that we have a new packet radio。

 a new wireless technology for a wide area， maybe based on ham radio。 So no。

 this really wouldn't work。 This is not a scalable approach if every application has to support every potential network technology。

 If every network technology requires re-implementation of existing applications。

 So how does the Internet avoid this？ Well， the goal here is to have reliable communication channels that we can build applications on。

 And we're going to reach that goal through a level of indirection。

 So we're going to add this intermediary layer that provides a set of abstractions for various network functionalities and components and technologies。

 So this allows us now to implement applications once。

 So we implement an application against this intermediate layer。 And similarly。

 when we add a new technology， we're going to implement support for that intermediary layer。

 So it's kind of， again， it's like a variant of just add another layer of indirection。

 which you heard through your entire academic time here at Berkeley。 This intermediary layer。

 this narrow waist here， is the Internet protocol。 And it's the fundamental abstraction that has allowed us to have innovation because when a new application comes along。

 like the web， all it has to do is implement support for IP， the Internet protocol。 And similarly。

 when someone comes up with 802。11， AX or AC or whatever。

 all they have to do is implement support for IP。 And then all of the applications work。

 The applications that were written， Skype was written 20 years ago。

 and it runs on the latest of networking technologies。 Similarly。

 I could pull out a microwave link from the 1980s that supports IP and run modern applications over it。

 And so that's what the power of having this narrow waist of having this layer of indirection or level of indirection gives us。



![](img/09ec77e1f3ad3b5a81728edbc013fe12_7.png)

 So this is called the Internet Hourglass。 And having just one network layer protocol is what gives us this interoperability。

 Underneath， we can have lots of different networking technologies that use lots of different physical implementations。

 So Ethernet over copper， like the connection I have to this room。

 this room might be connected to campus， gateway via fiber。 I could also connect my laptop over 802。

11 to the access points around the room， although I get very upset because authentication is not working today。

 And then on top of that， we have various kinds of transport protocols。

 like the unreliable data gram protocol， transmission control protocol。 And on top of that。

 we have lots of applications。 Questions？ Okay。

![](img/09ec77e1f3ad3b5a81728edbc013fe12_9.png)

 So what are some of the implications here？ Right？ Having this single Internet layer of IP allows arbitrary networks to interoperate any network technology that supports IP can exchange traffic。

 So I can be on that ancient microwave link and talk to someone who's on a modern fiber to the home link。

 Right？ As long as both are supporting IP， I can exchange packets between them。 Okay。

 It also allows applications to function on any network that supports IP。 And this is something that。

 you know， is pretty amazing， right？ When I think about an application from 20。

 30 years ago that supported IP， I can run it on the latest networks today without having to change anything。

 So this has led to phenomenal innovation。 Right？ Look at the millions of apps that are in the various mobile app stores。

 They all run on top of IP。 Right？ And simultaneously look at the phenomenal innovation that we've had below IP development of new wide area technologies like LTE and satellite and Starlink and so on。

 Right？ All of this enabled by having just one transport protocol that everyone implements against。

 The downside？ What happens when you want to change that transport protocol？

 So when we want to go from IP version four， which has a limited address space。

 we'll get into that later on， the IP V six， which has a pretty much unlimited address space。 Well。

 it turns out it takes decades。 So IP V six has been floating around for many decades。

 And we still are just incrementally getting there。 Right？ So when I connect to the wired network。

 I get an IP V four now address。 When I connect to the Wi-Fi。

 I get an IP V six address because we just over the past few years migrated our wireless networks to IP V six。

 We did it because we were running out of addresses， right？ Our daytime population is something like。

 I don't know， 70，000 people。 And each of those people has a bunch of devices and they all are on Wi-Fi and we just didn't have enough addresses。

 And so by moving to IP V six， we have basically unlimited addresses and that doesn't become a problem。

 But it took a lot of work and effort to make that happen。 And globally。

 we're still most stuff is still going in IP V four。 Okay。

 so that gets that's one example of the drawback of layering is that once you have a layer that everyone's dependent on。

 making changes to that layer is incredibly difficult。

 So other disadvantages are that at a given layer and you might end up duplicating functionality of the layer below it。

 Right， so things like error recovery and check sums and things like that。

 Layers might need the same information。 Timestamps are very useful in networks。

 And so I may have timestamps that appear at multiple levels of my networking stack。

 I need to know what's the largest transmission unit that the underlying network supports。

 I can also have performance implications from layering。 Right。

 because I hide details about what's going on。 I make assumptions that the higher layer and that interferes with my performance。

 We'll see some examples of that later on。 Sometimes the layers are not very cleanly separated。

 Sometimes there's overlap in headers， check sums or other sorts of things between layers。

 And so the layers kind of bleed through and I'm doing processing it at multiple layers kind of simultaneously。

 And let's see。 And then sometimes my headers are just big。 Right。

 because each layer adds a little bit of header information， some metadata that it needs。

 And when we talk about data that's small， so example would be the packet voice。 You know。

 that is being used by zoom。 The amount of header versus the amount of voice sample can actually be the case where the headers are much。

 much larger than the small voice sample that's being encoded and transmitted。

 So this really begs the question then of when I've got layering， where do I put functionality？

 Do I put it at layer n， layer n minus one or my highest layer in my system？

 So there was a paper that was written way back in 1984 and it's one of the most influential papers。

 in computer networking。 It's sort of the seminal paper that everybody turns to。

 And it's called the end-to-end， it's called end-to-end arguments in system design。

 There's endless disputes about what this paper means and what it says。

 And oftentimes you'll have people on polar opposite sides of an argument claiming that。

 the paper supports their position。 Okay， well， in summary， read the paper， it's a really good。

 paper to read。 The simple message here， some types of network functionality can only be correctly。

 implemented end-to-end。 Reliability， security， and other types of functionality。 So because of this。

 it means that end hosts can satisfy that requirement， say reliability， without the network's help。

 And so they have to do so because they can't rely on the network， doing it fourth。

 And so what's the point of doing it in the network if I'm just going to duplicate。

 that functionality end-to-end？ So don't go out of your way to do something in the network。

 since it's redundant with what I'm going to have to do at a higher level。 So it seems， simple。

 seems kind of confusing。 What do I mean？ Let's look at an example and that'll make it a。

 little bit clearer。 So let's say I want to do reliable file transfer。 I have a file on the。

 disk of host A。 I want to transfer that file to host B。 And I want to make sure that the。

 contents of that file on host B is equivalent and identical to the contents of the file at host A。

 Very simple。 You do this all the time。 Right。 FTP or SCP and so on。 Basic file transfer。

 So what do I have to do？ Well， I have to read the file in from the disk as the operating system。

 to read the file to a file read into the application。

 Then the application is going to provide those， file bytes back to the operating system and say send it to the application on host B。

 So it's going to send it across the network to the operating system on host B， which is then going。

 to buffer and send those bytes to application on host B， which is then going to turn around。

 open a file for writing and ask the operating system to write those bytes to the disk。 Simple。

 All right。 So how do we make this reliable？ That's just file transfer。 Well， two solutions。

 First solution， we're going to make each step reliable and then concatenate。 Second solution。

 is that we'll just have an end to end check and then retry if we encounter any errors and it's necessary。

 So it's sort of like， you know， we'll just simply read the file at the end， compute some checksum。

 and then send that checksum back to the original application， which will read a checksum from。

 its file， reading computer checksum from its file。 And if they match， we're done。 If not， you know。

 we have to retransmit it。 What do we do in the first case？ Well， in the first case， when we read it。

 from the disk， we'll check and make sure we read the data correctly from the disk。

 Then we'll send it to the other machine and make sure we reliably deliver it across this link。

 And then we'll copy it and we can check some that， you know， check some each of those packets。

 check some what we transmitted。 And then we're going to give it to the application on host B。

 And the application on host B is going to write it out to disk。

 And then it could check some to make， sure that that was reliably written。

 So those are the two different approaches。 Solution one， make each component reliable。

 And then solution two， which is just make the process reliable from， an end-to-end standpoint。

 So some discussion。 Solution one is incomplete。 So let's say I read it in at host A， all right。

 Read it in from this。 And now a cosmic race strikes， the memory chip holding the buffer in memory。

 Flip some bits。 And now I reliably send that over to the other machine。

 And then reliably write it out to disk。 And I've written a corrupted copy。

 The same thing could happen at the destination machine of a cosmic。

 ray could strike a bit and flip it。 So this solution won't work。 And the receiver is going to have。

 to check anyway。 The receiver will， even though every step was reliable， the data got corrupted in。

 trying in one of those buffers and the temporary storage。 I'm going to have to do an end-to-end。

 check to make sure nothing went wrong。 Right。 What about solution two？ It's complete。

 I get the functionality of reliably delivering my file from A and the drive on A to the drive on B。

 Because I do that end-to-end check some tests。 So that could ask， you can ask the question， okay。

 then why would I ever want to implement reliability at a lower layer？ What's the point？

 If I'm still， going to have to at the end of the day， do an end-to-end check。 And if it's messed up。

 then I have to， retransmit again。 That wasn't a rhetorical question。 That was an actual question。

 Yeah。 Yeah， exactly。 So if I don't implement reliability at the lower layers。

 then it might be the case。 If， I've got a really flaky link and I've got a large file moving a terabyte-sized file。

 I might have to transmit it a lot of times before I get a successful clean transmission。

 If I really lost the link， then providing reliability could actually help me quite a bit in terms of。

 efficiency。 It could make it much， much more efficient。 Because rather than retransmitting a。

 terabyte， I might just have to retransmit that 1，500 byte or 8 kilobyte packet that contained。

 the data that was corrupt。 So if we think about the end-to-end principle。

 it's kind of saying that implementing complex functionality in the network。

 isn't going to make the host implementations complexity any less。 I still have to do those。

 end-to-end checks for security or for integrity or for reliable delivery。 But it is going to。

 increase the complexity of my network。 What is a router components that have processors in them？

 It's going to increase the complexity of the code in my operating system for my network。

 If I've now got to have reliability in all of these different components。

 and that's going to impose a delay。 That's going to impose overhead on all applications。

 even if they don't need the functionality。 So let's imagine I do implement reliable， network links。

 And I'm going to use that as part of building my reliable file transfer application。 Well。

 take an example， like for those people who are at home watching me on Zoom。

 Zoom uses unreliable communication。 Why？ Because latency matters when you're dealing with an。

 interactive communication。 And so we've all had those Zoom calls where the audio kept dropping。

 and the video was dropping。 But you could still mostly understand what the person would say。

 That's better than if we said， well， we're going to perfectly deliver every voice sample。

 and so we're just going to keep retransmitting。 And so that person is like a second or two behind。

 And you're a second or two behind that。 That gets really when you have delayed communications like that。

 It's really difficult to have a conversation。 But we need to find some happy medium。 I just had a。

 FaceTime call with one of my colleagues who's in Idaho。 And she's on a satellite link that's。

 super-lossing。 And I could barely understand what she's saying because like every packet's。

 getting dropped。 And I was kind of like thinking about this lecture。 I was like， well， that might。

 be a case where I want a little bit of reliability。 So maybe retry a few times。

 And if it doesn't get， through， then you drop the packet。

 But even that will introduce latency and make it harder to have， a conversation that's interactive。

 So when you have a very lossing link， some degree of reliability。

 introduction could help and improve overall performance， especially if you're sort of。

 retransmissioned unit at the application level is really large。 If I'm dealing with a 30-byte voice。

 sample， retransmitting that isn't hard for the application to do if it really cares about。

 reliability。 But if I'm dealing with a terabyte-sized file。

 retransmitting that's going to be very painful。 Okay。

 so we can think about a really conservative implement kind of viewpoint for。

 interpretation for the end-to-end argument。 So the super conservative view is don't。

 implement a function at the lower levels of the system unless it can be completely implemented。

 at this level。 Or unless you somehow or other reduce the burden on the end-host。 If that's not。

 going to be the case， then don't bother implementing the functionality。 So with this super kind of。

 conservative extreme view， then， you know， we're never going to implement anything at the lower。

 levels。 Because anything that we do at the lower levels， we're always going to have to implement。

 it at our levels。 But some people will take this viewpoint and say that the network should be as。

 clean and simple as possible and basically just simply use best effort to deliver packets。

 do nothing more in the way of processing。 So that's one viewpoint， and there are cases where。

 that makes a lot of sense。 But I kind of argue for a more moderate interpretation， which is， well。

 let's think twice before we implement some functionality in the network。

 So if a host can implement that functionality correctly， then only do it at the implemented。

 at the lower layer if there's some performance benefit or improvement that we would get out。

 of implementing it at that lower layer。 But we want to make sure we only do so if it's not going to。

 impose a performance burden on applications that don't require that functionality。

 So this is the reason why we have TCP and we have UDP。 If you want reliable delivery， you use TCP。

 Don't want reliable delivery or you want to implement it yourself， use UDP。

 So you get to choose as the application at the end host， which are those protocols you're going。

 to choose to use。 So this is an interpretation that we use。 This is the interpretation I use in my。

 research group。 Many people kind of take this sort of more middle of the road approach to。

 how you interpret the end-to-end principle and an argument。 But you could ask the question。

 is this still valid in cases where we have things like。

 the distributed denial of service attacks or protection against inclusion and so on。

 Those are cases where we actually are pushing that functionality into the node。

 So I mentioned earlier， should a denial service attack that directs a。

 terabit per second of traffic at a host。 So you can argue， well， end-to-end says。

 I should deal with that attack at the host。 Well， there's not a host on the planet machine。

 which could absorb a terabit of data and filter out the attack from valid requests。 However。

 if I implement that functionality in the network， then I can decentralize it。

 And now I have individual routers that are maybe dealing with digabit flows， tens or hundreds of。

 gigabit flows。 And there I have a chance of being able to filter out and block those attacks。

 So you're seeing more and more of this with services like CloudFlare and others。

 where they're pushing functionality， implementing functionality in the networks that that。

 traditionally would have implemented at the end host。 If we， again。

 if we follow a sort of strict interpretation of the end-to-end。

 So this is going to the other end and saying we should push lots of functionality like this。

 down into the network because we can do a much better job of implementing it at the network level。

 Still have to implement denial of service protection on the servers， but much easier if I'm。

 dealing with a megabit or a gigabit flow than if I'm dealing with a terabit flow。 Okay。

 questions about end-to-end。 Okay。 All right， so let's switch gears and talk about distributed applications。

 So how do we actually write a distributed application？ What does it take to do？ Well。

 think about it， okay？ A distributed application， right？ There's two components to it。 There's going。

 to be code， right， that's implementing the functionality， and then there's going to be state。

 Right now， when we were writing our applications on a single machine， that state and synchronizing。

 around that state was really easy to do。 But now we have multiple threads that are running on。

 different machines。 And so there isn't shared state。 We can't just simply use test and set。

 to create critical sections。 So we're going to need a different primitive that allows us to have。

 synchronization on shared state in the wide area。 So one abstraction we could use is sending。

 and receiving messages。 Why？ Because if you think about it， right， it's atomic。

 I either get a message or I don't receive a message。

 The two receivers can't receive the same message。 So I can build synchronization on top of sending and receiving messages。

 So I have an atomic primitive if you want to think about it though。 So what's the interface？

 We're going to use a really simple interface to start of the notion of a mailbox。 So that's a。

 temporary holding area for messages that has a queue associated with it and a destination。

 And then they're sending a message to a mailbox。 And so this will send a message to。

 the location identified by the mailbox。 And there's receiving a message from a mailbox into a buffer。

 And so we'll wait。 The thread will sleep on that receive on that mailbox until a message comes in。

 And then it'll one of those threads that's waiting。

 we'll get woken up and we'll copy the message into， its buffer。 Okay。

 So we can ask some questions about like the behavior of a send， for example。 When does send return？

 So it could return when the receiving application's thread actually gets， the message。

 When we get an acknowledgment back saying it got the message。 It could be when the。

 message gets buffered by the operating system on the destination。 Well， maybe it's immediately。

 As soon as we copy it into the operating system buffer， send immediately return。

 The semantics that we want will depend on the application。

 And so it really is a question of like when can the sender know that the receiver has。

 actually received the message。 By only really in that first case， in the other cases we're kind。

 of relying on the systems to ultimately deliver the message。

 But what happens if it's the second case， and the destination host crashes before that message got delivered to the receiver。

 Or it's， buffered locally and the local machine crashes before it can send it on to the receiver。

 There's also a question of when can the sender reuse the buffer that contains that message。

 We'll come back to this when we talk about TCP。 But what a mailbox provides us with is a one-way。

 communication channel between thread one and thread two with a buffer in between。 Well。

 that looks really familiar。 Right。 We saw an instance of thread one communicating to thread two。

 with a buffer in the middle at the very beginning of the class。

 Remember the beginning of the semester？ Hopefully you haven't forgotten it。

 We have a midterm coming up soon。 This is producer consumer。 Right。

 Thread one is producing data that's getting consumed by thread。

 two and we put a buffer in between so we can decouple the execution of the two threads。

 So our send becomes like our V with a semaphore and our receive becomes like the P operation with our。

 semaphore。 But the key difference here now is that where at the beginning of the class。

 thread one and thread two were on the same machine。

 Now thread one and thread two don't even need to be， on the same planet。

 And yet they can communicate and synchronize。 All right。 So if we think about。

 like implementing something producer consumer style， the producer takes a message buffer。

 prepares the message and then sends that message to a target mailbox。 The consumer has a buffer。

 They wait on that buffer with a receive。 I want a message arrives。 It gets copied into the buffer。

 and then they get to process the message。 So the great thing here is that the producer and the。

 consumer， they don't care how much buffer space there is in the mailbox。 They don't have to track。

 that's handled by send and receive in the operating systems。 This is one of the roles of the window。

 in TCP。 It's a function of the buffer space that's available in the band with the delay product and。

 a couple other things。 But it tells us how much space the sender has to send to the receiver。

 Now what if we want to do to a communication？ We just don't want to like throw it over the wall。

 from thread one to thread two。 But we want to make a request， say of a server。

 like a client requesting， something from a server and getting a response。

 I want to read a file on a file server and get back， a response。

 I want to request a webpage from a web server and get back a response。 So this is。

 the client server application。 The client is our requester， the server is our responder。

 The server is providing some service to the client that's making a request。 So what would this look。

 like for a file service？ Well， the client says， I have a response buffer。 I'm going to send the。

 request to the server of read the file， root a big。 And here's the mailbox for that server。

 Where to find that application。 And then I'm going to receive a response back from that server。

 into my client mailbox。 So of course send also， there's a lot of missing details here， but。

 I have to tell the server how to find the client mailbox and all that kind of stuff。 Okay。

 so the server is going to receive into a command buffer that requests from the server mailbox。

 Read root a big。 It'll decode that command， load the file into memory， and then into that。

 answer buffer here。 And then it's going to send that answer buffer to the client mailbox。 So return。

 it to the client that made the request。 All right。 So again。

 you could think about how we would have， done this if we were on the same machine using inter-process communication or。

 you know， pipes and other sorts of things。 Here now we're doing this across the internet。

 Two separate， machines。 Okay， questions about request response。 Yes。

 Is this the same concept as the actor model？ It's kind of similar。 I mean， these are all kinds of。

 protocols where you're making some request and then there's some action that occurs at a remote。

 machine and some response that comes back。 So there's some overlap。 Other questions？ All right。

 so we're going to change gears and now talk about， distributed consensus making。

 So the consensus problem is you have a set of nodes。 They propose， a value。

 It could be true or false。 It could be a or b。 It could be abc。 But I have to make some， decision。

 This is the real world。 So some of those nodes might crash or they might stop responding or。

 they might be malicious。 I want it to be the case that eventually all of the nodes are able to reach。

 consensus and decide on the same value from that set of proposed values。 So that， in the nutshell。

 is the distributed consensus making problem。 So it's a form of， distributed decision making。

 Examples are choose between true and false， commit versus abort and so， on。 Now。

 one important component of distributed consensus or distributed decision making is， durability。

 Once you make an answer， it has to persist。 And so it's very important that you。

 include stable storage so that you have a durable way of recording that decision。 So like in a。

 transaction， this is the D and acid， the durability component。 Now， in a global scale system。

 lots of， different ways we can do it。 Everything from distributed ledgers like blockchain to a ratio。

 code or multiple replicas。 But the key thing is， however we do it。

 we want to make sure our decisions， persist。 Okay。

 So let's look at how hard it is to reach distributed consensus by looking at what。

 seems like a deceptively simple problem。 It's called the general's paradox。 So here are the。

 constraints。 We have two generals， the general on the mountain over here， general on the mountain。

 over here。 They can only communicate via messengers。 All right， so they're going to send messengers。

 through the battlefield from one mountain to the other mountain。 And there's， you know。

 I don't know， there's bobcats and bears and， you know， other things that can eat the messengers。

 And that's the only way they can communicate。 The messengers can be captured， you know， all sorts。

 of things can happen。 The problem is that they each have an army， but the armies aren't that big。

 in isolation。 And they're going to attack a target with a large army。 That army is larger than any。

 individual general's army， but the combined general's armies， the two armies。

 is larger than the target， army。 So if they attack at the same time， they will succeed。

 If they attack at different times， they will fail and die。 All right。

 So this is named after Custer who died at Little， Bighorn because he arrived early。 All right。

 So here's the question that I'm going to ask。 Can messages over an unreliable network be used to guarantee that two entities do something。

 simultaneously？ So， you know， we can make an unreliable network reliable， right？ Because we can。

 send acknowledgments， right？ We can send a flood of messages。 But kind of counterintuitive。

 the answer is no。 Even if all the messages get through。

 that's the part that's really confusing oftentimes to students is even if I say every single message。

 will get through， can you make this work？ The answer is no。 So let's look at a mockup and。

 what the message exchanges might look like。 And that'll help us see why we have this as a paradox。

 Here are two generals。 Okay。 So the general on the left is going to propose a talk。

 Let's attack at 11 o'clock。 Okay。 All right。 Are we done？ Can we go attack at 11？ Yes？ No， maybe。

 Exactly。 So the answer is no， right？ Because what if the general on the right doesn't get the。

 message because the mountain lion eats this messenger？ Okay。 How does the general on the left。

 know that the general on the right got its message？ Simple。

 We send a message in the other direction。 Yes， 11 a。m。 works。 Let's attack at 11。

 Can we attack now at 11 and live？ I see people nodding at if you people shaking out yet。 Yeah。

 So the frustration here is that the general on the right doesn't know if their。

 messenger got to the general on the left。 And what happens if it didn't？ Right？

 Then maybe it did get through or maybe it didn't。 If it didn't get through。

 then this general goes and attacks at 11。 Well， the general on the left never got the message。

 saying that it was okay to attack at 11。 So they're not going to attack at 11。 And they， you know。

 doesn't end well for the general on the right。 We can solve this。 So it's 11。

 We're going to attack at 11。 Okay。 Now the general on the left has told the general， on the right。

 I got your last message。 And so we're good to go。 Right？ Yeah？ No？ Yeah。 This is the same problem。

 Right？ Because now the general on the left told the general on， the right。 Yeah。 We can go at 11。

 but they don't know if their message got through。 If their message， didn't get through。

 then this general on the right might not know that their message got through。

 And so they're not going to attack at 11。 We can solve this。 We're computer side this。

 We just send another message。 Right？ So this is the problem。 We don't have any way of knowing。

 that that last message got through。 So we can never confirm that it's okay to attack at 11。

 No matter how many messages we send， even again， if we guarantee that we know that every message。

 got through， we still don't really know that every message got through。 So， you know。

 this doesn't happen in real life because we have out of band communication。

 But the two generals just， you know， use their walkie-talkies or their satellite phones and they're。

 able to in real time confirm that the other one knows that the attack plan is going to happen at 11。

 Right？ But if we look at two computers that are trying to agree to do something at a specific time。

 and can only communicate via these messages over unreliable networks， we cannot reach consensus。

 on a very specific time。 So we need to do something other than simultaneously。 Right？

 We need to make a decision， but we have to， unfortunately， remove time from that equation。

 because we don't know about this last message。 Okay。 So if we can solve the general's problem。

 we're going to solve a related problem instead。 And that's the problem of distributed transactions。

 So this is two or more machines agreeing to do something or not to do something and making。

 that decision a Thomas。 So either everyone agrees to do it or everyone agrees we're not going to do it。

 The key thing that we've done here was we removed the constraint of time and changed it into eventually。

 things will happen。 Rather than saying it's going to happen at 11， we say eventually it will happen。

 Or we all agree it's not going to happen。 And this is codified in a protocol called。

 two phase commit developed by another Turing Award winner， Jim Gray， who was also the first。

 Berkeley CS computer science PhD back in 1969。 And he made many， many， many contributions。

 to the foundations of databases。 He was really hugely impactful in the world of databases。 Okay。

 So how does this， what are some of the components？ So we have a persistent stable log。

 on each machine。 And this is where we're going to keep track of whether or not the commit happened。

 If a machine crashes， when it recovers， it's going to look at its log to see what was the state of the。

 world at the time that it crashed。 We're going to have two phases。

 The first phase is a prepare phase。 So we're going to have a global coordinator and they're going to request that all of the participants。

 promise to commit or roll back the transaction。 And so the participants are going to record that promise in the log if they agree to commit and。

 then acknowledge if anyone votes to abort， then the coordinator writes abort in its log。

 and it's going to tell all of the participants abort and each one is going to record abort in its。

 log。 Now， if everyone says， let's go ahead and commit， then we have the commit phase。 So if。

 everyone responds that they're prepared， the coordinator writes commit to its log。

 then it asks all the nodes to commit。 They respond with acknowledge。 After it receives all the。

 acknowledges， it writes got commit to its log。 Okay， so the decision point here is when the。

 coordinator writes commit to its log。 At that point。

 we are committed to phase complete to phase commit， will ensure that everyone eventually commits。

 And that's what we use the log for， guaranteeing， you know， once we put it into stable storage。

 we guarantee that either we're， going to proceed with the transaction or commit。

 or we've decided to abort the transaction and， everyone will roll back the results。 All right。

 so the algorithm here， one coordinator and workers， are replicants。 At a high level。

 the coordinator asks all the workers， okay， everybody ready to commit？ If all the workers say， hey。

 we vote to commit， then the coordinator says， global commit， everyone will commit， right？ Otherwise。

 if anybody said， no， I vote abort， then the， coordinator broadcasts to everybody global abort。

 And everybody rolls back the transactions， releases， all the locks， it's like it never happened。

 Workers obey whatever global message they receive。 So， if the global message is to commit。

 they will commit the global message is to abort， then they， will abort。 And again。

 we're using a persistent stable log on each machine to track what's happening， at that machine。

 so each of the replicas and at the global coordinator。 So when a machine crashes， again。

 as I said before， it's going to wake up， check its log to recover any data and understand。

 what the state of the world was at the time that it crashed。 All right， so one machine。

 the coordinator initiates the protocol。 It asks every machine， vote up or down on the transaction。

 Two possible votes commit or abort。 Only going to commit if we receive unanimous commit votes。

 from all of the machines。 So anybody basically has veto power and can say abort that transaction。

 Now， if a worker agrees to commit， then it has to guarantee that it's going to accept the transaction。

 So it's going to record that commit in the log before it notifies the server。 Once it records。

 that commit in the log， if it receives a go ahead and global commit。

 it has to complete that transaction。 It can't change its mind and say， oh， now I want to abort。

 Once it writes that commit in the log， it is guaranteeing that it will see that transaction to completion if told to do so。

 Okay， if the worker decides to abort， then it's guaranteed it will never accept that transaction。

 It records the abort in the log and can roll back that transaction and informs the server。

 I decided to vote abort。 At the end， when we decide to commit the transaction， the commit phase。

 the coordinator hears that everyone says， vote commit， it's then going to。

 record the decision to commit in the log。 This is the point again， where now the transaction is。

 committed。 No matter what happens to the coordinator， or whatever。

 what happens to any of the machines， we guarantee that we will eventually be in the state where all the machines will have committed。

 We'll go over some of the failure cases in just a moment and that'll make it clear。

 Then we apply the transaction and form everybody else。 If we decide to abort， because anybody。

 vetoes and says abort the transaction， then we're going to record in the log that we have aborted。

 and we're going to inform all of the machines with global abort。 So if we think about it， right。

 there's two actions。 Either everyone has agreed to commit。

 and we ensure that we go down that commit path atomically， or one or more has decided to abort。

 and we go down the abort path and notify everybody that it will abort。

 Only one of these outcomes can occur。 We either agree to commit the transaction， or we disagree。

 and the decision is to abort the transaction。 All right。 Questions？

 We'll go through a bunch of examples which should help a lot。 Yes？ Yeah， that's a good point。

 The question is， you write to the log as a worker before you tell， the coordinator your vote。

 That's really important because that log is persistent。 So I record that I decided to commit。

 or I report that I decided to abort， then if I immediately crash， eventually I'll come back up。

 I'll scan through my log， and I'll see I decided to commit or abort。

 and I'll contact the coordinator。 And we'll see an example of that in just a moment。 Okay。

 so some administrative stuff。 We have a midterm coming up on the 28th。

 It's going to be from 7 to 9 p。m。 All course material is fair game。

 although again the focus is going to be on the material since the last midterm。

 but that doesn't mean you can forget what happened 12 weeks ago。

 And there will be a review session on the 25th time and place to be announced。 Okay。

 so let's go through the algorithm in some more detail。

 So the coordinator sends out a vote request to all of the workers。

 The workers are sitting there and they're waiting for a vote request from the coordinate。

 Now if they're ready to commit， then they'll send a vote commit to the coordinator。

 They're not ready to commit， then they'll send a vote abort to the coordinator。

 and then they can immediately abort。 Now why can they immediately abort？

 Because they know the outcome。 If I vote to commit， I can't immediately commit and release。

 locks and do all that stuff， because I don't know if somebody else might cause the transaction to。

 be aborted。 But if I myself say I'm not ready， I'm going to vote for abort， then I can go ahead。

 and abort， because I know that the coordinator will listen to me and will ultimately abort the。

 transaction。 So I can just stop that transaction right now， release all the locks。

 roll everything back。 Okay， it would be equally correct for me to wait until I get the global abort from。

 the coordinator， but as an optimization， I can just clean up things right away。 Okay。

 so at the coordinator， if everyone votes to commit， it sends the global commit to all the， workers。

 If anyone disagrees， it'll send a global abort to all the workers。 And then again at the， workers。

 if they receive a global commit， then they'll go ahead and commit。 If they receive a， global abort。

 then they'll go ahead and abort。 All right。 So now let's， we're still kind of in。

 the algorithm phase。 So let's look at some execution examples of how this works。

 So we'll start first。

![](img/09ec77e1f3ad3b5a81728edbc013fe12_11.png)

 with a failure free case。 All right。 So here， the coordinator sends out the vote request。

 In the failure free case， all the workers are ready and they vote to commit。 All right。

 Now the coordinator has all those votes， records in the log， commit。 That's our commit point。

 And then broadcast out global commit。 All right。 And everyone will commit。

 So if we peer under the covers and we look at the state， machine of the coordinator。

 it's a very simple state machine。 All right。 We start in the init state。 We send。

 we receive a start。 So the program gets told start the two phase commit。

 And it sends out a vote request。 And then it waits。 If it receives a vote abort。

 it sends a global abort enters the abort state。 If it receives all vote commits。

 then it enters the commit state and sends a global commit。

 The workers also implement a very simple state machine。 They start in the init state。

 waiting for a vote request。 When they receive that vote request， they can either choose up。

 I'm going to vote abort， in which case they enter the abort state。 Or they can say， okay。

 I'm ready to commit and send a vote commit。 Then they enter the ready state。 And they wait again。

 They wait to hear back from the server， global abort， or to hear back global commit。

 And based on that， they'll either enter the abort state and roll everything back。

 or enter the commit state， finalize everything， release the locks， and the transaction is committed。

 So let's think about this。 Failure for the coordinator only really matters。

 when we're waiting for messages。 All right。 So when we sent out our vote requests。

 now we're waiting for messages from the workers。 So if one of the workers fails。

 then we're going to sit stuck in this waiting state。 And so if we don't receive all end votes。

 after a period of time， we could just simply time out and abort the transaction。

 That'd be the simplest implementation。 More complicated implementations， maybe we'll retry。

 sending a message to anyone who hasn't responded because maybe that message got lost or something。

 But conceptually， we just wait a fixed amount of time。 If we don't hear back。

 we abort the transaction。 So here's that example of a worker failure。

 So we send out the vote requests。 We get back a vote， commit from worker one and from worker two。

 And who knows what happens to worker three？ No， maybe their message gets lost or something。

 But eventually we tie or maybe they crash， we time out， and then we're going to send a global abort。

 At some time later， this worker three is going to recover， look through its log and say， hey。

 I have this transaction， contact the coordinator and say， what happened to this transaction？

 The coordinator will say the transaction was abort。

 In which case the worker will then clean everything， up， roll it back， release the locks。

 and proceed。 So that's where the eventual side of things comes in。

 Even if it takes a week for this machine to， get rebuilt and come back online。

 eventually it will and eventually will apply the results in this。

 case of having aborted the transaction。 Okay， when we think about coordinator failure。

 from the point of view of the worker， there are two places where we wait。 We wait for that vote。

 request in a NIN。 And from a worker standpoint， they could time out also。 They don't hear， you know。

 they've got a transaction that's ending， they're waiting to see， are we committing or aborting。

 I haven't gotten asked to enter Q-phase commit， they could just simply time out and abort。

 Later on when the coordinator contacts them， finally say， hey， I didn't hear from you。

 I boarded that transaction。 And that's fine。 The coordinator will handle that。

 it'll just get a vote abort， and then it'll send out a global abort。

 The other place where we can wait， is which is more complicated is in the ready state。

 And waiting here is really bad。 It's really， really bad， right？ Because in the NIT state。

 the worker has control。 All right， so think about this。

 this is a distributed transaction system on individual workers。

 there's a ton of transactions that are going on。 And each one of those transactions is grabbing。

 locks and preventing other transactions from being able to potentially make progress。

 So we want to complete transactions as quickly as possible。 When we're stuck in the NIT state。

 we have control as a worker。 Because we can always say， hey， it's been 10 minutes。

 I haven't gotten a request for this transaction。 So I'm just going to time it， out。

 I'm going to abort the transaction， release the locks， allow other transactions in the system。

 that are waiting on those resources and locks to proceed。 When we're in the ready state， it's。

 different。 We've told the coordinator， we're committing。 And so we can't release those locks。

 we can't abort， the transaction， we have to wait until the coordinator says， okay。

 we're going to commit， or no， we're， going to go ahead and abort the transaction。

 And so getting stuck in this ready state is really， bad。

 because it's holding up resources on that particular node， and it could be for an indeterminate。

 amount of time， and the node has no control over leaving the ready state。 Okay。

 so examples of coordinator failure。 So the first case， we don't get a vote request from。

 the coordinator， so because the coordinator crashes or something happens， and so the workers just。

 simply time out abort the transaction and keep going。 And eventually， when the coordinator comes。

 back， they'll say， hey， we all decided to abort the transaction because you went away。

 When we're in the ready state， we've got a vote request， we've all sent back， vote commit， or。

 we don't even know， maybe some of the workers have decided to vote abort because they had some issue。

 We're waiting to hear from the coordinator what's going to happen。

 And we're blocked waiting for the coordinator to eventually restart， and then perhaps send out。

 a global abort， or it could send out a global commit。 It's all going to depend on whether the。

 coordinator had written commit to its log or not。 If it hasn't written commit， then it'll abort the。

 transaction。 If it has written the commit， then it's going to send out a global commit。

 So one little minor optimization that people will sometimes make in this case is if you don't。

 hear from the coordinator， then you try to talk to all the other workers。 And if you can find any。

 of the workers that voted to abort， then you know the final decision is going to be a global abort。

 rather， and so you can go ahead。 And even though you are in the ready state， you can safely abort。

 But that's problematic， and you know just making sure you implement that correctly is complicated。

 But that's one of the optimizations that people will do in practical settings。

 because of this large potential gap between when the coordinator fails， and when it restarts。

 and the fact that it's holding up other transactions on these nodes。 Okay。

 so related to this is again durability。 All nodes are using stable storage to store， the log。

 the current state of things。 Nonvolatile storage could be either hard drive SSD or some。

 some kind of a nonvolatile RAM。 So now when we recover from a failure at a node。

 it'll look at that state and that tells it how to proceed。 Right， so if the coordinator finds that。

 it was in the init state， the wait state or the abort。

 it knows the transaction will be global abort。 If the coordinator wakes up and sees that it was in the commit state。

 then in this case， when it restarts， it's going to send out a global commit message to all of the workers。

 So it's really， you know， a question of when did this crash occur？ Did it occur before that。

 decision was made and written to stable storage？ In which case that's a global abort。

 we're going to occur after we wrote commit to the log， in which case it's going to be global commit。

 For the workers， if they come back up and they're in the init state or the abort state。

 they can locally abort because if the coordinator asks them， they'll say， "I vote to， I vote abort。

 I don't vote commit。" If it's in the commit state， then that means it。

 agreed to commit the transaction。 And so if it has to replay the log or whatever。

 it's going to do that， to ensure that the results of the transaction are durable。

 And if it wakes up and it's in the ready， state， then it's going to ask the coordinator。

 "What was the final decision？" Was the global decision。

 to go ahead and commit or was the global decision a global abort？ Okay。

 So before we dive into discussions， are there any questions about the phase commit？ Yeah。

 So the question is similar to the case with the general's paradox。 How does。

 the coordinator know that all of the workers receive this global commit？ Right？ So the thing is。

 if the workers don't receive a global commit and they're stuck in the， ready state。

 they're eventually going to come back and ask the coordinator， "Hey， what did you， decide？" Right？

 And they'll get a response back from the coordinator。 We decided a long time ago。

 we were going to do global commit。 And so they'll commit。 That's correct。

 So let's say we end up in the situation， I don't know if I have an exact picture of it。

 but where a worker receives global commit。 Okay？ But before it can right commit to its log and commit。

 process， it crashes。 All right。 So when it wakes back up， it's going to read through its log。

 and the last thing it's going to see is already。 And so then it'll go and contact the coordinator。

 The coordinator will say， "Hey， I already told you we globally committed。" And they'll say， "Oh。

 okay， I'll go ahead， commit， write a commit to the log， and then I'll commit the transaction。"。

 So the key thing here， and this is where the timing， again， and I've tried to overemphasize。

 when we're writing the stable storage， is to make sure that no matter where a failure occurs。

 we always end up in a state where we can ultimately either continue the transaction and commit。

 or we abort the transaction。 And we don't end up in a state where， well， we don't know what to do。

 There's something inconsistent。 Yes。 [inaudible]， Exactly。

 So the key difference here is that in the general's paradox， we tried to make sure our。

 distributed decision was going to occur at a specific time， 11 a。m。 Here， there's no time down。

 If a machine goes down， it might be a week before that machine comes back up。

 but when it comes back， up， it will ask the global coordinator what was the final decision。

 So one of the things is， if you remember earlier， I mentioned that once you do the commit。

 you then send an， acknowledgment back to the coordinator。

 That's when the coordinator knows when it's gotten all， of those acknowledgments。

 now it can delete that commit record。 Up until it gets all of those， acknowledgments。

 it has to retain that commit record because a week later， some worker that's。

 been offline for a week might come back and say， "Hey， what happened with this transaction？"。

 And it can tell it， yes， we decided to commit the transaction。 So there's no time bound on。

 when the decision gets implemented， just that we're going to reach a decision and do that。

 in a decentralized manner。 Yes。 [inaudible]， Yeah， so that's a very key distinction。

 So vote request occurs at the end of a transaction。

 when we've decided we want to commit the transaction。 That's when we initiate the two-phase commit。

 process。 So this is not starting the transaction， this is finishing the transaction after we've。

 decided we want to commit or abort the transaction。 All right。 Any other questions？ Yeah。

 [inaudible]， Yeah， so if one of the workers crashes before responding back to the vote request。

 then， we just treat it as a vote abort and it times out at the coordinator and then it makes the decision。

 to abort the transaction， which is persistent。 And so whenever that worker comes back， it'll be。

 told that the transaction did not commit it was aborted。 [inaudible]， That's correct。

 If the workers offline for an extended period of time， then all those pending。

 transactions would be decided to be abort。 All right。 Okay。 I will see everybody on Thursday。

 [inaudible]。

![](img/09ec77e1f3ad3b5a81728edbc013fe12_13.png)

 [ Silence ]。