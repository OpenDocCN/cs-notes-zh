# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p26 -26-Introduction to Computer Networks _ Week 1 _ -BV1aQmtYZEPr_p26-

Welcome to elements of network simulation。 So this is our first topic on network simulation。

And before we go to network simulation， well be getting to know something basic on computer networks。

 So what is really a computer network， supposeupp if you are a student already。

 you have aware of networking fundamental， you can skip this particular topic。

So that you can consider more on the actual simulations of networking。

So in this we are going to see what is the introduction of computer networks。

 what are the different topologies available， the functions of voice A layers and all these stuff we are going to see。



![](img/9b7177d560e3216c5144458c00c9269d_1.png)

So first thing is in computer networking。 So how data communication really works。

 So what is the data communication here is usually center will be sending data to the receiver。

 and this is the medium。 So it could be wired it could be wireless。



![](img/9b7177d560e3216c5144458c00c9269d_3.png)

And it could be。C， it could be any medium。 So that's how this medium the sender and receiver uses this medium。

 and mostly they can send messages。 And we have protocol。

 So one what basis what protocol the send and receiver is using。

 So protocol means set of rules and regulations and semantics。

 That's what a protocol usually will be heavy。So this data communication。

Is the fundamental of networking。 So how aer a source and their destination knows can exchange packages between them。



![](img/9b7177d560e3216c5144458c00c9269d_5.png)

![](img/9b7177d560e3216c5144458c00c9269d_6.png)

So what are the different components here is message。Sender。



![](img/9b7177d560e3216c5144458c00c9269d_8.png)

Receivever trans medium and protocol。 So these are the five things that this data communication。

 So message means the message is information to be communicated。

 popular forms of information or text numbers， pictures， audio video。

 So that is what the actual message center can send it to the receiver send is one。

 the device that sends the data message It can be a computer telephone radio camera anything receiver is the receiver is a device that receive the message。

 So one who receives's the receiver and trans medium already told you that what kind of trans medium it is sometimes it could be wireless will be wired。

 cellular in case of wired what kind of wire network ethernet or fiber optical cable or or twist or whatever。

 So even radio waves。 That's what in wireless。Protocol means a protocol is a set of rules that govern the data communications。

 It representss an argument between the communicating devices。

 It's an agreement between communicating devices without a protocol。

 two devices may be connected but not communicating。

 So that's what here they may not communicate to each other， but they can able to get connect。



![](img/9b7177d560e3216c5144458c00c9269d_10.png)

So what are the different directions of data So this is a very basic fundamentals that everyone will be aware of So we have three modes of direction of data one thing is simple。

Half duplex and full duplex。So simplex means only one side of communication。

 the other side is not possible。 So for good example is in the mainframe computers data of direction will be only in one direction。

 So this reverse direction is not possible。 So that's why we call this as a simplex communication。

 only simple communication， only on one side of data。

The other variant in half duplexes at any point about a given insert of time only one say communication is possible after the communication is received there is another undo next time duration the direction of data will be different so time number one this message time number two this message So at a given insert of time both packets cannot be traed so that is what we call this half duplex。

Full duplex in the sense that the source on the destination they can exchange packets in a given instant of time both can able to communicate at the same point of time。

 So that is what the direction of data thats full duplex。

 So full duplex half duplex and simpleplex these are the three directions of data at source one can send it to the destination。



![](img/9b7177d560e3216c5144458c00c9269d_12.png)

So now we will come to the topology。 So topology means it is a。

Geome presentation of the relationship between all the links and the notess。So thats a topology。

 So how how the set of network nodes can be connected together。

 So that's what we differentiate on topology。 So there are four kinds of topology here， mesh。



![](img/9b7177d560e3216c5144458c00c9269d_14.png)

Start。Bus and drink so there are four kinds of topology so mesh topology， start topology。

 bus topology and ring topology， so we will consider one by one。



![](img/9b7177d560e3216c5144458c00c9269d_16.png)

![](img/9b7177d560e3216c5144458c00c9269d_17.png)

So in a mesh topology， you can see this station number one here。 So this station station。

 So there are totally five stations they are just connecting to each other。

 So this station one is connected to here and this is connected。 this is connected this is connected。

 this is connected and from these two and these two。

 So that means every node have a connection to the other node。 So you， for example， if you take。



![](img/9b7177d560e3216c5144458c00c9269d_19.png)

If you take this node。For example，1，2，3，4。 So this station have get an incoming connection of 4。

 this not 1，2，3，4。 And this also 1，2，3，4。 So this is also 1，2，3，4。 This also 1，2，3。

4 completely mesh So that been set。 So each station will have four input links。

 So there are totally fine notes。 a excludinging that corresponding not every other link will be connected there。

 So in mesh topology。 every device has a dedicated point to point link to every other device。

 This link carries traffic only between two devices it connects duplex mode。

 So it generally uses duplex mode。 So duplex means both way communication is possible。

 So there is a mesh topology。

![](img/9b7177d560e3216c5144458c00c9269d_21.png)

Start apology means we have a hub or a switch。 We call it as a hub or a switch。

So like most of the campus networking。 so even in our university， the campus networking。

 most of them are connected to the hub in every laboratory we have a hubber switch in in one corner of this room。

 in all the computers are connected to that particular hub。

 okay So here you can see one station connected here， another station another station or station。

 So whenever this station want to send a packet。 So the data goes here from there it comes back here is how the way the connection works。

 So even from one station， another station， all the records happens via this hub。

 So that's what in start topology， Each device has a dedicated point to point link only to a center controller called hub。

 the controller acts as an exchange。 If one device wants to send data to another。

 it sends a data to the controller， which then relates the data to another connected device。

 So everything via happens via switch the control。

![](img/9b7177d560e3216c5144458c00c9269d_23.png)

Third thing is bus topology。 So you can see the bus topology。 bus topology is multipoint。

 So that means you can see there's a tap here。 and there's one there is one tap here。

 and there is a cable end。 and there is a cable。 So the nodes are connected like this on a bus。

 So that means a common group of wires will be there。

 Each and every network used in every node will be to a particular bus One long cable access a backboard to the link all the devices the network nodes are connected by bus cable by drop line and taps。

 So that means at each every tap station is connected via drop line。So this one bus topology。

 So bus topologies are almost more or less， like。Start aology， star uses a hub。

 whereas this uses a8 cable， simple cable。 So that's how this bus toppology works out。



![](img/9b7177d560e3216c5144458c00c9269d_25.png)

So the ring topologies is is connected down a ring So in ring topology each device has a point to1 connection with only the two devices on either side of it you can see there is a station here and this station this station connects here so there is a repeater here So this tool will be conducted on a bus something like this on but this station this is connected here or this is connected here。

So a signal is passed along a ring in one direction from device to device until it is destination。

 So the ring top are very very much helpful for。F tolerancele。

 So if any one of the particular station get fail so you can still be able to find out the nearby stations and then it can be able to transmit the data。

 So ring tops are very advantages in high internet working。 So that's what this ring topology。



![](img/9b7177d560e3216c5144458c00c9269d_27.png)

So now in this topic， so there's questions for the learnerers what kind of network does our V network follow So in V what kind of network it follows So please have this questions for you So we'll have a discussion forum you can discuss about these questions and this also for thought provoking questions so that you can really understand what really happens inside the network What apology does the broadband network follow So if you have a broadband connection in your home what kind of network those kind of broad network follow So either you can。

Check your broadband router by getting the information or you can ask your ISP Internet service provider for what kind of network they have been following。

Okay， thanks listeners and thanks learners So this is a first basic topic So if you are not if you are already comfortable with computer networking so you can skip this particular slide。

So thanks for watching。

![](img/9b7177d560e3216c5144458c00c9269d_29.png)