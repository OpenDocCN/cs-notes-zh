# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p16 -16-3.2 Transport layer multiplexing and demultiplexing.zh_en -BV1UMtueiEaA_p16-

Let's continue our study of the transport layer here by looking at the issues of multiplexing and demxing Now these actually happen in all layers of the protocol stack but we're going to consider them here in the context of the transport layer here's how to think about demxing think of an internet host it's got datagrams that are arriving these datagrams have payloads that are bound for different applications or possibly to different protocols running in that host the process by which those payloads are directed to the appropriate application or the appropriate protocol running in that host that's the issue of demxing multipleings is essentially the inverse of that we learned in chapter 2 for example。

 that many applications may be sending down through multiple sockets their application messages to TCP TCP is going to be taking those messages and then funneling them down into into IP。

That's the process of multiplexing Now again， we're going to look at this primarily in the context of TCP and UDP。

 but again， this is a more general topic that occurs in all layers of the protocol stack here's the setting。

In this scenario we've got an HTTP server in the middle here and this HTTP server is going to be sending HtT messages over to the client over on the lefthand side Now of course this client has many applications running。

 we see a Skype application and Netflix application and of course we've got an HTTP web browser there and so the question we want to ask ourselves is how among all those applications when a message is sent from the server to the client that that information is actually demplex up to the web browser and not to any of the other applications running on the client。

And we also have to think about demplexing at the server where multiple clients may be sending HGTP messages back to this server。

 these messages may need to be demplexed up to different processes at the server。

 each of which are responsible for communicating back to the clients， how is that done？

While we're all familiar with multipleing and demxing from things that happen in our daily lives。

 highways are a good example of that。 Many cases we have multiple on ramps where cars are being multipleed on to the highway and of course at big interchanges where demed off off of a highway onto a number of different possible exit ramps。

 maybe even better example， is what happens when we get to an airport， for example。

 you arrive and immediately， well， if you have business class， you go here economy class。

 you go over here， when you get to precheck， if you have TSA precheck you go to the left otherwise you go to the right and once you get to the gate。

 of course there's a place where you line up for premium class service and there are multiple coach class service lines as well that notion of being directed being split and being directed to a particular class of service that's sort of at the very core of what demxing is all about so。

Let's continue on here and let's actually look at this now in an internet context， of course。

 and take a look at what happens in UDP。 So here we have our threehost scenario again。

 And in this particular example， we're actually showing the processes that are going to be communicating as well as those sockets the little yellow rectangles there with the white in the middle showing where buffers actually are And so in this example P1 and P3 are going to be communicating in P2 and P4 are going to be communicating。

 Let's see how that's done。 Well， on the multipleing side。 If we look at the host in the center。

 we see that P1 and P2 are going to be sending down through their sockets through the transport layer。

 transport layer going to have to multiplex data coming in from P1 and P2。 take that data。

 put it into segments and add information into the transport header that's going to be used for later demxing。

Now， when packets and datagrams are actually received at that host in the center。

 we're going to have to perform the dual operation there， the demxing operation。

 and in that case the transport layer is going to be using header information to deliver the contents of the received segments up to the correct socket。

Okay so let's take a deeper dive into how demexing works。

 remember when a host receives an IP datagram， each datagram has a source IP address。

 the IP address of the center of the datagram it's also got a destination IP address and that's actually the host where we're actually doing this processing Each datagram also carries one transport layer segment and in the transport layer segment。

 There's a header and we're going to be interested in two fields within the header of the transport layer segment for our purposes here and that's the source port number and the destination port number and the host is going to use the IP addresses and the port numbers to direct the segment to the appropriate socket and we're going to see that this is a little bit different in TCP than it is from UDP UDP is simpler so let's start there。

Okay， in order to now understand how UDP connectionless de multiing works。

 We're gonna have to remember a little bit about what we learned in Chaer 2。 And remember there。

 when we were looking at socket programming， you recall that when creating a socket。

 an application programmer has to specify a host local port number。 Here's a code fragment here。

 where the datagram socket is being created and there's a host local port number，1，2，5，3。

4 that's specified。Now when creating a data that's actually going to now be sent into a socket。

 we have to specify where that datagram is destined and there we specify the destination IP address and the destination port number。

 not the local host port number now over on the receiving side when the receiving host receives the UDP segment it's going to check the destination port number and direct the UDP segment to that socket associated with that port number that's the act of de multiplexing there。

Now you may think for a second and saying well wait a second。

 we can have multiple clients sending datagrams to the same UDP port number at a destination if that happens the UDP datagrams with the same destination port number。

 even though they're coming from different source IP addresses and maybe different source port numbers。

 these are going to be directed to the same socket at the receiving host because that demxing only happens in the case of UDP on the basis of the destination port number。

Let's now take a look at an example of UDP d multiplexing。

 We've got our three hosts as usual on the left hand side， we have process P3。

 which has created a datagram socket with local port number 9157 on the right hand side we have process P4 which is created a datagram socket with a local port number5775 and in the middle we've got process p1 which has a datagram socket with an associated port number of 6428 Now P1 and P3 will be communicating with each other P1 and p will be communicating with each other In the first example here we see datagrams being exchanged from P1 to p3 and from P1 back to P3 Let's look at what p1 is sending to P3 and in particular focus here on the source port number and the destination port number of the datagram shown at the bottom of the figure here。

 the source port number9157 is the。Port number associated with the socket being used by the sender by the source the destination。

 well， that's being destined to port 6428， which is the port number associated with the datagram socket of processed P1 in the middle Now what happens when P1 replies back to P3 Well we learned in chapter 2 that the destination port number 9157 that was taken from the source port number from the datagram at the bottom the arriving datagram to which the return datagram is reply so we see the destination port of the uppermost of the two datagrams on the left has a destination port number of 9157 and the source port number of 64 to8 which again is the port number associated with the datagram socket4 P1。

Well， on the right hand side we don't specify what the destination and source port numbers are。

 see if you can figure that out for yourselves， it's really the mirror of what's happening on the left hand side。

Well， that's how multiplexing and demxing happens in UDP。

 now let's take a look at TCP where we'll see that the decisions are a little bit more complicated。

Well in the case of UDP we saw that demplexing was really pretty simple in the case of TCP it's connection oriented。

 That means we've got a sending side and a receiving side and how are we going to identify the sender and the receiver Well certainly on the basis of the IP address but also on the basis of the sending port number and the receiving port number So a TCP socket when we instantiate a TCP socket it's going to be identified by a4tupple the source IP address。

 the source port number that's on the sending side。

 the destination IP address and the destination port number that's going to be on the receiving side of the connection Now so when we do demplexing the receiver is going to use all four values in this fourtupple to direct a segment to the appropriate socket We'll look at an example in just a second let's wrap up here just by noting that a server can have many simultaneous TCP sockets each socket。

Is going to be identified by its own4 tuple， and each socket is going to be associated with a different connecting client client process。

Our TCP deplexing example here has again our familiar three hostss， except this time in the center。

 we've got an Apache HTTP server that's going to be exchanging HtTP messages over TCP with the host on the left hand side which has IP address A or the host on the right hand side which has IP address C and the address of the HTTP server is B。

 Let's take a look now at the communication that's happening between process P3 running on host A on the left hand side and process P4 running in the Apache server in a datagram flowing from left to right。

 we see the source IP address associated with that datagram of course is a that's the send of the datagram。

 the IP address of a and the source port number is 9157 That's actually the port number。

 the local port number associated with the socket that P3 has created。

What's in the destination fields there well the destination IP address is B。

 that's the IP address of the Apache server and the port number is 80 and you may recall that 80 is the port number associated with HTTP service。

Let's now look at a reply coming back from P4 back to P3 Here we see the source IP address is B。

 The port number is 80。 The destination， of course。

 is IP address A and the destination port number is 9157 we're also showing here on the righthand side two datagrams that are flowing from host C to the HttP server。

 the Apache web server in the middle here and so take a look at the field values there。

 hopefully those are going make make sense to you。 The one thing we really want to highlight here though is let's look at the three datagrams that are all arriving to the HtTP server in the middle notice that the destination port number in all three of these datagrams here is 80 that's absolutely critical。

 remember with UDP we would have demplex just on the basis of that destination port ID in the case of TCP because it's connection oriented remember we。

On the4 tuple and each of those four tus of those three messages arriving are unique。

 so those are going to be d multiplex correctly to P4， p5 and P6。

Well that wraps up our study of multiplexing and deming so let's just recap what we learned。

 We learned that that process of demplexing at the transport layer is really that question of deciding what is the socket to which we need to take the segment payload and then deliver into that socket in the case of multiplexing。

 we saw that both TCP and UDP need to be able to take data from multiple sockets and then deliver that put that in segments and then deliver that down to the network layer below it We saw that in the case of UDP that demplexing is made on the basis of simply the destination port number and we saw that in TCP it's done on the basis of a4tuupple and then finally we learn that multiplexing and Dmxing happens in all layers of the protocol stack so we're going to see this again when we get to the network layer and also when we get to the link layer。



![](img/e90eac65eb40309bbeab16f6597b02cc_1.png)

![](img/e90eac65eb40309bbeab16f6597b02cc_2.png)