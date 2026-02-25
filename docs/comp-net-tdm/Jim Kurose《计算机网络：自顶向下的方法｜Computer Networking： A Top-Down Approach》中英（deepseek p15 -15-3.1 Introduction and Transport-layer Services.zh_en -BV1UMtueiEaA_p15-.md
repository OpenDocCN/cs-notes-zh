# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p15 -15-3.1 Introduction and Transport-layer Services.zh_en -BV1UMtueiEaA_p15-

![](img/86e14f14c5e51d71debf98658238dab0_0.png)

🎼，Now that we've finished our study of the application layer。

 we can head down into the transport layer and we'll see that this is one of the key pieces of the internet architecture it's also one of my favorite ones to teach because there are so many fundamentally important challenges that we're going to encounter here we'll look at this question of how can two entities reliably communicate over a channel in which messages can be corrupted or lost we'll look at the question of how to distributed entities synchronize shared state we'll look at a question of how a collection of different entities can actually adjust their communication rates so that they don't the some of them don't actually overflow and exhaust network network resources and of course we'll study the two main transport protocols that are available in the Internet today。

 UDP and TCP so let's see what we're going to study here。Our approach， as always。

 is going to be to start with principles。How is it that multiplexing and de multixing can be done What about reliable data transfer or flow and congestion control We'll start out by looking at the principles underlying how these services might be implemented。

And then having studied principles， we'll look at how those principles are actually embodied in internet transport protocols。

 and here we'll take a look at two protocols， UDP， which offers a connectionless。

 best effort service between communicating processes and TCP， which offers reliable。

 flow controlled and congestion controlled connection oriented transport。

Let's take a step back and take a big picture view of transport services and protocols and here there are three things we're going to want to talk about we're going to want to talk about the notion of logical communication between application processes that are running on different hosts we're going to want to talk about the transport protocols and how the sending and receiving side what actions are taken on the sending and receiving side and then we're going to want to take a look at the internets two transport protocols that are available to applications TCP and UDP so let's start by diving into this issue of logical communication and biological communication what we mean is that from a transport layer perspective the two communicating sides。

 the sender and the receiver， they're logically connected to each other by essentially a direct link in reality the host may be on the different sides of the planet。

 they'll be separated by many different networks with different routers and different links but from a logical point of view。

Imagine that these the sender and the receiver are directly connected to each other now the medium by which they're connected to each other。

 the channel over which they communicate may actually lose messages or reorder messages or flipbits and messages but we're going abstract away everything that sits between these two communicating processes and really just look at the properties of that channel that connects them and then how they implement their services given what that channel is。

Now we've talked about logical communication between processes that are running on different hosts and this notion of the difference between communicating processes and communicating hosts is an important one because it really gets into the heart of what's the difference between the transport layer and the network layer and what are the services that they provide。

Here's an analogy that might be useful imagine we've got two houses and say there are 12 kids that are living in each of those houses。

 one houses， Anne's house， one house is Bill's house。

 we can think of internet hosts as being equivalent to the houses and processes as being the kids。

 so there are many processes that are running in each host and there are many kids living in each of these houses。

 we can think of the application level messages that are being exchanged between processes as letters that are sealed in envelopes and these envelopes then are passed between the houses。

Now let's think about what happens when a letter arrives to a house's say it arrives to Anne's house An's now got to take that letter and deliver it to one of her children。

 so similarly when a datagram arrives to an internet host that host needs to be able to deliver that datagram up to the appropriate process to hand out and arriving letter up to one of her kids the network layer protocol is equivalent to the postal service。

 the postal service job is simply to deliver letters between one house and another house。

 what happens inside the house is the job of the transport layer getting the messages from one house to another is the job of the postal service or of the network layer。

So hopefully this analogy makes clear the distinction between what the network layer does and what the transport layer does。



![](img/86e14f14c5e51d71debf98658238dab0_2.png)

So that's what we mean by logical communication between entities。

 let's next take a look at the actions that are taken at a transport layer sender or receiver and then we'll take a quick look at the UDP and TCP transport protocols which we'll cover in depth shortly。



![](img/86e14f14c5e51d71debf98658238dab0_4.png)

Let's use this animation here to take a look at transport layer actions at both the sender and at the receiver side and let's start at the sender。

 So as we saw in chapter 2， when we're looking at the application layer。

 everything starts when an application layer process creates a message and drops that message into the socket on the lower side of that socket is the transport layer。

 The transport layer is going to take that application layer message。

 it's going to determine what needs to go in certain header fields of the transport layer segment。

 it's going to create that segment， and then it's going to pass that segment down to the network layer to the IP protocol in the case of the internet。

 and it's going to be the job of the network layer。

 the internet protocol to actually deliver that IP datagram from the sending host to the receiving host。

Now let's see what happens on the receiving side。 the transport layer of the receiving side segment is going to be received from the network layer。

 We're then going to want to check certain header value fields， for example。

 to make sure that the segments not been corrupted。

 going want to extract the application layer message and then demplex that message up to the appropriate application layer socket。

 Let's wrap up here by just taking a very quick look at the TCP and UDP protocols。 TCP。

 which stands for the transmission control protocol。

 is going to provide reliable in order delivery between application level processes。

 Also we'll see that this delivery is subject to congestion control and flow control and that in order to implement reliability congestion control and flow control。

 we're going to need to set up a connection with connection state at both the sender in the receiver' side and we'll look at how that's done shortly。

 The other Internet transport protocol of course， is UDP。



![](img/86e14f14c5e51d71debf98658238dab0_6.png)

![](img/86e14f14c5e51d71debf98658238dab0_7.png)

The user Datagram protocol this is really a best effort sort of no frills approach for a protocol。

 it's got unreliable delivery messages may be delivered out of order and so as we'll see not too much is done there So these are the two principal internet transport protocols。

 you may want to think just a little bit about the kinds of service that are not available actually in the internet and through these transport protocols there is。

 for example， no service that provides a guarantee on the amount of time between when a message is sent into a socket and when it pops out the other end。

 that might be a really valuable type of service for example。

 for interactive voice applications like phone calls for example。

 Similarlyly there's no service that provides a guarantee and the amount of bandwidth between sender and receiver for example。

 that a streamed video might receive a guaranteed number of megabits per second in throughput between sender and receiver that too。

You could imagine it might be a very valuable service to be able to have at the transport layer。

 but neither of these two services are actually provided by an internet protocol and you may want to think a bit about why is it that these aren't provided services it's an interesting question gets to the heart of what are the services。

 what's a minimal amount of services that we really need in order to provide effective communication。

So that wraps up our brief introduction to the transport layer。

 now we can start digging down into some of the basic principles and techniques that we just talked about。



![](img/86e14f14c5e51d71debf98658238dab0_9.png)

![](img/86e14f14c5e51d71debf98658238dab0_10.png)