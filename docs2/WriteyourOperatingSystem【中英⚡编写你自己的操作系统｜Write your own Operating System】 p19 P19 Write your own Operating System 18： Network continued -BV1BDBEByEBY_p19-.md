# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p19 P19 Write your own Operating System 18： Network continued -BV1BDBEByEBY_p19-

Hello and welcome to the 18th part of the tutorial on writingriting your own operating system。

So in the last video， we've started discussing network communication。

But we didn't finish the drive yet。嗯。So， yeah， let's。Jump right back into that。啊啊。So。



![](img/de2eb8dbdb8833cd20f5653c22b35a57_1.png)

Now we're going to write some code for sending data and receiving data。あま。

So we'll have a cent method。😔，And a receive method。😔，Re。By the way， I noticed。

When we ran this code in the virtual machine last time， we've got this interrupt from the device。

 but。We didn't get。 I mean， this code didn't show what interrupt it was。

 And that was really just a little mistake here is。Was from the copy and paste from the data sent。

 interrupt。So this needs to be 0 x0100 instead of 200。And there's a typo。Yeah。Okay嗯。Now the1 method。

 how does it work？😔，Well first， we select。We need to know where this data has been written to。

And we get this from just the number of current send buffer。

And then we move the current scent buffer cyclic to the next cent buffer。Such that we could。

Write or send data from different tasks。In parallel。So。If we try to send more than。More than 1。

518 bytes at once， this is just too large。Then， we'll just。Discard everything after that。

Not a good idea， but。Yeah。You shouldn't be trying to send more at once anyways， so。

If we get a size larger than that at this point， then some other layer made a mistake already so。

So I think it's okay to do this here。And now we will just copy the data into the current or the send buffer that we have selected here。

Yeah。Okay。So we set this pointer to the end of the data that we want to send。And another pointer。嗯。

To the buffer where we want to write it。Yeah。So， we take the buffer that。

That we have selected up here。 Okay， so this is buffer that we are using。Yeah。Okay。

 so we move these two pointers。To the end of the buffers in those sources。

 the end of this buffer and destination is the end of the send buffer where we copy this。嗯。

And then we move both of them to the left。In the soup。And inside this loop， we just copy。

The data from the source buffer to the destination buffer。So now we mark this buffer as。In use， so。

So it's not allowed to write anything else in there until it becomes available again。う。With this。

 we clear any error messages that have been there before。Okay， and this is。

I don't even remember what this actually does， but。

One of the things we do here is we encode the size。Of what we want to send， and。

This here is the part that I told you about that had this mistake in it。Which I have found。😔。

So if you're curious， you can look into the。Technical menu of this。AM D AM79 C。9，7，3 chip。

The documentation is quite good。You can look into that and see what all this means。😔。

And here we have set the size。Okay， after that， we just have to write the。

Command to send the the data into the。啊。Into a zero register。Yeah。And this is a command。Okay。

 let's see if this works。😔，Okay， it compiles。Now we actually get this initialization done ina。So El。

In the kernel， I just want to test this code so。Okay， so the PCI。Code puts this driver into the。

Into the driver manager。What I'm going to do now。I's really a bad idea。Make this。

This data here in the driver manager public just so that I can access it。Okay。

 I'll just look into this array and take a second。So actually， is the third device。 You know。

 the first is a keyboard handler as a keyboard。 Then we have some mouse。

 and the third one will be the。The network the network card， of course， this is a really bad idea。

 So I have had really bad problems。With every time I changed a little bit。 And then this。

 this index would have changed and。Yeah， so。This is really a bad idea， actually。

 but for testing purposes， I think。It's okay。

![](img/de2eb8dbdb8833cd20f5653c22b35a57_3.png)

Okay， let's see。

![](img/de2eb8dbdb8833cd20f5653c22b35a57_5.png)

Okay， and it tells us it has sent this data out。But of course， hello network is not really。

Anything useful so。This is going to a virtualized network inside。retrotrobox。And。Yeah， this。

Just discards this because it cannot handle this。 It's not a useful information here。



![](img/de2eb8dbdb8833cd20f5653c22b35a57_7.png)

![](img/de2eb8dbdb8833cd20f5653c22b35a57_8.png)

Okay， and here。Here， in case we have received data， I will just jump into this receive method。

Actually， I don't know why we set the available flag for the receive path to 0， but。I mean。

 I've taken this from code that I've tested in a different operating system。Yeah， it's。It must work。

 I've seen it work。Okay， so in the receive method。😔，Yeah。

 we just iterate through the receive buffers。嗯。As long as we have。Receive buffer that contain data。

So what we will basically do now is in this loop， we will。We will the current received buffer。嗯。

Cyic around like this。And we will do that until we find a receive buffer that has no data。Okay， so。

P first empty if the first flag is 0。So inside this loop， we now have。

We have a receive buffer that holds data。So these are all 32 bit。台湾。Integer just that I a code here。

😔，I don't remember what this did。 I think it was for。嗯。I don't remember what it did。Okay。

 so now we read the size from。Doess a receive puff？我没。Then。Yeah if so size。😔，Its larger than 64。嗯。

Yeah， this is， this is the size of an ethernet2 frame。So if the size is。

That of an E andnet2 frame then。We basically just remove the last4 bytes。

Because they are a checkum and we are not really interested in the checkum at this point。没。Okay。

 so now we copy the address of the buffer。And。Yeah。

 so now we could basically do something like iterate over the data。IEx。Maybe something like this。😔。

So， this would。This would just print what we have received。😔，Okay， and in the end。

 but inside the loop。嗯。We have to。We have to tell the device now， okay。

 we have finished handling this。 You can have this back now。So。You can have it back， and。ど。Yes。Okay。

 so this clears the。嗯这不号。Okay， so。Can we test this code now？😔。

Not sure if we can really test the code。😔，Maybe。😔，I后。Yeah， maybe if we。嗯。

If we go to the network configuration of thebox， by the way， there's Mac address here。

This is actually the Mac address that you will see when you print out。Here's this。

Theres Mac address up here， but actually the Mac address you will see if you print this out is in the reverse order。

 so the bytes are in reverse order。So you will not see 0，8 in the beginning， but 0，8 in the end。

Because here we've start this in big Indian notation， because when we transfer data later。Yeah。

 when we send data， which contains the Mac address， then。

It is expected that the Mac address is big Indian encoded。 So we just store it that way in Ram。

 so then we can just。Printted out。Okay， so let's see。 I'll just do something like。Who， I don't know。

嗯。I don't think this will work because we haven't registered an IP yet。😔，Inside the operating system。

 So yeah。I'll just cancel that。嗯。

![](img/de2eb8dbdb8833cd20f5653c22b35a57_10.png)

嗯。Yeah， so I guess we have to live with this now so that we haven't tested this code yet。Yeah。

 maybe if we hard coded something like an address resolution protocol request。嗯。

Maybe we would get something back。😔，嗯。But I think if anything， I'll do that in a different video。嗯。

So。Yeah， the thing is I'm not sure that I'll have time to go into the network protocols。Possibly yes。

 but I think I'll do that more as as an appix or something。

But I want to tell you at least a few things about the the architecture of。嗯。Of the network now。嗯。So。

 I mean， you can send and receive data now。 And that is basically like being able。

 like knowing the alphabet。 You know， just because you know the alphabet。

 you cannot talk to someone because you don't know his language， possibly。

So in order to talk to someone， you don't only need to know the alphabet。

 you also need to know his language。And。Yeah， the， the language in that metaphor。

Corresponds to the protocols and these are the really the most common protocols and you need to support at least these to be able to communicate with the network。

So you need to implement the EAnet2 frame protocol。And by the way。

The Wikipedia pages about these protocols are really great。

 they will probably show you everything you need to know。I mean， Ethernet2 frame is really simple。

 It basically has the source， the Mac address of the source computer， the Mac address of the。

Destination computer and protocol number。Okay， so。And then just some data。

And depending on the protocol number。You pass that either to the ARP address resolution protocol。ARP。

You do that if。Yeah， so。The source and destination Mac address are these first 12 heights。And then。

Starting at the 12th sp， you have a 16 bit integer。Which is the protocol number。

 And if this protocol number is 0 x。806， it has to go to the address resolution protocol。

And if it is0 x。800。It's going to the internet protocol。Also， known as I P。

And you've probably heard that short term， for example， with IP addresses。So。The Internet protocol。

Has its own header again， which contains， for example， the IP address of the machine。

 of the source machine and the destination machine。You know。

 this Ethernet2 frame is really low level， it's the communication between the network chips。嗯。

But the I is。It's a logical address。 You know， this is a hardware address。 This is a logical address。

 because。If you didn't have a logical address。Then you would have to reconfigure your network every time you change out a network device。

 And thats that would be really。A lot of trouble to go through and wouldn't really make sense。So。

Yeah， and the header of the。IP。系。Internet protocol。You look at the offset 10。So the first 10 bytes。😔。

I think they all。Soce IP destination， IP， and so on。By the way。

 the address resolution protocol is there to ask a computer， hey， what is your IP address？Okay。

 so if you don't implement this， your machine will not communicate with anything because the other machine will try to ask you。

 what is your IP address and if you haven't implemented this。

 then you aren't responding and then it will just ignore you。So you need to implement this。

 then the Internet protocol。Here at the offset 10， you have an8 bit integer。

And depending on that value。嗯。If it is one。Then it needs to。

 you need to pass this so called payload after the header。By the way。

 the length of the header is also somewhere in there。

So you can take this pointer from this pointer and the length of the header。

So if this protocol number is one， you need to pass it to ICMP。

 the Internet control message protocol。Okay， this is， for example， used for pin。

So you should really respond to pings because otherwise computers will again think your machine is down and stop talking to you。

If you have。The number six there， then this is going to the transmission control protocol。

So this was ICMP。😔，Transmission control protocol also known as TCP。And maybe here you see something。

TCP，I P that's。That's where that name comes from。It's the combination of this protocol with this protocol。

嗯。By the way， this is talking about IP V4， by the way。Yeah。

 transmission control protocol is number 6， and if it's number 17。

Then it's going to the user data Gr protocol。Also known as。UDP。You don't need to implement UDP。

 but it's quite simple。So。I think it's probably a better idea to implement UDP before TCP because TCP is really。

 really hard。嗯。Yeah， but this is really the。嗯。The architecture of your network stack。

 you know the Ausie layer model。Yeah， so this is how that works， as I said。

 look into Wikipedia for this。嗯。Yeah maybe let's talk about a few more things in virtualualbox when you want to talk to the outside world。

嗯。Inside this virtual network， that virtual box。Os。Virtual box has a virtual I P address，10，0，2，2。

And this is the default the default gateway。 So when you send data there， then。Yeah， you just。

 then it can go outside。And actually， you。This is also a virtual IP address with which you can address your host machine。

 You know you have the host machine which executes virtual box and in the virtual box you have the guest machine。

 This is virtual machine terminology so。So through this IP address。

 you can communicate with the host machine， you know， if you run some server on the host machine。

And you have network access in the guest machine， then you can access the server on the host machine through that IP address。

And it's also the default gateway。Okay， and you would assign something like the IP address 100。

To 15 or something to your guest machine。 So this is a host。It's also the gateway。

And this is a guest。Yeah， you can assign this anything you want， but。I think it should really have。

 the same first。But it's here， because。嗯。Because of the subnet mask。So。

Yeah let's talk a little bit about a subnet mask because I think that's really something you don't necessarily understand。

It's definitely something that I didn't understand before I wrote my own code for all this。

So in a Windows machine， you usually。When you do the network setup up， I mean， today you have。呃。

You have this DHCP， which assigns。Your I address and everything automatically。

 But at least in previous years， you have to assign your I address。

 default gateway and subnet mask manually。And what that means is。

 so the subnet mask is something like。255。2，55。2，55。That0。 And what that means is。嗯。Yeah， if when。

 when you want to send some data out。嗯。You are really， you really want to know， where do I send this。

嗯。I mean， inside network。Maybe you have a switch。Okay， you have a switch and several machines。

 and they have relatively similar I addresses， which maybe only。Differ in the list。

In the last bite here。If they also differ in the second to last bite， you wouldn't need 255， 255。

 255，0， but 255， 255，0，0。So the subnet mask basically says if your IP address。Bit wise。

 And the subnet mask is equal to。To the target IP address。Pwiseice and submit mask。

Then the machine sings。 then you should think your。System should think， okay。

 this is inside my own network so I can communicate with that directly through the switch。

So I can just use that as my target IP address and。Target Me address。And otherwise。

 so if if my target IP address。So。Target I P。Bitwise and submit mask。If that is equal。

To the source IP address。It was an Subnet mask。Yeah， okay。 so if the target。

I's the same as a source except for the bits that are zero in the subnet mask。

Then we think it's the same network， and then we send our data directly there through the switch。

And otherwise， we sent it to the gateway instead。 And then we say， okay， here gateway， take this。

 you take care of it。 You know， then the gateway， then it's the gateways problem to send this out to the Internet or something。

O。这样。So。So that's what the subnet mask does。Okay， so， so I think this。



![](img/de2eb8dbdb8833cd20f5653c22b35a57_12.png)

Should be。Enough for today。As I said。If I have the time， I will probably go into this。Protocols。

 a little bit。In something like an appendix to these tutorials。But in the next video。

 I want to start talking about hard drives。So， yeah， hard drives is the next topic。

 And if I find the time later， I will then go into these protocols， at least ethannet frame ARP IP。

Before ICMP and UDP， as I said， TCP is really hard。I probably not go into that， but。Whatever， so。

So yeah， that's enough for today， hit subscribe to so that you don't miss the next video about hard drives。

And if you liked this video， hit like。Thank you very much and see you next time， bye。

