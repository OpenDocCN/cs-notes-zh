# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p05 -05-1.5 Layering, encapsulation.zh_en -BV1UMtueiEaA_p5-

In this section we want to tackle a pretty abstract problem， the internet is huge。

 it's got billions and billions as the saying goes of interacting pieces， we've got applications。

 we've got devices， we've got people at the edge， at the core， we've got links， we've got routers。

 we've got switches， hardware， software， and all of this interacts。

And so the abstract problem that we want to address is how do we tackle the design and the discussion and for us the teaching and learning of such an incredibly complex system。



![](img/02fce80d56b42dc94087e9e8f23563eb_1.png)

And so in this section we're going to do three things。

 we're going to introduce first the concept of architectural layering。

 and then we're going to look at the internet and look at the layers of the internet。

 and then finally we're going to sharpen up our definition of what we mean by a packet we've sort of referred to it vaguely as data that's flowing around through the network and we're going to want to be much more precise with our definitions here。

So let's begin with an analogy， since analogies are often useful。

 what's a complex system that you sometimes use or that you can think about？

Well how about airline travel or airline systems， that's an incredibly complex system think about it。

 there are planes， there are runways， there are towers， there's baggage， baggage claim。

 there's ticket， ticket counter security， there are travelers， there's gate agents。

 This is a really complex system of a lot of interacting pieces。

 How might we actually define and discuss such a system。 Well。

 you might think of it first as a series of steps。You buy a ticket。 you go to the check encounter。

 You' are authenticated。 You're starting your end to end journey。 You check your bags。

 and now you and your bags hopefully are on your end to end journey。 You go through security。

 You go to the gate。 you wait， and then you board your plane。 your plane taxis。

 It takes off it flies to the destination， there's a lot of routing of airplanes in between。

 you know， And when your plane arrives at the gate， you do these steps in reverse。

 You've completed your end end journey。 So this is helpful in one sense。

 and that we've broken down the trip into smaller pieces。

 but we want to be even a little more abstract here。 We want to think horizontally。

 There's a function on the take off side and a related function on the landing side that together provide and implement a service。

 delivery of your plane from source to destination， for example， or at a higher level。

 the delivery of you from an airport entrance to an airport exit。

 There are functions on the take off side and the landing side that together provide that service and to implement。



![](img/02fce80d56b42dc94087e9e8f23563eb_3.png)

At that service， they rely on the services of the lower layers in the stack。



![](img/02fce80d56b42dc94087e9e8f23563eb_5.png)

Well， let's step back and ask ourselves what's the advantage of this layered way of thinking of having a layered architecture Well。

 really there are two advantages。 first of all， this explicit structure that we have shows the different pieces of the system and the relationship to each other so we've got a very clear reference model for talking about the system。

 the system pieces and how they interact with each other and secondly。

 from an implementation point of view， we've really modularized the design。

 think about a layer the layer takes information in the internet from above uses the services of the layer below to implement its own service So if we make a change to the system we change how a service is implemented but keep the service interfaces the same we've localize the changes think about the airline analogy that we looked at if we change how the gate agent actually functions well that doesn't necessarily affect ticketing or baggage or how planes take off。

So we've got that modularization that helps us with implementation with maintenance over time Well the internet is clearly the probably the largest and most complex human system ever engineered does the internet have a layered architecture well of course it does otherwise we wouldn't be talking about it here so let's take a look。



![](img/02fce80d56b42dc94087e9e8f23563eb_7.png)

![](img/02fce80d56b42dc94087e9e8f23563eb_8.png)

The Internet architecture has five layers， the application layer， the transport layer。

 the network layer， the link layer， and the physical layer。

The application layer includes the application layer protocols that control the sending and receiving of messages among the distributed pieces of the application。

 We'll cover the application layer first since we're taking a top down approach in this course。

 and we'll use this Internet protocol stack here to actually provide the structure for our course。

 Another advantage to a layered architecture。 We'll start at the top with the application layer and then work our way down。

The transport layer transports application layer messages from one process to another。

 we saw earlier that packets could be lost along the way， for example， in router buffers。

 so perhaps the transport service has no reliability guarantee。

 or perhaps the transport layer implements a reliable data transfer service on top of a network service that can lose packets。

 that's what the internet's TCP protocol does。The network layer transports data from one end device or host to another。

 maybe reliably， maybe not， depends on the service model。

 The network layer of the internet does not provide reliable transport host to host service。

 It service models called best effort service， which means hey， we'll do our best。

 but we make no guarantees， and you should note that there's a subtle difference here between host to host transfer。

 which is done at the network layer and process to process transfer。

 which is done at the transport layer。The link layer transfers data between two network devices that are at either ends of the same communication link and the physical layer controls the sending of bits into this link。

Well we've talked many times about the notion of exchanging data and now it's time to be much more precise about that and let's start at the application layer at the application layer we say that the pieces the distributed pieces of the application exchange messages with each other。

 so at the application layer， the unit of data sometimes called a protocol data unit that entities exchange is known as a message now at the transport layer we've seen that these messages are now exchanged by the transport layer from one part of the network to the other。

What the transport layer will then do is take a message from the application layer and include some additional information with that message to create a new data unit。

 a new protocol data unit， known as a transport layer segment and this segment is the unit of data that's exchanged between entities at the transport layer。

 what information is included in the segment along with that application layer message。 Well。

 some information is going to be needed to identify the process to which the message is going to be delivered at the destination。

 since there might be many processes running there。

 in the case of a transport layer protocol like TCP that implements reliable data transfer。

 will need to include a lot of information in the segment to actually implement that reliable data transfer service。

The process of taking a data unit from a higher layer。

 adding information to create this new data unit， this new protocol data unit at another layer is called encapsulation。

 encapsulation happens everywhere in the internet， and so it's going to be a really important concept for us to get down。

A network layer protocol encapsulates the transport layer segment and adds its own network layer header information H sub N to create a network layer datagram。

 The datagram is the protocol data unit that's used at the network layer and the header H of N is used by the network layer protocol to implement whenever its network layer services will see。

 for example， that in the Internet's IP protocol， the IP address of the sending and receiving hosts are contained in the network layer header。

And the link layer similarly encapsulates the network layer datagram and adds its own link layer information。

 The protocol data unit transferred between the link layer sender and the link layer receiver is known as a frame。

Now let's focus on the messages， the segments， the datagrams， and the frames， and their headers。Well。

 we've been thinking horizontally in terms of layers and vertically in terms of data flowing down and up the protocol stack。

 and that's animated here。And so we see here data flowing down the stack across and then back up the stack on the other side。

 and as data is flowing down the stack， headers are progressively being added to create a segment and then a datagram and then a frame and then going across the wire。

 and then as data flows up the stack， those headers are progressively red acted upon and then removed as data flows up the stack。

 So this is a really important slide and you want to make sure you've got a good handle on this idea of encapsulation and data flowing down a stack and then back up a stack again。

And now let's take the end to end view as an application layer message starts its journey at an application layer process at the source and makes its way to an application layer process at the destination。

 And as you watch this animation， look for two things in particular。 First of all。

 pay attention to what's happening with the headers at each layer in the protocol stack。

 And secondly， as you do that， you'll note that deeper within the network。

 the switches in the routers only implement the lower layers of the protocol stack。

 That's because their job is to only forward frames and datagrams。

 they don't have to operate on the higher level transport layer segments or application level message inside the datagram or frame。

Well， we've covered some really important conceptual ideas in this section。

 We talked about the general notion of layering in an architecture。

 We looked at the internet architecture， and then we looked at the idea of encapsulation。

 taking information from a higher layer， wrapping a header around it to implement a service and then passing that down to a lower layer。

 So we've covered a lot of important conceptual ideas here coming up next。

 we're going to take just a quick look at some of the threats that networks face。



![](img/02fce80d56b42dc94087e9e8f23563eb_10.png)