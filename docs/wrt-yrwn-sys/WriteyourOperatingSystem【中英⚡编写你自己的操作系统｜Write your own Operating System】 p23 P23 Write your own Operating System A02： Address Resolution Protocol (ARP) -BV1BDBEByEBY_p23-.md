# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p23 P23 Write your own Operating System A02： Address Resolution Protocol (ARP) -BV1BDBEByEBY_p23-

Hello and welcome to the second appendix to the tutorial on writing your own operating system。Now。

 where are we。Le time。We wrote a code for handling ethernet frames。

Which we get from the network driver。嗯。And these frames look like this。

And this is anet frame handler。Checked， well， this this infinite frame for me。

 Does it have the correct。嗯。Meg address， is it my Mac address？A broadcast。And if so。

 it looked at the ether type and would then。Forward this data block to the handler for that ether type。

So。Yeah， but we didn't have any handrs for these E frames。So this is what we are going to do today。

We're going to write a handleler for the ARP because that's quite simple。From。And yeah。

 ARP is really for。For the communication between computers。Yeah。

 when one computer wants to know the IP address of another computer。So。I mean， not only that。

 but that is what we will be using it for again， the。Wikippedia page about this protocol， again。

 is very good。So， here you have， again。A nice description of of how this data structure is built。

Yeah， and an ARP。Data block looks like this。 You get。You get two bytes。Which。

Tell you the hardware type。 Yeah it。I think it's for it tells you。

 is this going through Ethernet or is it going through something else maybe。Wireless La or something。

I don't know， so in our case， this will always be one for Ethernet。But actually this is a2 byte。

Value and it's big Indian encoded。 So this will actually be 0 x 0，1，0，0。The big Indian encoding of。

Of a 2 byte one。Then， we have。Two bytes for the protocol。嗯。Yeah， i mean。嗯。

We already have an information about the protocol， this Ether type， which will be 806。

Hexta disimar 806。But。The protocol that we have here is not。The same as here。So。嗯。This tells us， hey。

 we are talking about IPV4， so this would say 0 x 800。O。So。Here you would have 8006。

 here you would have 800 because we are talking about， I mean， this is an ARP。Message。

 but this message talks about IPV4， which has code 800。And again， this is a big Indian encoded。

 so actually would have 0 x0，0，0，8 in there。嗯。Yes， then you have。Two fields of size 1 byte。

Which tell you the size of the hardware address， so this would be6。Because Mac addresses have size 6。

And here we have four because I P addresses have size 4 B。Okay， so this is a size of。

Of a hardware address。And this is the size of the logical address， and IPV4 address。

And then we have two more bytes。With。A command。So this really tells us what does the sender of this message want from us。

 So does he ask us。What is your IP address or is it a response to our question。

 maybe we have asked him， what is your IP address and this is a response。

And these are actually the only two commands that we will implement here。Okay。Yeah， and。After that。

 you have。6 bys。Four bytes， six bytes， four bytes， which contain。The Mac address of the。嗯 center。

The IP address of the send。The Mac address of the。Destination。So receiver。And the I address of the。

Receiver。Okay， so。This is what we will get。Yeah， of course if the command is， hey。

 tell me your IP address then。This won't be a legal value。

Or maybe if it's if we get it from a broadcast， then this Mac will be。Just a broadcast address。

I mean， we。When we send something back， we will copy this block here because。Yeah。

 we are sending this back to the send of the message。This stuff which set。

So this is the info about the sender， and he becomes a recipient of the answer， of course，U。

But actually。Not all ARP messages have this exact length。 Okay， so the length of the stuff。

Here after does this command。This is actually， this can differ based on these two values。 You know。

 you have。This many bytes here， this many bytes here， this many bitetes here。

 and this many bytes here。O。But we were really hardcoat this to be six and four right？O。😔，Yeah。So。

Yeah， of course， one thing that is left。Right now we have no， I mean， the the ARP。

Class needs to know the IP address of the machine because yeah。

 how do you how would you answer the question for your IP address if you don't know your IP address。

So。So he needs to get the IP address somehow。嗯。But we have。In， in the class for。The network card。

 we had this in it block， and this one had had4 bys for an I P address。

So I think what we will do is we will just tell this class， hey， this is your IP address。

 and he is supposed to ask him and he is supposed to ask him。O。Yeah， that I think makes sense。😔，Yeah。

Yeah。Yeah。Okay。は。Okay。So here in the user frame， we had。This is a frame handleter。😔。

So ARP is going to be。And is a frame handlelum。Yeah。Yeah。So we will have a structure for this。😔。

For such a message。Yeah。Okay。So。You in 6 tea farther。😔，Harware type。Yeah。Yeah。えじ。Protocol address。

 size。Yeah。Which will be far in our cases all the time。😔。

So here we have the Mac address of the sender。Oh， I see this should have。

 should have done this here also， I think。😔，32 bits。So P address。😔。

64 bit for destination Mac address。😔，O。By the way。If you ask yourself。

 why do we have the Mac address here again？I mean。Here we have the Mac address of the destination and of the source。

 But we also have these Mac addresses here and here in the。I that if net frame。Had on。

So you might think， yeah why have them here again， you could just look at these instead。

 but there's a problem。You can。 You cannot do it like this。 You cannot say， well。

 I'll just leave them out and just use them instead， because。

There can be multiple machines between the sender and the source as the sender and the destination。

Okay， so。So when he wants to talk to him。Then his Mac and IP address will be here and his Mac and I will be here。

 but。He will have to send the whole thing to him first， and。When he communicates with him。

 then the source will be his Mac address and the destination， his Mac address。

 not his his Mac address okay。And then when he communicates with him， then。

Then this destination will be his Mac address， and this。The Mac address from him is the source。

 And when he talks to him， then。The source is his Mac address and the destination is his Mac address。

So。So this is really the absolute low level。For the communication between one machine and the next machine through maybe one cable。

 okay， but。Yeah， as I've said， if he wants to know his。

IP or Mac address and he doesn't communicate with him directly then this will always be his Mac address and this will be his Mac address and these can vary between them on the path between them。

So。嗯。Okay。Yeah。By the way。At the end of the last video。

 we had this little error when I ran the code where we got an instantiation error from the memory manager。

Don't worry about that。 that came from。From a problem I was running an old version of the network manager here。

 not the one that I've shown you so。So if you did everything I did in the video。

 then you shouldn't have gotten this error。Yeah。Yeah。发生。Okaym。this back end。

 we need to pass that to the constructor of Ia frame handl。😔，嗯。Now。

 what we have to do is we have to overwride this unEer frame received。😔。

And I will also write something。So we will give this an IP address and big Indian encoding。😔。

And we wanted to。嗯。To request， yet， to send a request。For the Mac address of。This IP address。

And when we receive an answer for that。嗯。Yeah， we will basically really store others in an area。

 I mean， this is this isn't really a great design， but。嗯。Yeah， I'll do it like this。Yeah。

So maybe have something like 128。😔，IP addresses。Yeah。So we request a mega address for an IP address。

And when we get an answer。Then this is going into this unEa frame received。

Method and there we were star。Its。And。Then we'll have a method that。Looks for an entry in that cache。

O。Okay， so the is a frame hand learn。The ES frame provider， as I said， is supposed to give us an。

IP address。😔，Yeah。Yeah。Which it is supposed to get from。😔，So drive off。And the driver will get this。

I mean， this is。Yeah， you could set get this from an dynamic host client protocol， the HCP。

You could get this from a DHCP server， but I don't know I'm not that familiar with DHCP。

So we will set this IP address manually。You know， like you did it in the old days。

When you configured your network manually。Yeah。Yeah。Okay。Yeah。Okay。扫描为。

So now we have a way to get the IP address。是。Okay， so the constructor， we call it a base constructor。

😔，Neither frame handlers get a backend and an ease type。😔，The the ether type was 0x806。O。

And here we set this nonc entries to 0。あ。Okay， so in this reading something from the cache。

 we will just iterate through the cache。 And if we find something， return it and otherwise。

We will return0。嗯。Yeah。对。Yeah。Yeah。Thank。Yeah。嗯。Yeah。O。Okay， so like this。

 we can read something from the cache。Of course， we need a way to。Write something into it， also。Okay。

 when we want to request a Mac address， well just instantiate。Such a message block on the。Stick。

So big Indian encoding of number one。気持ち？We're talking about IPV4。😔，好。

So an address size for protocol。IPV4 is。4 bytes long。Oh， what have I done？😔。

I forgot the Ram for the command。😔，Okay， so。We set this to the command。😔，One， again。

 big Indian encoding， So 0 x 0，1，0，0。Yeah。嗯。Do we have a method to get the address from？😔，No。

 we don't。So， the ease frame provider can。Ask for。嗯。Here the AMD sort network trip back end。

Now we can ask the ES frame。Pro up。Yeah。Very。So we set the source。😔，For this request。😔，嗯。This is us。

Then we set this to the broadcast address。😔，嗯。O。So now this message is finished and we can send it。😔。

そして。Yeah。So we sent this to the broadcast address。😔，Right。嗯。We have inheritance。

This send message here where we don't have to specify the ES type manually。😔，So， we don't have to。

We don't have to send this to the back end manually we just call our own。Sent method。

Which we have inherited。So the buffer is just the address of this ARP。Message。And the size is。

Size of。Address resolution， Procol message。😔，是。Okay， so this is how we request。

Someone else's Mac address。So we say we want to talk to this machine。

 but we don't know its Me address yet， so we sent a request for that。O， now我啊。😔，Okay， when we。

 when we receive。Such。A message。Yeah we cast it to the message type first。😔，That's relatively normal。

😔，But we should only do this if the size is large enough。Yeah。Okay， so now we just。

Yeah now we can check these values here。So if it's an enetit method。😔，Then。Re trick。In the end。

 if nothing else happens， we return false， by the way。嗯。So the default behavior is to。

To not send anything back。Okay。Yeah。So only in these cases。😔，Can we do anything with it？啱。

So if we can do anything with it。I mean， if we understand this message and it is for us。I mean。

 if it's not for us， then we might look into our cash for the requested。I P address， and answer it。

Answer the request with our cache entry。Maybe so somebody wants to know the Mac address of some machine and if we know that Mac address。

 we could answer it。But no in this case， I'm not going to do anything。OrOtherwise。

 we might want to to pass the request on to some other machine， but。Yeah。

 but that would be the behavior of a gateway and。I mean， we are not making a gateway right now。

 right。So if the message is for us and we understand it， then。Yeah， then we look。

 what is the command。Okay， in case， so in this case， 0 x200。

 this means we have gotten a response to a request that we have made。And then we would just insert。

The response into our cache。Okay， so in this case。We just put this， although this is a bit I mean。

If we get a response for an IP address that we haven't asked for。

Maybe it's not a good idea to store it somewhere。嗯。But， I mean， these。

 these messages are unreliable anyways。 So if we ask the the network， hey。

 what's the Mac address of this and that I， someone might answer with his own Mac address。

 even though it's not his I。 So if you ask maybe for the I of。Google dot com。

 and someone answers with his own。Mac address， then effectively you will be talking to him whenever you make a Google request so and he behind that he might talk to Google and answer your requests。

 but he might read and what you are doing and he might change the results and。Yeah。

 so this is really a point where a man in the middle attack can happen。

Through something called ARPpoing。 But yeah， I think this is just unreliable。

 I don't think there's really something you can do against it because yeah。

 you are getting some data and you just cannot validate that where it came from。

 maybe if you did something like。啊。Like communication through SL。

 But then you need the private key of the。Of the other machine and not private。

 a public key of the other machine and。I think I'm afraid we have no other choice than to trust this message for now。

Okay， so。嗯。If。We are asked for our Mac address。Yeah。Then。We change the command into。A response。

You know， because we will be sending it back in the end。By returning true。So。

We change the command into。0ero x 200。Now we turns up。😔，Send her into the recipient。う。And yeah。

The new sources。😔，It's gonna be our I P address and our Mac address。Okay。あ。Yeah。

 this should really do everything we need at this point。😔，So。um。

One more method that I want to include。So， here we can。Request a Mac address。And then later。

 it will be put into the cache if we are lucky。And after it's put in the cache。

 we can get it from Mac get Mac from cash。But I want to have something like。

Like a method that sends a request waits for an answer and then returns。嗯。Then， returns the。嗯。

The Mac address。So。So first， we look if we already have the make address in our cache。If not。

Then will you request it？Yeah。So this is what we get if the Mac isn't in the cache。Okay。

 so this isn't really safe because if the machine isn't even connected。

 then of course you will never get an answer to this request。And then。

You will never get an entry in the cache。And then this loop will never have。Terminate。

So we should have some way of finding out if of having some time out here， but。Yeah。

 I'll leave it like this for now。😔，Okay， so I'm gonna put it in the make file。Yeah。And in the corner。

Yeah。So。Yeah， I think this was。An IP address that virtual box will accept 1002 15， I think。

Then the gateway。😔，This。10，0，2，2。Okay， now。So our own IP address。Again， I'm big Indian。Then IP3， IP2。

😔，1？Okay， so this is our own IP address。So now we have told the network car that this is our AP。😔。

So that the other。Layers can request it from there。Yeah。

And the address resolution protocol is attached to the Enet frame handler。😔，Here， we attach。

Eth0it frame to the driver and now we attach the address resolution protocol to the e0 frame。ok。Yeah。

And the gateway IP。😔，Yeah， so。So now we have something that in theory。

 should really be able to talk to the network。knowBefore we could just send some stupid data that didn't mean anything。

Everything in Vibox just。So the Gateway inver box just discarded these messages because it couldn't do anything with them。

But I'm really interested。😔，What happens now because？😔，I mean。

 we have really a lot of code for the driver， for the Ethernet frame and now also for the ARP。

And most of this we couldn't test so far， so this is really is a test for all three of these things and I'm a bit scared that this might not work。

嗯。So， I'm gonna do something like。Okay， we can get an answer only after the interrupts are activated。

 you know， because when we get an answer。This is done through an interrupt handr。So。

I'm going to request。😔，给away I p。Okay。And let's see in here。😔，When we receive data。嗯。

I'll just print the data out。Before we handle it。😔，And I think I'll just before we do that。😔。

Make a few line feeds。

![](img/45ed86ee30ad23118cdbf92c215699ed_1.png)

![](img/45ed86ee30ad23118cdbf92c215699ed_2.png)

So that we get a clear screen first， and then。And then we can see the data that is coming if it's coming。

 I hope。嗯。Yeah。Okay。I don't know。😔，Oh。synyntax for that。 let's see。Yeah。



![](img/45ed86ee30ad23118cdbf92c215699ed_4.png)

Yeah。嗯。

![](img/45ed86ee30ad23118cdbf92c215699ed_6.png)

嗯。

![](img/45ed86ee30ad23118cdbf92c215699ed_8.png)

![](img/45ed86ee30ad23118cdbf92c215699ed_9.png)

Okay， it tells me it has sent the data。有一点。

![](img/45ed86ee30ad23118cdbf92c215699ed_11.png)

Yeah。Yeah。Okay， let's look at。This whole thing。😔。

![](img/45ed86ee30ad23118cdbf92c215699ed_13.png)

So six times F， the broadcast address that's correct。😔，This is our own。Make address， let's see。Yeah。

 this， this。The same as our Mac address here。We have 806。😔，What's strange。I mean，8000 x。

806 should be in。Big Indian。 So it should actually be。The other way around， I think。

This is really strange。It seems like all the。Like all the。All the bes are the wrong way around。Okay。

 here' the data。Here starts the data。Hartware type 0，0，0，1。😔，Then we are talking about IPV form。😔。

Hardware address， protocol address。😔，0，0，0，1 is a request。😔，On my own。I P address。

Our own this is our own Mac address， correct。This is our own IP address， the one that we've set。

From the destination。😔，Destination， Me address and。Destination I P address hasn't been set。

On the way it it actually it has been set by， isn't it。Print it here。Okay， this should be 32。



![](img/45ed86ee30ad23118cdbf92c215699ed_15.png)

Hey， this looks differently， I think we have gotten some result。😔。



![](img/45ed86ee30ad23118cdbf92c215699ed_17.png)

![](img/45ed86ee30ad23118cdbf92c215699ed_18.png)

So here we print the data that we've received right。😔，Now I'll limit this to。Something like 64。😔。



![](img/45ed86ee30ad23118cdbf92c215699ed_20.png)

![](img/45ed86ee30ad23118cdbf92c215699ed_21.png)

Okay， we have sent this， which we had already determined seems relatively correct。

 and here we have received something。😔，Which is directed at us。This looks very good。😔，嗯。

This seems to be the neck address of。Of the gateway， the virtual gateway。Then 806 is ARP。😔。

And then it asks us。For our I P address。Here。Protocol 800， size 6， size 4。Then again。

 its own Mac address。Yes， you yes， yes， yes， yes， yes。This is a protocol。😔，嗯。

Here startss the ARP message。So this is type Ethernet。Protocol I size， hardware， size 6， Pro size 4。

 Me address， IP address。Then 00，02 is the command， which says it's a response。You know， we had sent。

A request。 and now it' sent a response。Then here， it has its own。Make address again。

Its own I P address。 and the recipient is ourmic address and our I address。Yes， this looks really。

 really good， yes。So， yeah。What we did worked。What can you say about this。

 We are really communicating with the network。 Ha。 Yeah。

 I'm totally happy now because this was really a lot of code， which we couldn't test before。

 So there was really a big potential for something not to work。😊，But， yeah。

Now we really see it has worked。 We have sent an ARP request we have received an ARP response。嗯。Yeah。

 yeah， this is nice。I'm really happy about this。So。This should be really enough for today。

 I hope you are as excited as me。Because now you can really go and start communicating with the network。

 maybe。You'll start writing your own IP beforehandr now。APV4 isn't that hard。I mean。

 it's harder than ARP， but。I can tell you far simpler thanTCP。 So if you go for IP before。

 then the next thing you should do is ICM。And after that you should do UDP。Yeah。

 but I think we will have time to go into these topics in these appendices also so yeah。Great day。

So a lot of code that we've written， I think this was。2 videos。 This was one video。

 although I haven't cut it yet。 Maybe it becomes two videos and。



![](img/45ed86ee30ad23118cdbf92c215699ed_23.png)

Another video shows the the code that we've written over。A course of four hours。

 we couldn't test before。 Now we've tested， and it works。

So I think this is really an awesome feeling because now you are really communicating with the network。

Yeah。So tune in next time， when we start looking at。The IPV4 protocol。And yes， see you next time。

 don't forget to subscribe so that you don't miss the video about IPV4。And if you liked this video。

 hit like。嗯。I like this video， so I don't know if I can hit like。

 but if I can I will because I really like this now。😊，We really got the data that we wanted。

 I'm so happy now。😊，Okay， so see you next time and bye。

