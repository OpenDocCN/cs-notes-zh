# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p24 P24 Write your own Operating System A03： Internet Protocol (IPv4) -BV1BDBEByEBY_p24-

Hello and welcome to the third appendix to the tutorial on writing your own operating system。

So in this third appendix， we will be looking at the IPV4 protocol。嗯。Yeah。

 before we had written a driver for this network trip that Vibox offers。We have。A handler。

 which is connected to that driver。 And this handler basically looks at the two bys starting at。

So we are getting raw data from this。This object basically looks at the two bytes starting at offset 12。

And depending on these two biteits。The data is then passed to the next handr。

 and we already have written。The handler for this protocol。Address resolution protocol。And today。

 we will be。Implementing。The handler for the protocol 800， the 0 x 800。嗯。

So this is the IPV4 protocol and。This is quite similar to the Enet frame protocol itself in that it basically looks at。

A certain offset， in this case， offset number 9。And。Yeah， depending on that。

 it just passes the data on to。The next protocol。嗯。

So why aren't these things directly attached to ethernet frame Yeah。

 well ethernet frame is more on a hardware level and this is more on a software level。

 So this basically just says， hey， I have gotten something。Just some raw data。

 And this thing decides， hey， is this really for me or is this for someone else。

 So should I keep it or should I should I keep it and。And process it。

 or should I discard it or maybe pass it on somewhere else。Okay， so again。

 the Wikipedia page about IPV4 is again， very helpful。So。There you will see again， how such。

Such an IP。Message is structured。So， we have。1 by containing。嗯。The version and the links。

Off the header。Version and length。Which are half pipes。Both。Then， we have1 B。Which yeah。

 in the Wikipedia page， it tells you different this is differentiated service services code point。

And explicit congestion notification。嗯。But in practice， this is used for something else Nowadays。

 This is for the type of service。And。Yeah， that。That。Mostly says， hey。

 is this a privileged message so should it be？Handed with priority or not。So。Yeah。

 we will basically just set that to zero all the time， which says no this is not privileged。

 this is just a normal message。Then you have two bytes。😔，So呃。This is one by， This is one by。嗯。

These are two bytes， which。Tell us the。Yeah， the length of the full message。

So this tells us the length of the full message and this only of the header okay。

And both of these are。In 32 bit integers so。So the numbers that you find here and there you have to multiply with four to get the number of bytes。

Okay， yeah， this is the first。32 Bs。Lock。And then we get something called the identification。

And another two bytes。Yeah， which。Which actually。3 bits。😔，And。13 bits。系。Yeah， this。

These three bits are for fl。And this is an fragment offset， and I'll explain what that is。

So these messages have a limited size。Okay。So。

![](img/dbee1152748108010cd0e23b83e02274_1.png)

Ethernet frames， what was it somewhere around 2 kilobytes is the maximum size of an ethernet frame。

So if you want to send something that is larger than2 kilobytes。



![](img/dbee1152748108010cd0e23b83e02274_3.png)

Then you have to send multiple frames。And yes， this is really for。嗯。Yeah， for identifying。

These fragments， okay， so you have to send multiple fragments of the message。And yellow。

Each individual fragment might arrive in。In the wrong order。And， and yeah， this。I don't know this。

This is the purpose of this is to， to sort out which。

which messages belong together and in which order， but yeah to my knowledge this isn't really used in practice so because TCP has its own ways and UDP has its own ways and ICMP is small enough。

So TCP and UDP both have their own ways of identifying what belongs together and in which order。嗯。So。

 yeah， we will。嗯。We will basically just use some random。Number for this。 And we will always say。

 I mean， I mean， we will be sending small packets only。 So， so we will basically say。

 we don't fragment and。We only send the fragment at offset 0， okay。

So we will only work with small messages， so we don't have to deal with this stuff anyways。Okay。

 then after that， we have one by。Called time to live T T L。There's a very common。

Short term for time to live。嗯。Then， the protocol。Both one bys and then a two by checks them。Okay。

 so the protocol， yeah， that's this number。1 for ICMP 6 for TCP and 17 for UDP。 And yeah。

 you will find a list of of these numbers。Easily on the Internet， so。I'm not going into that。So。Yeah。

 this is really this number that we use for distinguishing where to pass this。The time to live。Yeah。

 the time to live is an interesting thing because you don't want these messages to。

To circle around forever。Right so if you send it， you either want it to arrive or be discarded at some time you。

Because in theory， it could happen that if you didn't have this time to live。

 that the message is passed back and forth between two gateways。Yeah。

 this is what this time to live is for。 I mean， actually it。At first， this was really used as a time。

Value， but。Yeah， over time， it has developed that there's time to live every hop that， I mean。

 a message。I mean， a message can go through multiple machines right。

 and every machine it goes to decreases this time to live by one。And when it arrives 0。

 the message is discarded。 Okay， and that just makes sure that the that the message isn't。

Is't circulating forever。 Okay， and actually， this is actually how the trace route program finds out。

嗯。The root of a packet， you know， when you。When you trace root。😔，An Ip， it just sets this value。

 I think， to one。 And then it gets a notification。 Okay， so this message has only gone to。Yeah。

To this point， Because this is a point where this has。嗯。Has reached0， So then。

You apparently get an answer saying， yeah I have dropped this。And after that。

 it sends another message built with a tomb。When。It's discarded at the second top， gets a message。

 This is where it has been dropped， D lap。IP address， then it sends another message with。3 and so on。

 and so。Like this， it always gets messages。Of where。Where these packets。Have been dropped。

 So this shows you， this then shows you the route that。That your messages are going。Okay嗯。Okay。

 and then there's a checkum here， which is only a checkum for the header， not the full message。嗯。

Yeah， the computation of this checks is a bit， I don't know it's a bit。Unnecessarily complicated。

 I think， in my opinion， but。Yeah。The Wikipedia article about that check sum is quite good。So。

It's basically just， you basically just add all the。呃。All the。2 by pair。And then you。

And then you basically just flip the bits。Okay， but when it does some。

Some more stuff if you have overflows in there。Yeah。

 I'm gonna I'm just gonna to show you the code and。That's not really hard。Okay。

 here do a track some yeah and then after that。You have 4 by for the。嗯。For the source of the message。

So the sender and four bytes for the destination。O。So if you count this， then these are 20 bytes。

So why is there this length in the beginning。Well。You are allowed to add some more options behind that。

But I don't know these options very well。 and I mean you can look at the Wikipedia article on that。

 but。To my knowledge， these options are basically unused。So， there's almost no。Deice and so yeah。

 these options to my knowledge are。Are just unused nowadays so。

But that's why you have this length in the header。嗯。Yeah， and。Yeah， okay。So。So let's code this。😔，嗯。

Yeah。Okay， so。As usual， I'm going to make a structure for for such a data block。好。Yeah。So。

I put the length of the header here， first。Just because of the。Of big Indian encoding。Okay。Yeah。

So this version number will always be4。😔，Because we are using IPV4。These are for for bits， always。😔。

And8 bids for the type of service。😔，嗯。Total。嗯。Yeah。O。Now， this is going to be。And E frame hand done。

 you know， because we are connecting it to the Enet frame provider。

And we are basically doing the same system again。The Internet protocol provider will。

We'll look at an internet protocol message and depending on the protocol pass the message to an internet protocol handler。

 so basically the same idea that we had here where we had an Ether frame provider passing the messages to Ether frame handlers。

And it's actually so similar that I'm going to copy some of this。😔，Yeah。Now， here we only have。

Only one by it for the protocol of IPV4。Yeah。Yeah。Okay。And when we want to send something。

Then we only need a 32 bit。😔，Interron now to， to identify the。I P address。Okay， but。One thing more。

 I will also pass the。And。These values are source IP and destination IP。

 I will also pass to the hand club。Because for example，'s a TCP。嗯。Handler uses these well used。

You know， you can have。You can have multiple connections to different Is， but on the same part， so。

That's why you need these here。So these are to distinguish different connections on the same。呃。

On the same part。😔，Yeah。嗯。Okay。And for the provider， I will again copy some of this。😔。

So here we only have。1 by。So， we don't need that many。Andless here。😔。

So here we don't receive raw data。 Here， we receive ethernet frame payload， so。

That's where I have copied the method from the user frame handleer now。😔，Okay， and when we。😔。

Sent something。Then we have to pass an IP address。😔，Protocol number。And the data that we are sending。

😔，Okay。No。啊。We also need a way to get this check some。Yeah。Okay。Okay。Okay。

 so what do we need as parameters for the。Constructor。😔，Where we meet。😔，The back end。Yeah。You know。

 we pass it to the base constructor。Then。Yeah， then we need。😔。

We need a pointer to the ARP handler because we need to talk to the ARP handler if we。嗯。

If we want to get。And。The Mac address for an I P address。 You know， we， we want to。

To use this resolve。😔，Method here。Yeah。Yeah。Yeah。Yeah。Okay， and then what we need is。😔，I mean。

 we can already ask the back end for our own IP address。

But we need the I address of the default gateway and our subnet mask。

 and I will go into why we need that。嗯。So。は。Okay。没有。Okay， so this is。How we do that？😔。

Now let's go into the CPP file。😔，He。Okay， so we will do it basically like here。 So we've start the。

The protocol number and the back end。And now we register ourselves in the back end as handler for that protocol。

😔，Yeah。Yeah。So default behavior as usual。😔，We just discard the message and say we don't want to send it back。

And yeah， when we want to send something。Yeah， we just pass it to the backend。Yeah。嗯。Okay。

So this is for the handler。😔，Okay， so。The constructor will set all the handless20 for at first。

It will also store the back end the pointer to the address resolution protocol。

 the gateway IP and Snetm。Yes。So， here we pass the。Eha times 0 x800。To tell the Iaf frame Han。

That this is our Ea type。Okay， and now I， I would just store ARP Gateway， IP and SnetMask。Yeah。Okay。

 so when we receive data。嗯。Yeah， we will basically do the same as in the internet frame。Actually。

 why aren't we checking the size here？😔，下。Yeah。So we first check if this。😔。

If the data we received is large enough。😔，Then we overlay this message with this structure that we've written。

😔，Yeah， we we haven't really checked if the message is for us so if。😔，If I P message。

So only if the message is really for us。We look at the。And plus。Yeah。

So if we have a handler for that protocol。😔，Then， we call it。Handler method。😔。

So we give it source and destination。😔，うん。Then the data that we pass is a payload behind the。Frame。

Behind the head up。But we don't actually know the size of the header because of this options that could be there so。

What we have to do is。呃。Yeah， we don't add the size of the。How are we at the。

The content of this header length。Multiply with 4， because it's in。嗯。And 32 bit steps。Hey everyone。

 I'm cutting this video right now and I don't like interrupting it like that but yeah I just realized that I made a real huge mistake here and yeah normally I would just put some text over it but yeah this is such a huge mistake which and I didn't really catch this mistake in a later video where it really caused trouble。

嗯。So that's why I'm cutting this in here， although I don't like it。嗯。Yeah， so。

The problem is that here in this。In this line， I basically pass the complete ethernet frame to the next level。

 but the thing is that the IP message can be shorter than the ethernet frame and the stuff behind it is just garbage。

And okay if you just print it， then the stuff behind it it's all zeros。

 so print app immediately terminates on them， so you won't see them but yeah in a later video this really caused a lot of trouble and as I've said I wasn't able to find it and yeah this is here this here is a big problem so you shouldn't use the size here。

 you should use the total length from the IP message。

And actually you shouldn't even use that the thing is。That， I mean， normally you would say， okay。

 an IP message is inside an ethernet frame， so it must be shorter than the ethernet frame， right？

But the heartbleed attack uses a ping with a fake total length in the header。

 and that causes in before the。This error was fixed in the major operating systems。は。

It worked like this。 They， They sent you a ping with a fake length。A much too large length。

And that caused them to just send back not only the ping。

 but a lot of data behind it and that could include passwords that you just entered。

 I mean this is somewhere inside the network code， you know。

 so it's probable that you catch something that you've sent over the network like a password on HTTP。

Stuff so。So yeah。 So because of that， you shouldn't use the total length from the I P message。

 You should， in fact。Use。The minimum of。呃 a。Of the length that IP message tells you it had。

And the size of the。啊。Of the Enet frame。 So that。So that even with a fake length。

 you won't do stuff with the data behind the actual。Behind the actual ethernet frame。Okay， so。Okay。

 so yeah， so this is fixed now and now let's get back to the original video bye。Okay。

 so now we have passed it to。The handton。And。And when the handler tells tells us that he wants to send the data back。

Then what do we have to do？We have to switch out the source and the destination just like here。Yeah。

Yeah。So this is the same thing that we did before， so we just switch out the source into the destination of the message。

Then we reset the time to live。To something like 64。Sts。And yeah， when we。

We have now changed the header。And because of that。That we have to update the check sum。

I think if we didn't change the time to live， I think the checksum should stay the same and we wouldn't have to recalculate it。

 but。But I think it wouldn't be a good idea not to reset the time to live， so。Okay。So by the way。

 this checks some。There are protocols which allow you to just set the check sum to0。

 and then if the check sum is0 it they don't check if the checkum is correct。

 but IPV4 is more strict on that。 So if you don't have a correct check some， then the recipient is。

They' supposed to drop the message。So you really have to implement this method here。嗯。Okay。

 but first， I will implement this send method。Yeah。We really should ride a better wave。😔。

Of doing this。Like a static melo function or something， but yeah。Okay。Yeah。Yeah。

So we set the version to far because it's IPV4。I want to record a TOSs only。😔。

The type of service is just zero。😔，So it's not a privileged message。😔，Okay。

So now we have set the total length。 but the problem is this is。A big Indian value。

 So we need to switch the。S pipes。Okay。So now we have the total links。😔，As I've said。

 I'll just set the identification to some random number。This is just one。

So this is the message is not fragmented。😔，So in my implementation， I use this。

 but I'm not sure if that was for the flex， Ill just make it the way I edit did it in my implementation。

😔，行。I just used this these together。Okay。嗯开。Okay。So then we set the checkum。😔。

We need to initialize this with zero because。The checkum will also add this value。

When it adds all the values together， and if it wasn't zero， you would get an error。

And the packet would be dropped。Okay。Now， so the header is finished now。😔，嗯。So， now I'm going to。

To copy the。The message that we are supposed to send。So a buffer itator。😔，And the detectoratorator。😔。

So this is not the fastest way to do it， but。😔，So here I now copy the data from this data。😔。

To the area behind the buffer。So， now the。The IP message is complete and we give it to the back end。

And this is the point where the。嗯。Yeah， this is a point where the subnet mask and default gateway come into play。

So。嗯。So by default， we want to send the data to the destination。O。So this route is really the。

The IP address that we will resolve。Using the ARP， but。Yes。

 so if the target IP address is not within our own subnet， so not within our local area network。

 maybe。嗯。So if it's somewhere outside。Then we don't talk to the recipient directly so we don't resolve the Mac address。

Ourselves。In that case， we leave this to the gateway， okay。So。对。

So this is how we determine if the recipient is in the same。Local area network as as ourselves。

 so you can have a smaller local area network， and one of the machines is the gateway that talks to the internet for you。

嗯。And if you have a machine outside of your local area network。

 and this is determined by this subnet mask。嗯。Then you don't send the data directly to the recipient so you don't resolve the recipient's IP address instead you resolve the IP address of the gateway and send it to the gateway。

Yeah。Okay。对。Yeah。So now we ask the ARP for the Mac address。

 which we pass to the Ethernet frame handler。As I've said before。

 this is actually a pretty bad idea because。We have this loop here。And if we are offline。

 then we will never receive this message that。That puts the。The result。Into our cache。

And then the result will always stay as a broadcast address and then this loop never terminates。

So you need to come up with better ideas here。Yeah。So I want own an aha type。Which is just the0 x800。

 but in Big Indian。Then。Yeah， we sent the full buffer。And full buffer has size。This。Okay。

 so now we after that， the backend should have sent this。And then we should。😔。

We should free this data again。😔，And I think in the use sub frame。We did the same thing。Here。

 we allocated the buffer and。Added our own data to it and copied the data that we are supposed to send。

O。😔，Yeah， so this is all we have to do。Except for the checkum。But the checkum isn't that hard。

 actually。Okay。So。Yeah， we， we add the。The data， but in big Indian again。So， no。

We've added that in big N。然后。Yeah， what happens if the。Data we sent is an odd number。

Then there would be one byte left at the end。So if it's an odd number。Okay， so what I'm doing is。

I cast this to。One by， a one by area。So an array of single byte values。When I take the last one of。

A face。So this is the last one of these。😔，Let I shift it to the left。Yeah， cospic again。😔，O。

Looks strange， actually， because if we convert this to big Indian all the time。😔，And this last。声音。😔。

我代妈。Yeah。Now， in the end。We will return。This1 value， again。To big Indian。But in between， there is。

 yeah， this is a strange convention。So if we have。If we have。嗯。An overflow in this。

When we sum this up。😔，And then we。We basically have to， to add the。

Bits that we have that were overflown。Back to the 16 bits。You know we have a 32 bit value here。

If we have an overflow， then that's the case when。When there's something above the。

Above the last 16 bits。Yeah。Okay， so we take the。So overflown bits and just add them to the last ones and we do this until。

The first。16 bits are all0， okay。It's a strange。Strange thing。If you ask me， it's too complicated。

 but yeah。Yeah， this is all we have to do。For IPV4。



![](img/dbee1152748108010cd0e23b83e02274_5.png)

![](img/dbee1152748108010cd0e23b83e02274_6.png)

and the subnet mask is basically the same thing。😔，Not 255，255，255 as a normal。Subnet mask。😔，O。Yeah。

Let's see， so。We can kick out this ARP resolve， because。IPV4 will。

Will resolve the gateway address anyways when we sent something。不。

So this would be the big Indian encoding of IPV fraud。So0 x 800。

So we want to send something to the gateway。😔，Using IPV file。



![](img/dbee1152748108010cd0e23b83e02274_8.png)

![](img/dbee1152748108010cd0e23b83e02274_9.png)

Yes。

![](img/dbee1152748108010cd0e23b83e02274_11.png)

![](img/dbee1152748108010cd0e23b83e02274_12.png)

Okay。

![](img/dbee1152748108010cd0e23b83e02274_14.png)

![](img/dbee1152748108010cd0e23b83e02274_15.png)

![](img/dbee1152748108010cd0e23b83e02274_16.png)

![](img/dbee1152748108010cd0e23b83e02274_17.png)

嗯。

![](img/dbee1152748108010cd0e23b83e02274_19.png)

嗯。Okay， so。I think this is。Yeah， this is。The ARP request。



![](img/dbee1152748108010cd0e23b83e02274_21.png)

And here we get the ARP。😔。

![](img/dbee1152748108010cd0e23b83e02274_23.png)

Response。😔。

![](img/dbee1152748108010cd0e23b83e02274_25.png)

Okay， so I found the problem。 The situation was that I didn't make these on rawaw data received methods virtual。

So。And actually， nowhere， neither here nor。There， and also， not。Here。So。So， when。

I'd derived classes from them and overwrote those methods， it just didn't work。So the AM D， actually。

 when it tried to pass the data to。To the on raw data to the raw data handleler。

 it actually sent it to this base class raw data handleler， which just。Which just returned false。

 So you could。You could see the data。Because here in this receive method。要有诶。The data was printed。

But。So it was printed， but it wasn't passed through the chain to the handlers。



![](img/dbee1152748108010cd0e23b83e02274_27.png)

So now I made them virtual， and now。Now when I run this。😔，嗯。



![](img/dbee1152748108010cd0e23b83e02274_29.png)

Then you can see here's an ARP request， here's an ARP response。And here is this IPV4 message。

As you can see here， we have。We have type 800。Instead of 806 that we had before。

And here's the IPV form message，4 or 5 is sub version and the length。

0ero is the type of service length 1 a。Is。26， I think。Does that make sense， Yeah。

 20 the header has size 20 and we send fua， which has size 6。So 26 makes sense。嗯。Yeah。

 then this identification and fragment stuff。😔，And。Yes， this seems to be the IP address。

Recipient is 100，2。And sender is 100215， recipient is 10022 per gateway。Thank。The protocol。YeahYeah。

 the protocol I set the protocol to 0 x 800， I think。That doesn't really make sense here。😔，Here。

 this doesn't make sense。😔，Because this is an IPV4 protocol and had an ethernet frame protocol。

 So here we should put something like0。X 0，1 for IMP。0 x06 for TCP， but 0 x 0，0，08 didn't make sense。

嗯。40 is the time to live， Mrs。Protocol。Yeah。I P address and this。66，6。F6， F is the full bar， so。啊，你子。

The ASI codes， you see。6 f，6 F must be the small O because we have two of them。Yeah， so， so yeah。

 we have sent。An actual I message， although it doesn't。

ItIt's not an actual ICMP message or TCP or UDP or anything， but yeah， this is an。An I P message。嗯。

One last thing that I。Think we should do。诶。Here when we send， we set the check sum to0 before。😔。

We compute the checksum。And here we didn't do that beforehand， so。I think we should do that。

 because otherwise， we might get。False check sums， although I have run this code and it worked， but。

Whatever， I mean， it， it might。Po possiblyssibly it has been processed by something that just ignores the checks just like we do so yeah。

But yeah， there you have it。We are sending IPV4 messages。We are not receiving IPV messages yet， but。

But we will do this next time。Yeah， next time we will implement the ICMP protocol。

 at least a small part of it， the ping。然。Which is done on this protocol。So。Yeah。

I think this is a good point now to finish the video。Yeah。See next time。

 don't forget to subscribe so you don't miss the next video on ICMP so you'll learn how to paint。嗯。

Yeah。Don't forget to hit like if you liked this video， I think IPV4 is really something nice to have。

 so I like this video。Yeah， so see you next time。

![](img/dbee1152748108010cd0e23b83e02274_31.png)