# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p26 P26 Write your own Operating System A05： User Datagram Protocol (UDP) -BV1BDBEByEBY_p26-

Hello and welcome to the fifth Appendix to the tutorial on writingt Your own operating System。Now。

 then in this fifth appendix， I want to talk about the user datagram protocol UDP。嗯。

UDP is quite similar to TCP in its use， but it has some differences。In particular。

 TCP does a lot of error recovery and。Yes， make sure that everything you send arrives at the recipient and in the correct order and all that stuff。

 And UDP just doesn't do that。 And UDP， you send data and。It might arrive。 It might not arrive。

 It might arrive in the wrong order， but。Yeah， but UDP is faster than TCP。And that is why， yeah。

 for example， in。In voice over AP video conferencing。And multimedia streaming。

 you usually use UDP because as I've said it's faster。 and yeah， what happens if a packet is dropped。

 Yeah then then maybe the screen。Won't you know， you you'll have a little bit or maybe you get these。

These strange pixel errors for a short time， or maybe maybe parts of the image are。

In a wrong position for one frame or something。 but that's really not。Not so bad。

 so in the voice of IP system， when you send critical data like an email。

 you really shouldn't use UDP， you know because。If you lose a packet which contains。

 maybe for example， the word， a word not。Okay， so you want to send the message。呃。Don't attack。

And the packet that contains the dont gets dropped。

 and then the recipient gets the message attack okay and now you've started a war。Okay。

 so that's why you really should use TCP and not UDP for。For discrete data， but you can use UDP。

For dense data。Okay。Yeah， let's take a look back。I want to talk a little bit about the Ausie layer model。

 I'm sure you've heard about that， if you。If you have comes this far。The Ausie layer model。

How many words， I think， seven layers。😔，Yeah， seven day。And the lowest layer is physical。

So this basically， this is called a network stack where you have different systems communicating。

 every system is only communicating with the next。Layer in the。In this stack。

 the physical layer is the real hardware。Okay。When you have the data link layout。

That is our ethernet frame。Class。When you have a network layout。That's our IPV4 class。

And then comes the transport layer。嗯。And yeah， TCP and UDP are both transport layers， Okay， so。

These three layers we already have。 Now we want at least one transport layer。And then。On top of that。

Yeah you。Not directly， but then you have the session layer。Presentation and application。没。

Movinging on。So the transport layer， TCP or UDP is really the last thing we will be looking at。

Because everything above that is really not part of an operating system， so。嗯。

Everything above that is the business of the application programs， for example。

A web browser maintains a session in the communication with a web server， you know。

And the presentation layer。嗯。Its the rendering engine and the application is in the program that really shows you the data and。

Gives you the buttons that you can click and all the stuff。So。So yeah。So when we have UDP。

 then we have。Some networks deck and yeah I think I will make a short video about TCP where I will talk a little bit about the differences between TCP and UDP but。

TCP is just too complicated to really deal with this inside。So videos。So so yeah。Today。

We'll implement UDP and UDP is not so complicated。So again， if you look at the Wikipedia page。

 here's， again， the。A header for the protocol。 and yeah this is a very simple header compared to IPV4。

 for example。嗯。You basically just have a source port and destination port。So an application。

Might say， hey， I want to open a pod1，2，3，4。Maybe I want to listen on that part。

 or I want to connect to a different machine on that part。But yeah， that's。

 that's already an application， something that would run in the user space， right， So that would be。

Not our， not what we are doing here so。So you just need to offer a way for an application to say。

 hey， I want to communicate over this part okay。Okay， so。So， the UDP。

Protocol basically is a multiplexa and de multixa again， which just looks at a certain。诶。

A certain field in this header， and depending on that， passes the data onto some other application。O。

And this isn't something fixed， like。We did before。

 you know before we had this ESnetframe and we hard coded the connection to ARP IPV4。

 we hard coded the connection between IPV4 and ICMP will hard code the connection between IPV4 and UDP but these connections won't be hard coded in the end you know an application will just be able to say。

 hey I want to be connected to that。O。没。

![](img/43a45d5a1d463c5ee41587e1bc6c7844_1.png)

うん。Oh。So what do we have， source part， destination part length and the checkum。等下。Yeah。Okay。

 so we were。Have a structure for this header again。Yeah。So source port。

 destination port length and check some。Yeah。Yeah。So when an application wants to connect to some other machine。

Then。This user datagram protocol object will create something called a socket。Yeah。Yeah。Yeah。

So the user data Gr protocol will have。Yeah， just。Again。An area of these sockets。

And since we have 16 bit part numbers。I will。Initializes。 I will have 65000 copies of that。 I mean。

65000 is a lot。 but I think nowadays， it's we can afford that。

Although I'm going to go down into the loader。t S and increase our stack to4 megabytes now。

Because we already have。A lot of space for the Enet frame handlers。You know。

 that was also a 16 bit interger。Yeah。So。So the user data Gr protocol will get an IPV form。Packet。

Yeah。So， we will override。This method here。😔，Okay。我。Okay。何？Yeah。Yeah。

And then the socket will basically。Just maintain the information about the connection。Basically。

 just the parts and。嗯。And the I addresses。Yeah。And the socket is then supposed to pass the data it gets to。

A user datagram protocol handler。Yeah。Yeah。Yeah。Okay， such a handler。

 yeah you would then derive your applications from this handler and connect them to the user datagram protocol using such a socket。

な。Okay。Yeah。Okay， this is all we have to do for the。I装。What about a socket。Yeah。

So the user datagram protocol object will give the message to the socket and the socket will give it to the handle okay。

Thank。So equipment also asend。And I'm going to put。😔，A methodod wide disconnect。😔，So when we have。

When we have a socket， we can disconnect it like this。😔。

But this will basically just call the method on the back end， the user Datagram protocol。Yeah。Yeah。

Then we'll have a function that。Gives us such a socket。う。F given me。I P and port。

Then a disconnect and ascent。看完了。我た。😔，Disconnect， we already have。Defined。Connect。

 disconnect and send。嗯。い。う。Okay， so this is going to be our classes。😔，Right。

So the handlers don't too much as usual in the default behavior。😔。

So the socket will basically always call up the corresponding method on the back end。😔，没什东西。Yeah。う。

And when it gets data， it just passes it to its handler。😔，So。Yeah。What。UDP is 0 x11， right？

So IV4 is supposed to give it data with。Protocol 17。0 x out of them。Okay。

 so this is basically just if you get data from the application， you pass it to the back end。

 if you get data from the back end， you pass it to the application。嗯。So now implement。

 and the application is。Not our business， although we， of course。

 we will have a little example application， but。But yeah。

 the interesting part is this stuff here with the connect disconnect。Sent。Right， of course。

 I will set all the。Are these sockets here to0 at first。Yeah。Okay， so。When we receive data from IPV4。

As usual， we'll just put such a header over it。は。对。谢。也也。By the way。

 the UDP is not supposed to change the data and send it back because it's。

It's not supposed to see the data as individual packets， it's supposed to see it as a stream。

And not know where a。Where the gaps are between the packets。Therefore。

 we must always return falses in this method。嗯。やす。Okay。Yeah。Yeah。こ感。Okay。Oh yeah。

We cannot do it that easily。嗯。Because you can have multiple connections on the same part。If you。

 if the。If the IP addresses are different。But I'll leave the size of the sockets。The same。い。Yeah。So。

Instead， we will have non sockets。😔，So we will not select the socket directly based on the part。

 We will iterate over it。Yeah。So we we get data and now we iterate over all the sockets that we have and check if the。

IfThe current socket is a socket that is supposed to get this message。So， if so。Destimation。Part。

So if the destination part is equal to our port。So we have gotten a message。

Which has a source port and a destination port。So if the destination part is our part。And。

So if the local part of the socket。😔，Equals。Destination part of the message。And。

So remote part is equal to the。Messages sourceport。😔，Yeah， this looks good。

So if the message is supposed to go to the local part of the socket。On the local I P。

And it's coming from。The remote machine was a remote part that this socket is handling。

Then this is a socket。We are looking for。And then we can terminate the loop。😔。

So if we have found a socket。Yeah， then we just pass it the data。The data， and we drop off。

 of course， header。Okay。So we trip off。The header and pass just the payload to the next to the socket。

 which then。Hassses it to its hand life if any， if there is one。Okay， when we want to connect。😔。

We will create。😔，We will create a new socket。So we create a new socket。😔，Yeah。Yeah。

Then we will put it in the list。Okay。Yeah。But first， we need to configure it。い？没。So。Yeah。

So the remote part is a part that we want to connect to。The remote I is the IP that we connect to。

 you know the。The were values we get from the parameters。さ。Yeah。Okay。ど？Okay。Do't this remote part。😔。

Local address。

![](img/43a45d5a1d463c5ee41587e1bc6c7844_3.png)

So what do we set this part to Yeah， the interesting thing is and this is really also the case in TCP。

 This is a nice thing the remote port and local port don't have to match so。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_5.png)

You give me a part on the。On the remote machine。But on my machine， I can just use any port I want。

What I'm going to do is， I will。I will just use。😔，Such an interte。

And I think I should make that static， probably。😔，Yeah， help。

No actually I don't have to make it static so。😔，Yeah， I'll just set this to。Something。Like 1024。嗯。

You know， because。The first 1024 parts are reserved。So。We'll start at 1024， and then just use this。

Like this。哦。Okay， but。These must be in big Indian， again。Okay。Yeah。这。嗯。Yeah。Yeah。嗯。Yeah。不。对没。嗯不。Yeah。

不。Okay， so now they are in big Indian。And that should。

Be everything we need to do for the connect method。F子。Disconnect。Yeah， we basically just。

Look for the。For the socket in our list of sockets。う。And if we find it。😔，We just。

We just remove it from the list。Yeah。So now we just take the last socket from our list and。

And what if there are no other sockets left？😔，嗯。Yeah， but that shouldnt shouldn't actually matter。

 I think so。So if this is the last socket， then this overrs itself。

This overrs socketss eye with itself。 but since we decrease numb sockets。

 then it's outside the legal range， so。Yeah。Okay， and then we have to freeze the memory。😔。

And break the loop。Yeah。Okay， we look for the socket。 if we find it， we。

We overwrite it with the last element from the list。And。😔，Then decrease number sockets first。😔，ok这样。

This looks good， I think。Okay， what do we have to do if we want to send data。Yeah。对。Yes。

So this is the length of the data that we want to send plus a new header。Yeah。Yeah。

Then we allocate the RE for that。没。Yeah。And put a pointer to。To the head on。On that。Okay。

 so then we set。The source port number。To the sockets's local part。Okay。Yeah。No。

 we don't have IP in now。😔，Sace part， destination part。嗯。The total length。

It's just what we just allocated， so total length。Then we copy the the data。Yeah。Yeah。Yeah。Okay。

 so now we copied the data。Into the new message。😔，Now， the last thing we have to set。This check some。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_7.png)

And。The computation of this checkum is really crazy，It involves。诶。

Something called a puo header and which contains some data from the IPV4 header。

 which actually absolutely doesn't belong in there。嗯。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_9.png)

But the good thing is。UDP doesn't require this， you are allowed to set this just to zero so。Just。

 this just deactivates the error tracking。ok。So the check sum is just set to zero and then。

Then we pass it to the sent method of the base class。😔，Just one。So which IP do we send it to？😔。

To the remote IP。And what do we send Well the。打说。And yeah， the full buffer。

 including the header buffer2 is only a payload without the header。And both together have length。

 total length。Yeah， this should be it。😔，嗯。In the end， of course， we need to free。😔，The memory， again。

So we have。I located here。And this really should be it， I think。😔，So。Was more code than I expected。

 but okay。Yeah。こも？Okay。Yeah。Okay。So， now we have。Now we have this UTP handler。😔，So let's see I want。

Yeah。So I want to connect to the gateway IP。😔，One part，1，2 3，4。Yeah。Yeah。I knew it。

The total length here needs to be in big Indian。I mean， these parts already have been。Set to Big end。

嗯啊。This needs to be set to big Indian， also。Yeah。嗯。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_11.png)

Okay， let's see。Yeah。Yeah。Actually， before I start。

 you know the thing directly tries to connect to the。To the host machine， so to my laptop here。嗯。

So I just want to open。this。I this part already before。😔。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_13.png)

Before I run this。the source I and destination I。Of course， they aren't in the。In the header。

 they are given from from the parameters。

![](img/43a45d5a1d463c5ee41587e1bc6c7844_15.png)

![](img/43a45d5a1d463c5ee41587e1bc6c7844_16.png)

Yeah。は。Yeah。Okay。So we need to get the IP address。😔，没常。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_18.png)

Okay。

![](img/43a45d5a1d463c5ee41587e1bc6c7844_20.png)

Hey， what do you say， what do you say， what do you say？So， this thing has really。嗯。

Sent something outside of the machine to the outside world。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_22.png)

So this is really good。😊，ButLet me。Try。What happens。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_24.png)

So leave。TheUDP。H装。Yeah， in the in the kernel， I will just basically do the same thing I did。

Way back then with a keyboard enterer。So， in here。When I get data， I'll just。Ft， every。

Every character one by one。 Okay， it's a bit insane but。啊。Otherwise。

 we would be accessing data outside of this。 I mean， I could just set。Data plus size to back slash 0。

 and then print the whole data， but。That would possibly remove the last character。 And if I， if I。

Set the next character to backstlash， and I might break。呃。Memory manager。So I'm not going to do that。

 I'm going to do it like this。😔，有。So this is just supposed to。😔。

Se the handler of the socket to this handler。😔，Yeah。听们。So， let's see。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_26.png)

So let's cut this running。😔，I get the message again。Yeah。And yeah， look at that。

 I have received the answer from the。From the net cut server here。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_28.png)

ふえ。Okay， so the。The data can go in both directions。 This is great。嗯。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_30.png)

But， I haven't。I haven't defined a way to。Connect。To do anything in listening mode。 But yeah。

 I think this video is long enough now， so。I mean呃。

It should be relatively clear what to do and how you would。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_32.png)

Basically。You would have to say something like UDP socket。So you would have to create a UDP socket。

 not with connect， but with listen。And was only an。The port number。And。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_34.png)

人。Yeah， yet it should be set。 You would need something like a booleion telling you that it is listening。

 So when you get data on that part and the。You know whats。Let's coat this。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_36.png)

Yeah。这个。ふ。一个。Yeah。嗯。继是。这对。Yeah。So， we create。Socket again。嗯。A remote part and local part。

 remote part and remote I are not set yet。So we listen on this part， this is a local part then。😔。

Okay。And then when we receive data。So if our local part is the destination part of the message。

 our local IP is a destination IP of the message。And the socket is listening。😔，Then， we can。

Then we can set the socket and this socket。Is selected。いよ？Now it's not listening anymore。

 And we set its remote port and IP。嗯。So。嗯。Yes。Saying， listen， if we listen on a part， that means。

We create a socket in a listening mode。We don't set its remote port and remote IP。 We do that when。

We just take the remote part and remote IP from the first connection that tries to send something to us。

 And then we also set this listening to false， because then we are actually connected。

So let's look what。😔，Okay， so this should then open a socket top。😔，Yeah。

 open a socket and wait for data。

![](img/43a45d5a1d463c5ee41587e1bc6c7844_38.png)

![](img/43a45d5a1d463c5ee41587e1bc6c7844_39.png)

Now let's see。😔，I'm going into the network configuration， and set。A part forward rule。ForUDP。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_41.png)

Okay， now we have told virtual box to accept。Incoming connections。 and forward them to。

Our operating system。Did I report the machine。😔。

![](img/43a45d5a1d463c5ee41587e1bc6c7844_43.png)

Okay， so it seems I have connected。😔，Yeah。Yes， so we have opened a server。😔。

We've connected to it from outside and sent data there， Yes， incredible。So。Yeah。

 this was a bit more work than I expected， but。I mean， it's crazy。

 look at what we have achieved in this， I think it's about one hour，15。Now so we've implemented UDP。

A way to connect from inside to the outside， to send data from inside to the outside， receive。

Responses。From the outside and also we have written a UDP server。

 which you can connect to from outside。Using this plot for wedding so。😔。

So a lot of code a little bit longer time than I expected， but really， I think this really paid off。

 So yeah。So this is really enough for today now， I'm actually quite exhausted now。

I think my voice is also a bit hose。啊。Yeah， so yeah， that's enough for today。Yeah， tune in next time。

 next time， as I said， I will talk a little bit about the differences between TCP and UDP。



![](img/43a45d5a1d463c5ee41587e1bc6c7844_45.png)

Although not so I'm not going to implement TCP， just talk about how to implement it。

 but not really show you。

![](img/43a45d5a1d463c5ee41587e1bc6c7844_47.png)

嗯。But yeah， so tune next time， so you don't miss that。

I think it will be really a lot of useful information for implementing in your own TCP。嗯。Yeah。

 don't forget to subscribe so that you don't miss the next video and hit like。

 if you like this video， I really like this video。This is really who。嗯。So yeah。

 see you next time and bye。

![](img/43a45d5a1d463c5ee41587e1bc6c7844_49.png)